“Київський фаховий коледж зв’язку”  
Циклова комісія Комп’ютерної інженерії

## ЗВІТ ПО ВИКОНАННЮ
## ЛАБОРАТОРНОЇ РОБОТИ №9
>з дисципліни:  
>«Операційні системи»

>**Тема:** 
>захист системи та користувачів у Linux. Створення користувачів та груп

>**Виконали студенти групи РПЗ-03**  
>**Команда 2:**
>- Кушанов Р.Г.
>- Путін М.Г.
>- Штома Д.О.

>**Перевірив викладач**  
>Сушанова В.С.

>**Мета роботи**:
>1. Отримання практичних навиків роботи з командною оболонкою Bash.
>2. Знайомство з базовими структурами для збереження системних даних - процеси, память, лог-файли та повідомлення про стан ядра.
>3. Знайомство зі стандартом FHS.
>4. Знайомство з діями при налаштуванні мережі

>**Матеріальне забезпечення занять**
>1. ЕОМ типу IBM PC.
>2. ОС сімейства Windows (Windows 7).
>3. Віртуальна машина – Virtual Box (Oracle).
>4. Операційна система GNU/Linux – CentOS.4. 


***

### Завдання для попередньої підготовки.
1. Прочитайте короткі теоретичні відомості до лабораторної роботи та зробіть невеликий словник базових англійських термінів з питань призначення команд та їх параметрів.
 
>Готував студент Кушанов Р.Г.

| Термін англійською | Термін українською |
|:-------------------|-------------------:|
|requires            |             вимагає|
|allows              |            дозволяє|
|perform             |          виконувати|
|separated           |           розділені|
|primary             |           первинний|
|supplemental        |          додатковий|
|switching           |         перемикання|
|distributions       |           розподіли|
|collaborate         |       співпрацювати|
|access              |              доступ|

2. Дайте відповіді на наступні питання: 

>Готував студент Кушанов Р.Г.

  - Розкрийте поняття UPG, коли їх доцільно використовувати?

    UPG (User Private Group) is used in Unix/Linux-based operating systems to organize user access rights to files and directories. Each user has a unique User ID (UID), and UPG allows you to create groups of users with a separate Group ID (GID), which can have their own access rights to files and directories. It is appropriate to use UPG when you need to provide shared access to files and directories for a certain group of users who must have the same access rights to these files.

  - Якими командами можна створити групи користувачів? Наведіть приклади
    
    `groupadd`: `sudo groupadd developers`

    `usermod`: `sudo usermod -aG developers john`
    
  - Якими командами можна змінити налаштування груп користувачів? Наведіть приклади
    
    `groupmod`: `sudo groupmod -n newname oldname`
    `chgrp`: `sudo chgrp groupname file.txt`
    `gpasswd`: `sudo gpasswd -p newpass groupname`

### Хід роботи

1. Опрацюйте всі приклади команд, що представлені у лабораторних роботах курсу NDG Linux Essentials - Lab 15: System and User Security та Lab 16: Creating Users and Groups.

>Готував студент Путін М.Г.

|  Назва команди  |  Її призначення та функціональність  |
|:----------------|-------------------------------------:|
|`su`| used to switch users and start a new shell as root user |
|`sudo`|used to execute a single command as the root user by prefixing that command |
|`exit`| used to logout of root user |
|`head /etc/passwd` | shows detailed information about users, including encrypted password and password policy |
|`getent passwd username`| used to retrieve the account information for a user |
|`w`| used to get a more detailed view of the users who are currently on your system |
|`last`| used to display all logins and reboot records |
|`groupadd`| used to create a new group |
|`groupmod`| used to make changes to groups |
|`useradd`| used to create a new user |
|`passwd`| used to set and reset a user's password |
|`usermod`| used to make changes to the user account |
|`groupdel`| used to delete either of the groups, as long as neither of them have been made the primary group for a user |
|`getent group *groupname*`| used to retrieve to retrieve information about the group |
|`userdel`| used to delete a user account |




2. Виконайте практичні завдання у терміналі:

