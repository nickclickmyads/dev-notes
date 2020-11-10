# Applications for Amazon Workspaces Linux 2

## Docker ([источник](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/docker-basics.html))

    sudo amazon-linux-extras install docker
    sudo service docker start
    sudo usermod -a -G docker ec2-user

После выполнения нужно перелогиниться из Amazon Workspaces, после чего можно проверить результат

    docker info

Для определения адресов доменных имен внутри контейнеров необходимо добавить адреса Google DNS

    echo '{"dns":["8.8.8.8","8.8.4.4"]}' | sudo tee /etc/docker/daemon.json
    sudo systemctl restart docker

## Docker Compose ([источник](https://docs.docker.com/compose/install/))

    sudo curl -L "https://github.com/docker/compose/releases/download/1.23.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
    sudo chmod +x /usr/local/bin/docker-compose

## Google Chrome
    curl https://intoli.com/install-google-chrome.sh | bash

## Visual Studio Code ([источник](https://code.visualstudio.com/docs/setup/linux))

    sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
    sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'
    yum check-update
    sudo yum install code

## DBeaver

Скачать RPM-пакет последней версии по [ссылке](https://dbeaver.io/download/) и установить

    sudo rpm -i <имя-rpm-пакета>

## PHP

    sudo amazon-linux-extras install php7.2
