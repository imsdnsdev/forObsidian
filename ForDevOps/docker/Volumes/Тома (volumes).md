Тома используются если необходимо постоянное хранение данных



`docker volume ls`  - Посмотреть все созданные тома
`docker volume create <Имя тома>`   - Создание тома 
`docker volume inspect <Имя тома>`  -Исследовать том


## Точка монтирования
![[Pasted image 20250619235836.png]]



## Удаление томов
`docker volume rm`
`docker volume prune`

# Bind mounts

[[Работа с томами для управления постоянными данными]]
## Это монтирование каталогов в контейнер
```
docker container run -d \ 
--name nginx-bind-mount1 \ 
--mount type=bind,source="$(pwd)"/target,target=/app \ 
nginx
```

###  Тут `mount` задает образ монтирования, `source` что монтируем, `target` куда монтируем;  это тоже самое что и 

`-v <что монтируем>:<куда монтируем>`  -Вмонтирровать в контейнер по принципу <источник>:<цель>



