LEMP-стек за 5 минут
====================
![alt LEMP-stack][image-001]

Всем привет! В этой сатье я расскажу как за пять минут приготовить рабочий и готовый к употреблению LEMP-стек. 

Ну, во-первых, давайте раберемся, что подразумевется под понятием **LEMP-стек**. Все вы наверное знаете термин **[LAMP-стек (Linux Apache MySQL PHP)](http://ru.wikipedia.org/wiki/LAMP)**. LEMP-стек это тоже самое только вместо web-сервера **[Apache](http://ru.wikipedia.org/wiki/Apache)** использется **[Nginx](http://nginx.org/ru/)**.


## Ингридиенты

Для поднятия LEMP-стека нам понадобится:
* Выделенные сервер (я использую сервер в облаке от **[rackspace.com](http://www.rackspace.com/)** - это очень удобный сервис облачного хостинга позволяет накатывать различные дистрибутивы из образов за считанные минуты нажатием всего одной кнопки "Rebuild"...)
* Дистрибутив Linux (в данном варианте я использую дистрибутив **[Ubuntu 12.04LTS - precise](http://ubuntu.ru/get)**)
* **[Chef-server](http://wiki.opscode.com/display/chef/About+Opscode+Chef)** - cреда автоматизированного развертывания окружений. Необходимо будет зарегистрировать бесплатный аккаунт на сейте **[opscode.com](http://www.opscode.com/hosted-chef/)**, чтобы получить возможность управлять **бесплатно!!!** до 5 нодами (серверами). Чего нам более чем достаточно для экспериментов =)
* Набор необходимых рецептов _([chef cookbooks](http://wiki.opscode.com/display/chef/Cookbooks))_ для приготовления LEMP-стека (их вы найдете в моем [репозитарии](https://github.com/uran1980/lemp-stack-in-5-minutes) к этой статье). Эти рецепты подобраны мной и проверены на работоспособность. Также при необходимости вы можете сами подобрать нужные рецепты на **[сайте Chef комюнити](http://community.opscode.com/)** или на просторах **[гитхаба](https://github.com/search?q=chef+cookbooks&ref=commandbar)**.


## Начальные приготовления
### Регистрация
Регистрируемся в облаке **[Rackspace Open Cloud](https://cart.rackspace.com/cloud)** или в любом другом VDS хостинге (выбираем по вкусу). Если вы будете регистрироваться на ракспейсе, как я, то выбирайте при регистрации тип **Cloud Account** как на рисунке, т.к. это аккаунт в отличае от типа **Managed Account** не подразумевает абонентской платы в 100$ в месяц за техническую поддержку, которая нам как вы сами понимаете как собаке пятая нога =)

![alt "Регистрация Cloud Account"][image-002]


### Установка нужного дистрибутива
Устанавливаем нужный образ дистрибутива Linux. В данном случае я использую ```Ubuntu 12.04LTS presice```, т.к. это стабильная ветка как раз для серверов с долгосрочной поддержкой (до 2017 года). Образ устанавливается за минуту!

В дальнейшем свои образы вы можете изменять и сохранять, а потом, при необходимости, накатывать из них систему заново, если в ходе экспериментов что-то пошло не так. Все опреции происходят очень быстро, почти за минуту у вас будет развернута чистая система, готовая к дальнейшим экспериментам =)

![alt "Ubuntu 12.04LTS presice"][image-003]


## Настройка сервера

TODO


## Заключение

TODO


### Полезные ссылки

* **[Rackspace Open Cloud](http://www.rackspace.com/)**
* **[wiki.opscode.com](http://wiki.opscode.com/display/chef/About+Opscode+Chef)**
* **[community.opscode.com](http://community.opscode.com/)**
* **[GitHub Chef cookbooks](https://github.com/search?q=chef+cookbooks&ref=commandbar)**
* **[Nginx+php-fpm+perl под Debian Squeeze](http://habrahabr.ru/post/164401/)** - очень полезная статья на хабре по правильной настройке LEMP-стека

[image-001]: https://raw.github.com/uran1980/lemp-stack-in-5-minutes/master/images/image-001.jpg "LEMP-стек за 5 минут"
[image-002]: https://raw.github.com/uran1980/lemp-stack-in-5-minutes/master/images/image-002.png "Регистрация на Rackspace Open Cloud"
[image-003]: https://raw.github.com/uran1980/lemp-stack-in-5-minutes/master/images/image-003.png "Развертывание образа дистрибутива Ubuntu 12.04LTS presice"

[placeholder]: https://raw.github.com/uran1980/lemp-stack-in-5-minutes/master/images/placeholder.png "placeholder"




