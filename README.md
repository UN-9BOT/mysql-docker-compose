# Установка и подключение MySQL через docker-compose

**Поднимаем контейнер:**

```sh
docker-compose up -d
```

**Подключаемся к mysql shell для создания бд и юзера:**
```sh
docker exec -it mysql_db mysql -u root -p 
```
 

**Выполняем следующие команды:**

```sql
CREATE DATABASE mydatabase;
CREATE USER 'myuser'@'%' IDENTIFIED BY 'mypassword';
GRANT ALL PRIVILEGES ON mydatabase.* TO 'myuser'@'%';

FLUSH PRIVILEGES;

```


**выходим из шелла**:
```sh
exit
```
**Всё мы создали юзера myuser с паролем mypassword**

Для удобного подключения можете использовать любую IDE (DATAGRIP, Pycharm, VScode и т.д.)
Но я использую консольные утилиты.
</br>
**Например mycli**

**Вот как это делается на примере mycli:**
```sh
mycli mysql://myuser@localhost:8101/myfirstrb 
```

**Вводите пароль mypassword**

**Готово. Вы в интерактивном редакторе с подсветкой и autocompletition.**

К сожалению я так и не смог подключиться к mysql дб через visidata... (может кто-то знает, отпишите мне, буду благодарен)
