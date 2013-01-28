LEMP-стек за 5 минут
====================

Всем привет! В этой сатье я расскажу как за пять минут приготовить рабочий и готовый к употреблению LEMP-стек. 

Ну, во-первых, давайте раберемся, что подразумевется под понятием **LEMP-стек**. Все вы наверное знаете термин **[LAMP-стек (Linux Apache MySQL PHP)](http://ru.wikipedia.org/wiki/LAMP)**. LEMP-стек это тоже самое только вместо web-сервера **[Apache](http://ru.wikipedia.org/wiki/Apache)** использется **[Nginx](http://nginx.org/ru/)**.


## Ингридиенты

Для поднятия LEMP-стека нам понадобится:
* Выделенные сервер (я использую сервер в облаке от **[rackspace.com](http://www.rackspace.com/)**)
* Дистрибутив Linux (в данном варианте я использую дистрибутив **[Ubuntu 12.04LTS - precise](http://ubuntu.ru/get)**)
* **[Chef-server](http://wiki.opscode.com/display/chef/About+Opscode+Chef)** - cреда автоматизированного развертывания окружений. Необходимо будет зарегистрировать бесплатный аккаунт на сейте **[opscode.com](http://www.opscode.com/hosted-chef/)**, чтобы получить возможность управлять **бесплатно!!!** до 5 нодами (серверами). Чего нам более чем достаточно для экспериментов =)
* Набор необходимых рецептов _(chef cookbooks)_ для приготовления LEMP-стека (их вы найдете в моем репозитарии к этой статье). Эти рецепты подобраны мной и проверены на работоспособность. Также при необходимости вы можете сами подобрать нужные рецепты на **[сайте Chef комюнити](http://community.opscode.com/)** или на просторах **[гитхаба](https://github.com/search?q=chef+cookbooks&ref=commandbar)**.


## Начальные приготовления

TODO


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




