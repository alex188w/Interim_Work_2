Задание 1
 
1)   Используйте команды операционной системы Linux и создайте две новых директории – «Игрушки для школьников» и «Игрушки для дошколят».
avc@avc-VirtualBox:~$ mkdir "Игрушки для школьников" "Игрушки для дошколят"

2)   Создайте в директории «Игрушки для школьников» текстовые файлы - «Роботы», «Конструктор», «Настольные игры».
avc@avc-VirtualBox:~$ mkdir "Игрушки для школьников" "Игрушки для дошколят"
avc@avc-VirtualBox:~$ cd "Игрушки для школьников"
avc@avc-VirtualBox:~/Игрушки для школьников$ touch "Роботы" "Конструктор" "Настольные игры"

3)    Создайте в директории «Игрушки для дошколят» текстовые файлы «Мягкие игрушки», «Куклы», «Машинки»
avc@avc-VirtualBox:~/Игрушки для школьников$ cd ../"Игрушки для дошколят"
avc@avc-VirtualBox:~/Игрушки для дошколят$ touch "Мягкие игрушки" "Куклы" "Машинки"

4)   Объединить 2 директории в одну «Имя Игрушки»
avc@avc-VirtualBox:~/Игрушки для дошколят$ cd ..
avc@avc-VirtualBox:~$ mv "Игрушки для дошколят" "Имя Игрушки"
avc@avc-VirtualBox:~$ mv "Игрушки для школьников"/* "Имя Игрушки"
avc@avc-VirtualBox:~$ rm -r "Игрушки для школьников"

5)   Переименовать директорию «Имя Игрушки» в «Игрушки»
avc@avc-VirtualBox:~$ mv "Имя Игрушки" "Игрушки"

6)   Просмотреть содержимое каталога «Игрушки».
итого 8
drwxrwxr-x  2 avc avc 4096 мар  8 13:35  .
drwxr-x--- 32 avc avc 4096 мар  8 13:36  ..
-rw-rw-r--  1 avc avc    0 мар  8 13:31  Конструктор
-rw-rw-r--  1 avc avc    0 мар  8 13:33  Куклы
-rw-rw-r--  1 avc avc    0 мар  8 13:33  Машинки
-rw-rw-r--  1 avc avc    0 мар  8 13:33 'Мягкие игрушки'
-rw-rw-r--  1 avc avc    0 мар  8 13:31 'Настольные игры'
-rw-rw-r--  1 avc avc    0 мар  8 13:31  Роботы

7)   Установить и удалить snap-пакет. (Любой, какой хотите)
avc@avc-VirtualBox:~$ snap search vlc
Название         Версия                  Издатель    Примечание  Описание
vlc              3.0.18                  videolan✓   -           The ultimate media player

avc@avc-VirtualBox:~$ sudo snap install vlc
[sudo] пароль для avc:
vlc 3.0.18 от VideoLAN✓ установлен

8)   Добавить произвольную задачу для выполнения каждые 3 минуты (Например, запись в текстовый файл чего-то или копирование из каталога А в каталог Б).
avc@avc-VirtualBox:~$ crontab -e
MAILTO="" 
*/3 * * * * tar -zcf /var/backups/home.tgz /home/
	Сохраняем, выходим. Проверяем:
avc@avc-VirtualBox:~$ grep CRON /var/log/syslog
Mar  8 14:00:01 avc-VirtualBox CRON[4111]: (avc) CMD (tar -zcf /var/backups/home.tgz /home/)
Mar  8 14:03:01 avc-VirtualBox CRON[4115]: (avc) CMD (tar -zcf /var/backups/home.tgz /home/)
