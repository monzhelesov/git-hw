# Домашнее задание к занятию "Система мониторинга Zabbix" - Монжелесов Роман

### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

2. ![alt text]()

### Задание 1

![alt text](https://github.com/monzhelesov/git-hw/blob/main/Снимок%20экрана%202024-10-13%20в%2023.26.12.png)

* wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_7.0-2+ubuntu24.04_all.deb
* dpkg -i zabbix-release_7.0-2+ubuntu24.04_all.deb
* apt update
* apt install zabbix-server-pgsql zabbix-frontend-php php8.3-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent
* sudo -u postgres createuser --pwprompt zabbix
* sudo -u postgres createdb -O zabbix zabbix
* zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
* systemctl restart zabbix-server zabbix-agent apache2
* systemctl enable zabbix-server zabbix-agent apache2

### Задание 2

![alt text](https://github.com/monzhelesov/git-hw/blob/main/Снимок%20экрана%202024-10-14%20в%2000.06.27.png)

![alt text](https://github.com/monzhelesov/git-hw/blob/main/Снимок%20экрана%202024-10-14%20в%2000.06.52.png)

![alt text](https://github.com/monzhelesov/git-hw/blob/main/Снимок%20экрана%202024-10-14%20в%2000.08.33.png)

![alt text](https://github.com/monzhelesov/git-hw/blob/main/Снимок%20экрана%202024-10-14%20в%2000.10.14.png)

* wget https://repo.zabbix.com/zabbix/7.0/debian/pool/main/z/zabbix-release/zabbix-release_7.0-2+debian12_all.deb
* dpkg -i zabbix-release_7.0-2+debian12_all.deb
* apt update
* apt install zabbix-agent2 zabbix-agent2-plugin-*
* systemctl restart zabbix-agent2
* systemctl enable zabbix-agent2