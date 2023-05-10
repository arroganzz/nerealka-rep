В этой лабораторной работе мне нужно было определить точку монтирования Volume внутри контейнера

затем внести изменения в Dockerfile, где я добавила команду VOLUME, которая указывает точку монтирования для VOLUME: VOLUME /app

далее собрала образ Docker, используя уже измененный Dockerfile

Ввела: docker build -t nginx-dock

Создала volume используя следющую команду: docker volume create storage

index.html доступен по пути /app/index.html

далее копирую данные index.html внутрь volume с помощью нереальной команды:

docker run -v storage:/app -v /Users/Win10Pro/desktop/lab5:/data --rm alpine sh -c "cp /data/index.html /app/"

Я использовала образ alpine для контейнера и команды sh -c для выполнения команд которые будут происходить непосредственно внутри контейнера

Теперь мне нужно проверить, что index.html подгрузился внутрь Volume, запустив временный конейнер, образ которого я использовала выше и проверила наличие файла docker run -v storage:/app --rm alpine sh -c "ls /app"

Файл index.html отображается в выводе команды, хначит что он подгружен
