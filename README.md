# ktop

## Шаг 1: Збереження скрипта як плагіна kubectl

#### Збережіть скрипт локально. Переконайтеся, що скрипт має правильні права на виконання:

chmod +x /path/to/your/script.sh

#### Переіменуйте скрипт для використання як плагін kubectl. Скрипти плагінів для kubectl повинні слідувати у форматі kubectl-<name>.

mv /path/to/your/script.sh /usr/local/bin/kubectl-ktop

#### Перевірте доступність плагіна:

kubectl plugin list

## Шаг 2: Тестування плагіна

#### Тепер ви можете протестувати скрипт, запускаючи його як плагін kubectl:

kubectl ktop pod -n kube-system

#### Ця команда повинна вивести статистику використання ресурсів для подов у просторі іменувати kube-system.

## Шаг 3: Зареєструвати зміни в репозиторії

#### Клонуйте репозиторій, якщо у вас його ще немає локально:

git clone https://github.com/######/ktop.git

cd ktop

#### Створіть новий ветку для ваших змін:

git checkout -b feature/add-kubectl-plugin

#### Додайте файл скрипта в директорію скриптів:

cp /path/to/kubectl-ktop scripts/

#### Додайте зміни в git і зробіть комміт:

git add scripts/kubectl-ktop

git commit -m "Додати плагін kubectl ktop"

#### Запустіть зміни на GitHub:

git push -u origin feature/add-kubectl-plugin

## Шаг 4: Створення Pull Request

#### Перейдіть на сторінку свого репозиторію на GitHub. Ви повинні побачити повідомлення про нову ветку. Натисніть на кнопку «Порівняти та витягнути запит». Введіть опис ваших змін і створіть запит на отримання.

## Шаг 5 Використання скрипта як плагін kubectl:

#### Для використання скрипта як плагіна kubectl виконайте наступні кроки:

#### Встановіть скрипт у шляху, доступному в `$PATH` з іменем `kubectl-ktop`.

#### Ви можете викликати плагін за допомогою команди:

kubectl ktop <resource-type> -n <namespace>

#### Наприклад, для перегляду використання ресурсів подов у системі kube:

kubectl ktop pod -n kube-system

Usage ./kubeplugin [type resources] [namespace]

Example

./kubeplugin pod kube-system
```
pod kube-system coredns-76f75df574-htj8q 2m 44Mi
pod kube-system coredns-76f75df574-qxfhd 2m 48Mi
pod kube-system etcd-docker-desktop 20m 334Mi
pod kube-system kube-apiserver-docker-desktop 23m 289Mi
pod kube-system kube-controller-manager-docker-desktop 23m 134Mi
pod kube-system kube-proxy-jt25p 1m 69Mi
pod kube-system kube-scheduler-docker-desktop 4m 69Mi
pod kube-system metrics-server-84989b68d9-z484b 4m 24Mi
pod kube-system storage-provisioner 2m 18Mi
pod kube-system vpnkit-controller 0m 42Mi
```
