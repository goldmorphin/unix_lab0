
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
