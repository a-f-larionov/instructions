# Instructions

### Устанавливаем WSL 2 для Windows

[Инстуркиця от MS, если что то пошло не так](https://docs.microsoft.com/en-us/windows/wsl/install)

Убедимся, что у нас WSL 2(WSL 1 не является полноценной Linux, не будет работать)

Проверяем версию WSL
```cmd
wsl -l -v

    NAME    STATE       VERSION
* Ubuntu    Running           1
```

Если VERSION 1:

Установка по умолчанию WSL2
```cmd
wsl --set-default-version 2
```

Смотрим какие есть дистрибутивы
```cmd
wsl --list --online 
```
Устанавливаем новую Ubuntu
```cmd
wsl --install -d Ubuntu-20.04
```
Устанавливаем по умолчанию wsl:
```cmd
wsl --set-default Ubuntu-20.04
```


Старую версию(WSL 1) можно удалить
```cmd
wsl --unregister Ubuntu
```

### 2. Выполняем инструкцию

https://about.gitlab.com/install/#ubuntu



#### Install Docker

<a href="https://docs.docker.com/engine/install/">Instruction to install Docker</a><br>
<a href="https://docs.docker.com/engine/install/ubuntu/">Install on Ubuntu</a><br>
<a href="https://www.docker.com/products/docker-desktop">Install on Windows</a>



#### Create SSL keys (self signed certificate) (for M3 Project\nginx)

Move private and public key to /var/m3-test/m3-compose/keys/self-signed/
For windows use PuTTY Key Generator

    linux:
    openssl req -x509 -outform PEM -sha256 -nodes -days 365 -newkey rsa:2048 -keyout priv.key -out cert.pem



##### Or Install Certbot

    According documentations
    https://certbot.eff.org
