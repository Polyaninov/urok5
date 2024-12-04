
    1. Установить mongodb
    
    2. Выяснить, где находится директория с данными командой grep -i dbPath /etc/mongod.conf
       pmn@pmn-VirtualBox:~$ grep -i dbPath /etc/mongod.conf
       dbPath: /var/lib/mongodb

    
    3. Подключить еще один дополнительный диск к ВМ

    
    4. Сделать из нового диска PV, из PV - VG

pmn@pmn-VirtualBox:~$ sudo pvcreate /dev/sdb
  Physical volume "/dev/sdb" successfully created
  
pmn@pmn-VirtualBox:~$ sudo vgcreate vg01 /dev/sdb
  Volume group "vg01" successfully created
  
    
    5 .Создать Logical Volume mongo-data и вынести директорию из п6 на него
    6 .Убедиться, что все прошло корректно (сервис mongodb запущен, можно подключиться к БД)

