в общем то  я нашла в интернете уже готовый html файл в котором уже использовался  js

затем создала dockerfile и отредактировала его с помощью этих команд:

FROM nginx

COPY js.html /usr/share/nginx/html

COPY style.css /usr/share/nginx/html

COPY script.js /usr/share/nginx/html

затем я создала docker образ:

docker build -t js

Через "docker desktop" проверила рабочий ли контейнер

и ввела запуск образа 
docker run -itd -p 8011:80 --name nginx-dock localhost:5000/nginx:0.0.
