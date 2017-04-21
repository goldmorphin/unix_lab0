
## Пример выполнения нулевой (ознакомительной) лабораторной работы 


# Установка Git
Заходим на [сайт](https://git-scm.com/download/win) и выбираем нужную версию, скачиваем.
![1](/images/1.png)

После скачивания два раза нажимаем на установочный файл и производим процесс установки.
Порядок установки показан ниже:

  <details>
    <summary>Нажать, чтобы расскрыть</summary><p>
<!-- alternative placement of p shown above -->

![](/images/2.png)![](/images/3.png)![](/images/4.png)![](/images/5.png)![](/images/6.png)![](/images/7.png)![](/images/8.png)![](/images/9.png)![](/images/10.png)![](/images/11.png)![](/images/12.png)

  </p>
  </details>

# Установка docker-machine с помощью Git

Открываем консоль установленного Git и выполняем следующие команды:
>if [[ ! -d "$HOME/bin" ]]; then mkdir -p "$HOME/bin"; fi && \
  curl -L https://github.com/docker/machine/releases/download/v0.10.0/docker-machine-Windows-x86_64.exe > "$HOME/bin/docker-machine.exe" && \
  chmod +x "$HOME/bin/docker-machine.exe" 
  
После установки, командой
> docker-machine version

Проверяем корректность установки.
[](/images/13.png)
  <details>
    <summary>В скриншотах...</summary><p>
<!-- alternative placement of p shown above -->

![](/images/13.png)![](/images/14.png)![](/images/15.png)![](/images/16.png)

  </p>
  </details>
  
  
# Установка docker-client

Установка клиента docker проще, чем может показаться. Скачиваем [по ссылке](https://get.docker.com/builds/Windows/x86_64/docker-17.04.0-ce.zip) архив, распаковываем и копируем docker.exe в папку, куда была установлена docker-machine.
После этого выполняем команду
> chmod +x "$HOME/bin/docker.exe"

Которая позволит файлу выполнятся, установит права на выполнение если быть чуть более точным.
![](/images/17.png)


# Создание docker-machine

Для создания docker-machine выполните команду

> docker-machine create <НАЗВАНИЕ>

![](/images/18.png)

  <details>
    <summary>Процесс создания</summary><p>
<!-- alternative placement of p shown above -->

![](/images/19.png)![](/images/20.png)

  </p>
  </details>
  
  После создания, выполним команду
  
  > docker-machine ls
  
  Чтобы посмотреть список всех машиных, в том числе только что новосозданной
  
  [](/images/21.png)
  
  
# Управление docker-machine и подготовка среды

Полный список команд для управления docker-machine можно получить, написав в консоли

> docker-machine

Но наиболее часто используемые это:

>docker-machine create
*для создания машины*

>docker-machine start
*для запуска машины*

>docker-machine stop
*для остановки машины*

>docker-machine ls
*для просмотра всех существующих машин*

Сама docker-machine, что логично, не поддерживает команды docker, нам необходимо подключится "внутрь" её или с помощью ssh или настроив переменную среду, что более правильно. Для этого выполним команду

>  docker-machine env <ИМЯ МАШИНЫ>

На выходе получим

![](/images/22.png)

Читаем последние две строки и выполняем то, что от нас хотят

> eval $("C:\Users\Илья\bin\docker-machine.exe" env lab0)

![](/images/23.png)

После этого можно выполнить например команду

>docker

Чтобы убедится в корреткности наших действий.
![](/images/24.png)

# Создание контейнера

В качестве базового контейнера будем использовать vlavad/lab00
Выполняем команду
> docker run -d -t --privileged -h lxc21 --name lab0 vlavad/lab00

тем самым скачивая с репозитория на Docker Hub контейнер и запуская его.
После выполнения команды убедимся в том, что контейнер запущен
> docker ps
![](/images/25.png)
