LEMP-стек за 5 минут
====================

* **[Начало](#%D0%9D%D0%B0%D1%87%D0%B0%D0%BB%D0%BE)**
* **[Ингридиенты](#%D0%98%D0%BD%D0%B3%D1%80%D0%B8%D0%B4%D0%B8%D0%B5%D0%BD%D1%82%D1%8B)**
* **[Начальные приготовления](#%D0%9D%D0%B0%D1%87%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BF%D1%80%D0%B8%D0%B3%D0%BE%D1%82%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F)**
  * [Регитсрация](#%D0%A0%D0%B5%D0%B3%D0%B8%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D1%8F)
  * [Установка нужного дистрибутива](#%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-%D0%BD%D1%83%D0%B6%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B4%D0%B8%D1%81%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%82%D0%B8%D0%B2%D0%B0)
* **[Chef - или подготовка шеф повара](#chef---%D0%B8%D0%BB%D0%B8-%D0%BF%D0%BE%D0%B4%D0%B3%D0%BE%D1%82%D0%BE%D0%B2%D0%BA%D0%B0-%D1%88%D0%B5%D1%84-%D0%BF%D0%BE%D0%B2%D0%B0%D1%80%D0%B0)**
  * [Что такое Chef?](#%D0%A7%D1%82%D0%BE-%D1%82%D0%B0%D0%BA%D0%BE%D0%B5-chef)
  * [Архитектура Chef](#%D0%90%D1%80%D1%85%D0%B8%D1%82%D0%B5%D0%BA%D1%82%D1%83%D1%80%D0%B0-chef)
  * [Регистрация и настройка Chef-Server](#%D0%A0%D0%B5%D0%B3%D0%B8%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D0%B8-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-chef-server)
  * [Настройка Chef-Knife (нож шеф-повара)](#%D0%9D%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-chef-knife-%D0%BD%D0%BE%D0%B6-%D1%88%D0%B5%D1%84-%D0%BF%D0%BE%D0%B2%D0%B0%D1%80%D0%B0)
  * [Настройка Chef-Client](#%D0%9D%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-chef-client)
* **[Создание и применение рецептов](#%D0%A1%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B8-%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D1%80%D0%B5%D1%86%D0%B5%D0%BF%D1%82%D0%BE%D0%B2)**
* **[Заключение](#%D0%97%D0%B0%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5)**
* **[Полезные ссылки](#%D0%9F%D0%BE%D0%BB%D0%B5%D0%B7%D0%BD%D1%8B%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8)**


## Начало
Всем привет! В этой сатье я расскажу как за пять минут приготовить рабочий и готовый к употреблению LEMP-стек.

![alt LEMP-stack][image-001]

Ну, во-первых, давайте раберемся, что подразумевется под понятием **LEMP-стек**. Все вы наверное знаете термин **[LAMP-стек (Linux Apache MySQL PHP)](http://ru.wikipedia.org/wiki/LAMP)**. LEMP-стек это тоже самое только вместо web-сервера **[Apache](http://ru.wikipedia.org/wiki/Apache)** использется **[Nginx](http://nginx.org/ru/)**.


## Ингридиенты

Для поднятия LEMP-стека нам понадобится:
* Выделенный сервер (я использую сервер в облаке от **[rackspace.com](http://www.rackspace.com/)** - это очень удобный сервис облачного хостинга позволяет накатывать различные дистрибутивы из образов за считанные минуты нажатием всего одной кнопки "Rebuild"...)
* Дистрибутив Linux (в данном варианте я использую дистрибутив **[Ubuntu 12.04LTS - precise](http://ubuntu.ru/get)**)
* **[Chef-server](http://wiki.opscode.com/display/chef/About+Opscode+Chef)** - cреда автоматизированного развертывания окружений. Необходимо будет зарегистрировать бесплатный аккаунт на сейте **[opscode.com](http://www.opscode.com/hosted-chef/)**, чтобы получить возможность управлять **бесплатно!!!** до 5 нодами (серверами). Чего нам более чем достаточно для экспериментов =)
* Набор необходимых рецептов _([chef cookbooks](http://wiki.opscode.com/display/chef/Cookbooks))_ для приготовления LEMP-стека (их вы найдете в моем [репозитарии](https://github.com/uran1980/lemp-stack-in-5-minutes) к этой статье). Эти рецепты подобраны мной и проверены на работоспособность. Также при необходимости вы можете сами подобрать нужные рецепты на **[сайте Chef комюнити](http://community.opscode.com/)** или на просторах **[гитхаба](https://github.com/search?q=chef+cookbooks&ref=commandbar)**.

[наверх](#lemp-%D1%81%D1%82%D0%B5%D0%BA-%D0%B7%D0%B0-5-%D0%BC%D0%B8%D0%BD%D1%83%D1%82)


## Начальные приготовления
### Регистрация
Регистрируемся в облаке **[Rackspace Open Cloud](https://cart.rackspace.com/cloud)** или в любом другом VDS хостинге (выбираем по вкусу). Если вы будете регистрироваться на ракспейсе, как я, то выбирайте при регистрации тип **Cloud Account** как на рисунке, т.к. это аккаунт в отличае от типа **Managed Account** не подразумевает абонентской платы в 100$ в месяц за техническую поддержку, которая, как вы сами понимаете, нам нужна как собаке пятая нога =)

И еще, при регистрации указывайте ваши реальные данные (телефон, email, номер кредитки), т.к. вам втечение 15 минут позвонит аж из Америки менеджер и проверит указанную вами информацию (и естественно на английском...). После того как вы ему все поддтвердите он активирует ваш аккаунт. Это единственное неудобство которое придктся испытать...

В дальнейшем вы будете платить только за ресурсы которые вы используете. В зависомотси от конфигурации сервера это от 16$ и выше в месяц. Более подробно расценки смотрим **[здесь](http://www.rackspace.com/cloud/servers/pricing/)**.

![alt "Регистрация Cloud Account"][image-002]

[наверх](#lemp-%D1%81%D1%82%D0%B5%D0%BA-%D0%B7%D0%B0-5-%D0%BC%D0%B8%D0%BD%D1%83%D1%82)

### Установка нужного дистрибутива
Устанавливаем нужный образ дистрибутива Linux. В данном случае я использую ```Ubuntu 12.04LTS presice```, т.к. это стабильная ветка как раз для серверов с долгосрочной поддержкой (до 2017 года). Образ устанавливается за минуту!

В дальнейшем свои образы вы можете изменять и сохранять, а потом, при необходимости, накатывать из них систему заново, если в ходе экспериментов что-то пошло не так. Все опреции происходят очень быстро, почти за минуту у вас будет развернута чистая система, готовая к дальнейшим экспериментам =)

![alt "Ubuntu 12.04LTS presice"][image-003]

По окончании развертывания образа у вас будет IP-адрес вашего сервера и рутовский пароль для доступа к нему. Это все что нам необходимо для дальнейшей работы.

[наверх](#lemp-%D1%81%D1%82%D0%B5%D0%BA-%D0%B7%D0%B0-5-%D0%BC%D0%B8%D0%BD%D1%83%D1%82)


## Chef - или подготовка шеф повара
### Что такое Chef?
Если коротко, то **[Chef](http://wiki.opscode.com/display/chef/About+Opscode+Chef)** это опенсорсный фреймворк, разработанный на языке **[Ruby](http://ru.wikipedia.org/wiki/Ruby)**, специально для автоматизации развертывания различных окружений. Как заверяют разработчики: "Не важно насколько сложен ваш бизнес, **Chef** позволяет очень просто и быстро развернуть все необходимые сервера и приложения для его полноценной работы". Т.е. Chef может автоматически развернуть и настроить любое программное обеспечение на любой платформе, где доступен язык **[Ruby](http://ru.wikipedia.org/wiki/Ruby)** (а это **Linux/Unix** и **Windows** платформы).

Chef оперирует **[рецептами (cookbooks)](http://wiki.opscode.com/display/chef/Cookbooks)** и **[ролями (roles)](http://wiki.opscode.com/display/chef/Roles)** - наборами абстрактных определений, описывающих то, как должна быть построена необходимая нам инфраструктура и какие роли отведены ее компонентам. Т.е. мы в рецептах указываем, что хотим, на новом сервере создать определенных пользователей, с определенными правами, установить и настроить определенные приложения и сервисы и чтобы этот сервер выполнял определнную роль (к примеру, был LEMP-стеком) в нашей инфраструктуре. На основе этих рецептов Chef сам, в зависимости от опреционной системы, делает все необходимые действия, чтобы на выходе мы имели готовую к работе систему.

Теперь если к нам, например, поступает новый сервер все что необходимо - это сказать Chef'у какую роль должен выполнять этот сервер в нашей архитектуре и в зависимости от этого Chef сам все подготовит без дальнейшего нашего вмешательства...
В теории все выглядит великолепно, попробуем реализовать это на практике...

[наверх](#lemp-%D1%81%D1%82%D0%B5%D0%BA-%D0%B7%D0%B0-5-%D0%BC%D0%B8%D0%BD%D1%83%D1%82)


### Архитектура Chef
![alt "Архитектура Chef"][image-004]

Архитектура Chef состоит из **[центрального сервера (Chef-Server)](http://wiki.opscode.com/display/chef/Chef+Server)** и подчиненных ему **[клиентов (Chef-Client)](http://wiki.opscode.com/display/chef/Chef+Client)** - узлов **([nodes](http://wiki.opscode.com/display/chef/Nodes))**. С Chef-сервером мы будем работать через **[Web-интерфейс](https://manage.opscode.com/)**. Для чего далее нам необходимо будет зарегитсрироваться на сайте.

Одной из радновидностей Chef-клиентов являеются особые клиенты, обычно это администраторы, у которых установлен специальный инструмент командной строки - **[Knife (нож шеф-повара)](http://wiki.opscode.com/display/chef/Knife)**, он предназначен для создания **[рецептов](http://wiki.opscode.com/display/chef/Cookbooks)**, которые, в свою очередь, будут применятся на остальных подчиненных Chef-клиентах.

[наверх](#lemp-%D1%81%D1%82%D0%B5%D0%BA-%D0%B7%D0%B0-5-%D0%BC%D0%B8%D0%BD%D1%83%D1%82)


### Регистрация и настройка Chef-Server
Чтобы получить доступ к **[web-пенели Chef-сервера](https://manage.opscode.com/)** и бесплатно управлять пятью узлами, заходим по этому адресу: [http://www.opscode.com/hosted-chef/](http://www.opscode.com/hosted-chef/), нажимаем кнопку **Free Trial** и регистрируем бесплатный аккаунт. Если вам по каким-либо причинам будет не достаточно пяти узлов, то придется раскошелиться от 120$ в месяц за большее количество доступных для управления узлов.

Теперь когда мы зарегистрировались, нам необходимо для дальнейшей работы получить два приватных ключа. Я зарегистрировался под ником **uran1980**, у вас будет свой ник, поэтому дальше предполагается, что вместо моего ника будет подставляться ваш. 

Итак, нам нужно два приватных ключа:
* **uran1980.pem** - приватный ключ от публичного профиля с сайта Chef комюнити,
* **uran1980-validator.pem** - приватный ключ от организации, которую мы создадим далее (у меня название организации совпадает с моим ником)

Чтобы получить ключ от публичного профиля, заходим по адресу ```http://community.opscode.com/users/uran1980/user_key/new``` и нажимаем кнопку **Get a new key**. Скачиваем и сохраняем ключ.

![alt "Get a new key"][image-005]

Затем нажимем ссылку **[create an organization](https://manage.opscode.com/organizations/new)**. Заполняем все поля и выбираем бесплатный план для управления до пяти серверами (узлами).

![alt "Создание организации"][image-006]


TODO


[наверх](#lemp-%D1%81%D1%82%D0%B5%D0%BA-%D0%B7%D0%B0-5-%D0%BC%D0%B8%D0%BD%D1%83%D1%82)


### Настройка Chef-Knife (нож шеф-повара)
TODO

[наверх](#lemp-%D1%81%D1%82%D0%B5%D0%BA-%D0%B7%D0%B0-5-%D0%BC%D0%B8%D0%BD%D1%83%D1%82)


### Настройка Chef-Client
TODO

[наверх](#lemp-%D1%81%D1%82%D0%B5%D0%BA-%D0%B7%D0%B0-5-%D0%BC%D0%B8%D0%BD%D1%83%D1%82)


## Создание и применение рецептов
TODO

[наверх](#lemp-%D1%81%D1%82%D0%B5%D0%BA-%D0%B7%D0%B0-5-%D0%BC%D0%B8%D0%BD%D1%83%D1%82)


## Заключение
TODO

[наверх](#lemp-%D1%81%D1%82%D0%B5%D0%BA-%D0%B7%D0%B0-5-%D0%BC%D0%B8%D0%BD%D1%83%D1%82)


### Полезные ссылки

* **[Nginx+php-fpm+perl под Debian Squeeze](http://habrahabr.ru/post/164401/)** - очень полезная статья на хабре по правильной настройке LEMP-стека
* **[Rackspace Open Cloud](http://www.rackspace.com/)**
* **[wiki.opscode.com](http://wiki.opscode.com/display/chef/About+Opscode+Chef)**
* **[community.opscode.com](http://community.opscode.com/)**
* **[GitHub Chef cookbooks](https://github.com/search?q=chef+cookbooks&ref=commandbar)**
* **[Установка Ruby RVM (Ruby Version Manager) в Ubuntu 12.04](http://habrahabr.ru/sandbox/49699/)**
* **[Ruby Installer для Windows - самый простой способ установить Ruby под Windows](http://rubyinstaller.org/)**
* **[Установка Ruby on Rails на Windows с использованием Vagrant и VirtualBox](http://nashbridges.me/ruby-windows-bootstrap)**

[наверх](#lemp-%D1%81%D1%82%D0%B5%D0%BA-%D0%B7%D0%B0-5-%D0%BC%D0%B8%D0%BD%D1%83%D1%82)

[image-001]: https://raw.github.com/uran1980/lemp-stack-in-5-minutes/master/images/image-001.jpg "LEMP-стек за 5 минут"
[image-002]: https://raw.github.com/uran1980/lemp-stack-in-5-minutes/master/images/image-002.png "Регистрация на Rackspace Open Cloud"
[image-003]: https://raw.github.com/uran1980/lemp-stack-in-5-minutes/master/images/image-003.png "Развертывание образа дистрибутива Ubuntu 12.04LTS presice"
[image-004]: https://raw.github.com/uran1980/lemp-stack-in-5-minutes/master/images/chef-server-arch.png "Архитектура Chef"
[image-005]: https://raw.github.com/uran1980/lemp-stack-in-5-minutes/master/images/image-005.jpg "Получение приватного ключа от публичного профиля"
[image-006]: https://raw.github.com/uran1980/lemp-stack-in-5-minutes/master/images/images-006.png "Создание новой организации"

[placeholder]: https://raw.github.com/uran1980/lemp-stack-in-5-minutes/master/images/placeholder.png "placeholder"




