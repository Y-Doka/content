# Предпросмотр статьи

Иногда стандартного предпросмотра маркдауна недостаточно, и нужно посмотреть на статью в оформлении сайта.

Мы сделали такой предпросмотр удобным. Посмотрите [видеоинструкцию](https://www.loom.com/share/150f5c7124c94ce497fc49fb8596a013) или выполните команды:

1. установите
    - на компьютер Windows или Mac (intel) [Docker Desktop](https://www.docker.com/products/docker-desktop)
    - на Mac (M1) [Docker Desktop (beta)](https://docs.docker.com/docker-for-mac/apple-m1/)
    - на Ubuntu Linux [Docker Engine](https://docs.docker.com/engine/install/ubuntu/)
        - на других Lunux-дистрибутивах не тестировалось, но [искать их тут](https://docs.docker.com/engine/install/)
        - на всех Linux-дистрибутивах, чтобы Docker не требовал прав супер-пользователя, его необходимо добавить в группу с правами после установки ([инструкция](https://docs.docker.com/engine/install/linux-postinstall/)).
1. откройте консоль и перейдите в папку с контентом
1. выполните команду `./start.sh` на Mac или Linux, либо `bash -c "./start.sh"` на Windows
1. дождитесь, когда в консоли появится заголовок `Access URLs`
1. перейдите по адресу [http://localhost:8080](http://localhost:8080) на вашу локальную копию сайта

🧨 Вы можете редактировать статью и видеть все изменения вживую — достаточно обновить страницу.

Чтобы выключить локальную копию сайта, нажмите CTRL+C в консоли, где выполняли команду.
