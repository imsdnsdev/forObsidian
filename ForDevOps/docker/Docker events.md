
`docker events --since время - покажет события в докере в течении определенного времени

#### `docker events --filter type=<имя фильтра>` - с помощью этой команды можно фильтровать объекты, например задать фильтр container
### Также есть возможность фильтровать по `events`

`docker events --filter type=contaier --filter event=start`