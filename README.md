# bash-po-golove
2kab para

nano script.sh //  create file
chmod +x script.sh // sdelaet ispolnyaemim
/script.sh //  launch

#!/bin/bash // первая строка любого скрипта
mysql -u root -p'root' -e// авторизуемся с пользователя
"CREATE DATABASE USER_DB;"   // создадим базу данных
mysql -u root -p'root' -e " USE USER_DB; // выбираем базу данных
CREATE TABLE USERS (ID INT AUTO_INCREMENT PRIMARY KEY, NAME VARCHAR(255), PASSWORD VARCHAR(255));" // создаем таблицу для юзеров

for i in {1..10};
do 
username="user_$i" // создаем пользователетей user1, user2,...
bdname="base_$i" // создает базы 
password=$(openssl rand -base64 10) // создает радомный пароль

mysql -u root -p'root' -e
"CREATE USER $username@localhost IDENTIFIED BY $password"; // создаем пользователей

mysql -u root -p'root' -e
"USE USER_DB;
INSERT INTO USERS(NAME, PASSWORD) VALUES ('$USERNAME', '$PASSWORD');"

mysql -u root -p'root' -e
"CREATE DATABASE $USER_DB;
GRANT ALL PRIVELEGES ON $USER_DB.*TO $username@localhost"
