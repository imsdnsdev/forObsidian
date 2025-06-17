

# #!/bin/bash - обязательная строка

`bash bash.sh` - Чтобы выполнить




# Создание переменной
`number=9`

`comand=`ls` -Загнал в переменную команду, все делается благодаря косым ковычкам


echo "$number $comand" -Все переменные выводятся благодаря знаку $

# *Ввод данных из консоли*
`input=$1` -Ввод данных из консоли
`read -p "Введите число":num` - Тоже прием данных из консоли



### *Но чтобы вывести с данными из инпут, нужно после вызова прописать данные которые вводим*





res=$((a+b)) - Синтаксис сложения



# **Создание условия

if ["$num" == 5]; then
	ls
elif ["$num" > 10]; then
	echo "number is bigger than ten"
else 
	read -p "Enter your Name":name
	echo "$name"
fi

# Bash шпаргалка для DevOps

## 1. Основы

```bash
# Переменная
name="DevOps"
echo "Hello, $name"
```

## 2. Условия if

```
if [ "$a" -lt "$b" ]; then   
	echo "$a меньше $b" 
else   
	echo "$a не меньше $b" 
fi`
```

## 3. Циклы

# for

```
for file in *.txt; do   
	echo "Обрабатываю $file" 
done
```

# while

```
while true; do   
	read input   
	
	if [ "$input" == "exit" ]; then     
	
		break   
	
	fi 

done
```

## 4. Функции

```
say_hello() {   
echo "Привет, $1!" 
} 
say_hello "Мир"
```

## 5. Работа с файлами и текстом

```

grep "ERROR" logfile.txt       # Поиск строк с ERROR 
head logfile.txt               # Первые 10 строк файла 
sed 's/error/ERROR/g' logfile.txt  # Заменить error на ERROR`
```

## 6. Перенаправления и пайпы

```
ls > files.txt                 # Перенаправить вывод в файл 
echo "Новая строка" >> files.txt # Добавить в конец файла 
cat logfile.txt | grep "ERROR"  # Пайп: вывод одной команды на вход другой`
```

## 7. Работа с процессами

```
sleep 60 &                    # Запустить в фоне 
ps aux | grep sleep           # Найти процессы 
sleep kill 12345                   # Убить процесс по PID`
```

## 8. Системные утилиты

```
systemctl status nginx        # Проверить статус сервиса nginx 
journalctl -u nginx.service   # Просмотреть логи nginx
```

## 9. Автоматизация с cron

```
crontab -e                    # Редактировать расписание cron  
# Запуск скрипта каждый час: 
0 * * * * /path/to/script.s
```

## 10. Переменные окружения
```
echo $PATH                  # Показать PATH 
export PATH=$PATH:/custom    # Добавить путь в PATH
```

## 11. Обработка аргументов

```
while getopts "u:p:" opt; do   
	case $opt in     
		u) user=$OPTARG ;;     
		p) pass=$OPTARG ;;   
	esac 
done  
echo "User: $user" 
echo "Pass: $pass"
```

## 12. Отладка

```
bash -x script.sh            # Запуск с выводом команд 
set -e                       # Выход при ошибке
```

## 13. Работа с удалёнными серверами



```
ssh user@host "uptime"       # Выполнить команду по SSH 
scp file.txt user@host:/tmp/ # Копировать файл на сервер
```

