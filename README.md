# Контент Доки

Дока — это место, в котором мы с огоньком перекапываем документацию по веб-разработке. Наша цель сделать ее практичной, понятной и не унылой.

Этот репозиторий содержит только тексты статей и материалов проекта «[Дока](y-doka.site/)». Статьи попадают на сайт через платформу, которая живет в [отдельном репозитории](github.com/y-Doka/platform).


## Как работать

Статья в Доке — это Markdown-файл. Чтобы написать статью, нужно:
1. создать новую папку с названием статьи 
1. скопировать шаблон в папку и переименовать его в `index.md`
1. писать статью
1. дополнительные материалы: картинки, демки, видео сохранять в ту же папку

🤝 Всё, что хорошо выглядит в маркдауне, будет хорошо выглядеть на сайте.


## Предпросмотр статьи

Иногда стандартного предпросмотра маркдауна недостаточно и нужно посмотреть на статью в оформлении сайта. 

Мы сделали такой предпросмотр удобным. Посмотрите [видеоинструкцию](https://www.loom.com/share/150f5c7124c94ce497fc49fb8596a013) или выполните команды:

1. установите [Docker Desktop](https://www.docker.com/products/docker-desktop)
1. откройте консоль и перейдите в папку с контентом
1. выполните команду `docker-compose pull && docker-compose up`
1. дождитесь, когда в консоли появится заголовок `Access URLs`
1. перейдите по адресу [localhost:8080/](localhost:8080/) на вашу локальную копию сайта

🧨 Вы можете редактировать статью и видеть все изменения вживую — достаточно обновить страницу.

Чтобы выключить локальную копию сайта, нажмите CTRL+C в консоли, где выполняли команду.

