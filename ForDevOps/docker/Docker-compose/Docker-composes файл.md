[[Docker compose]]
Файл докер компоуз имеет расширение .yml или .json

# Команды для работы с Docker-compose

`docker-compose up` - Поднять контейнер
`docker-compose build`    - Пересобрать докерфайл


# Ключи верхнего уровня
### Версия файла докер компоуз

`version '3' ` 
###  `volumes`

### `services`
### `networks`



### Ключ `services` - определения сервисов, каждый из этих сервисов будет представлять отдельный контейнер

```.yml
version '3'
services:
  webbap                  # имя сервиса
    build:                # собирается из докерфайла
      context:            # где лежит докерфайл
      args:               # опциональные аргументы
        - VERSION=v2  
    ports:                # Порт может принимать массив из переодрессаций
     - "8081:3000"
    environment:          # параметр окружения
	 - NODE_ENV=production
```