>Готував студент Штома Д.О.

  - виведіть інформацію про поточного користувача різними способами (підказка використовуйте
  команди id та grep);
  
      id
      whoami
      id -un
      grep "^$(whoami):" /etc/passwd
  
  - попрактикуйте в терміналі команди last, w та who. Порівняйте результати виводу кожної команди,
  які деталі відсутні в кожній із команд порівняно з іншими?
  
      last
      w
      who
      
    Команда last показує історію входів користувачів, w показує поточних користувачів та їхню активність, а who просто відображає поточних користувачів.
  
  - створіть дві нові групи користувачів - super_admins, noob_users та good_students, визначте їх
  ідентифікатори;
  
     sudo groupadd super_admins
     sudo groupadd noob_users
     sudo groupadd good_students

     grep "super_admins" /etc/group
     grep "noob_users" /etc/group
     grep "good_students" /etc/group

  
  
  - для кожного члену Вашої команди за допомогою терміналу створіть нового користувача (якщо
  працюєте самі, то просто трьох довільних користувачів), не забудьте після створення нового
  користувача одразу задати йому пароль;
  
     sudo useradd user1
     sudo passwd user1

     sudo useradd user2
     sudo passwd user2

     sudo useradd user3
     sudo passwd user3

  
  - додайте нових користувачів у створені Вами нові групи таким чином, щоб у групах super_admins та
  noob_users було по 2 користувачі, один з яких є в обох групах, у групу good_students додайте всіх
  трьох користувачів;
  
     sudo usermod -aG super_admins user1
     sudo usermod -aG noob_users user1

     sudo usermod -aG super_admins user2
     sudo usermod -aG noob_users user3

     sudo usermod -aG good_students user1
     sudo usermod -aG good_students user2
     sudo usermod -aG good_students user3

  
  
  - перегляньте інформацію про групи, та які користувачі до них входять, поясніть що ви бачите;
  
     grep "super_admins" /etc/group
     grep "noob_users" /etc/group
     grep "good_students" /etc/group

  
  - видаліть першого створеного вами користувача, перегляньте чи залишиться інформація про нього в
  групах, де він перебував;
 
     sudo userdel user1

     grep "super_admins" /etc/group
     grep "noob_users" /etc/group
     grep "good_students" /etc/group


 
  - видаліть другого користувача, перегляньте чи залишиться інформація про нього в групах, де він
  перебував;
  
     sudo userdel user2

     grep "super_admins" /etc/group
     grep "noob_users" /etc/group
     grep "good_students" /etc/group



  
  - видаліть третього користувача, перегляньте чи залишиться інформація про нього в групах, де він
  перебував;
  
     sudo userdel user3

     grep "super_admins" /etc/group
     grep "noob_users" /etc/group
     grep "good_students" /etc/group

  
  - перегляньте інформацію про існуючі групи користувачів;
 
    cat /etc/group

 
  - видаліть створені Вами групи користувачів;
  
    sudo groupdel super_admins
    sudo groupdel noob_users
    sudo groupdel good_students

  
  
  - перегляньте інформацію про існуючі групи користувачів.
  
       cat /etc/group


### Контрольні запитання

>Готував студент Кушанов Р.Г.

1. Чому в конфігураційних файлах паролі не зберігається в явному вигляді?

   Passwords are usually not stored explicitly in configuration files for security reasons. If the password is stored in explicit form, it can be seen by anyone who has access to this file. Therefore, hash functions are usually used to store passwords, which are used to compare with the password entered by the user.

2. Чому не рекомендується виконувати повсякденні операції, використовуючи обліковий запис root?

   The root account has the highest privileges on the system and can perform any action. Using the root account for day-to-day operations exposes the user to the risk of executing incorrect commands, which may result in data loss or system failure. Therefore, it is recommended to use limited accounts for day-to-day operations, and leave the root account for administrative tasks only.

3. У чому відмінність механізмів отримання особливих привілеїв su і sudo?

   The su mechanism allows a user to gain root privileges temporarily by using the root user's password. In this case, the user is completely replaced by the root user, and he has full access to the system. The sudo mechanism allows a user to execute individual commands with root privileges without using the root user's password. At the same time, the executable command is executed with limited root rights, which allows the user to perform the necessary tasks without violating system security.

4. Чому домашній каталог користувача root не розміщено в каталозі /home?

   The home directory of the root user is usually not located in the /home directory for security reasons. The root user has full access to the system, so his home directory is located in a separate /root directory that has limited access for other users.

5. Для чого використовується команда getent?

   The getent command is used to retrieve information from various sources, such as the /etc/passwd file or the /etc/group file. It is typically used to retrieve information about users, groups, or passwords from these files, allowing programs or scripts to access this data.

6. Яким чином можна видалити існуючі групи користувачів? Чи залишиться інформація про них десь у системі?

   To delete an existing user group in Unix/Linux, you can use the `groupdel` command. For example, to delete a group named `developers`, you need to execute the command `sudo groupdel developers`. After deleting a group, its information will disappear from the /etc/group and /etc/gshadow files, but if it was used to provide access to files or folders, there may be problems accessing those files.

7. Як можна змінити пароль користувача?

  To change the user password in Unix/Linux, you can use the `passwd` command. For example, to change the password for a user with the name `john`, you need to execute the command `sudo passwd john` and enter the new password twice. After that, the password will be changed for the user named `john`.

>Висновок:
>>Готував студент Кушанов Р.Г.

> In this lab, I learned how to work with user groups, assign access rights to them, set up passwords for groups, and work with system users
