# Installation of selenoid for mac

создаем папочку под конфиги (она будет отзеркаливаться в контейнер)
mkdir ~/etc/selenoid создаем папочку под конфиги 

Странный изврат для получения конфига браузеров (генерим конфигурационный файл)
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock aerokube/cm:1.0.0 selenoid \   --last-versions 2 --tmpfs 128 --pull > ~/etc/selenoid/browsers.json

Описание конфига браузеров
https://aerokube.com/selenoid/latest/

Запускаем селеноид
docker run -d --name selenoid -p 4444:4444 -v ~/etc/selenoid:/etc/selenoid:ro -v /var/run/docker.sock:/var/run/docker.sock aerokube/selenoid

Запускаем графическую морду, она в другом контейнере
docker run -d --name selenoid-ui -p 8080:8080 aerokube/selenoid-ui
