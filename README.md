# ansible3

Вот все задание, которое нам дали:
---
   1. На серверах web1, web2 установить Nginx.
2. На серверах haproxy1, haproxy2 установить и настроить  отказоустойчивую связку HAProxy+Keepalived. Настроить VIP с помощью Keepalived в соответствии со схемой
3. На серверах web1, web2 Nginx должен работать по порту 8080 и отдавать кастомную страницу, зайдя на которую можно понять на каком сервере вы находитесь.
4. На серверах с HAProxy ПО должно обеспечить балансировку нагрузки серверов web1 и web2 в режиме round-robin. Сделать таймауты ожидания ответа web1 и web2 как можно меньше. Скажем, 1-2 секунды
5. Установка и настройка всего ПО должна быть обеспечена Ansible-сценарием.
6. Все файлы по этому заданию выложить в Github и написать ReadMe со скринами работоспособности и инструкцию по запуску вашего Ansible-сценария.

Вот че надо сделать в этой штуке:
---
Скопировать репу
Потом зайти через терминал в папку, которую скопировали.
Открываем Vagrantfile.
Меняем 46ую строчку `ssh_pub_key = File.readlines("/home/alex/.ssh/id_rsa.pub").first.strip` - Надо указать тут свой путь до ключа.

Пишем в консольке `vagrant up`, чтобы подднять виртуалки.
Если ничего не получилось - пошел ты отсюда, неуч
Далее, прописываем в консольке `ansible-playbook nginx.yml`
ждем
ждем
ждем
и еще раз ждем

Если вы все сделали правильно, по ip Vip: 192.168.11.110, у вас должна появиться кастомная страничка:

![](https://github.com/ismailtez/ansible3/blob/main/web1.jpg)

При нажатии Ctrl+Shift+r, у вас обновится страничка с web1 на web2:

![](https://github.com/AlexanderPodprugin/ansible3/blob/main/web2.jpg)
