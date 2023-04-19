“Київський фаховий коледж зв’язку”  
Циклова комісія Комп’ютерної інженерії

## ЗВІТ ПО ВИКОНАННЮ
## ЛАБОРАТОРНОЇ РОБОТИ №8
>з дисципліни:  
>«Операційні системи»

>**Тема:** 
>збереження службових даних системи та її мережева конфігурація

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
|||
|||
|||
|||
|||
|||
|||
|||
|||
|||

2. Дайте відповіді на наступні питання: 

>Готував студент Кушанов Р.Г.

  - Розкрийте поняття “псевдо файлової системи”, для чого воно потрібно системі?
  - Чому користувачі не так часто звертаються на пряму до каталогу /proc, яким чином з нього можна отримати інформацію?
  - Яке призначення файлів /proc/cmdline, /proc/meminfo та /proc/modules?
  - Яке призначення команди free?
  - Для чого потрібні лог-файли, наведіть приклади їх застосування?
  - Яке призначення файлу /var/log/dmesg?
  - Для чого розроблено FHS?
  - Які основні команди є у Linux для перегляду та конфігурації мережі

### Хід роботи

1. Опрацюйте всі приклади команд, що представлені у лабораторних роботах курсу NDG Linux Essentials - Lab 13: Basic Scripting та Lab 14: Network Configuration.

>Готував студент Путін М.Г.

|  Назва команди  |  Її призначення та функціональність  |
|:----------------|-------------------------------------:|
|`su`| is used to change the current user to root user |
|`ls /proc`| is used to list the contents of the /proc directory |
|`sleep`| is typically used to pause a program (shell script) for a specific period of time|
|`pkill`|command to terminate the remaining sleep command|
|`ifconfig`| used to determine your Internet Protocol (IP) address |
|`route`| used to view the table of routing information |
|`ping`| used to tell if a system is presently connected to a network |
|`dig localhost.localdomain`| used to resolve the localhost.localdomain name to an IP address |
|`netstat`| performs a large variety of tasks related to networking |
|`ss`| used to view which connections are currently established between the local machine and remote machines, statistics about those connections |



2. Виконайте практичні завдання у терміналі (продемонструйте скріншоти):

>Готував студент Штома Д.О.

  - в даній лабораторній роботі використовувалась команда cat, дослідіть її можливості та опишіть для яких задач вона призначена;
  - продемонструйте приклади, коли команда cat використовується для створення файлу, перегляду вмісту файлу, перенаправлення інформації у інший файл, склеювання декількох файлів в один;
  - які параметри команди cat треба використати, щоб пронумерувати рядки файлу, відобразити недруковані символи, видалити порожні рядки?
  - опишіть можливості команди dig та наведіть приклади;
  - опишіть можливості команди netstat та наведіть приклади;.


### Контрольні запитання

>Готував студент Кушанов Р.Г.

1. Як пов&#39;язані між собою команди cat та tac?
2. Що робить команда ss?
3. В чому відмінність між командами ps --forest та pstree?
4. У яких каталогах зберігаються налаштування системи?
5. У яких каталогах можна знайти встановлені в системі програми, доступні для користувача?
6. У яких каталогах можна знайти встановлені системні програми і програми призначені для виконання суперкористувачем?
 
>Готував студент Путін М.Г.

7. Поясніть призначення команд ping, ifconfig, traceroute.  
   - The ping command is used to test the connectivity between two networked devices by sending ICMP echo request packets to the destination and waiting for the ICMP echo reply packets from the destination. This helps in verifying if the network connection is active, and if there are any packet losses or network latency issues.  
   - The ifconfig (interface configuration) command is used to display and configure the network interfaces of a system. It displays the IP address, netmask, and other parameters of the network interfaces. With ifconfig, you can configure network interfaces manually or enable/disable them, set up the IP address and network masks, and so on.  
   - The traceroute command is used to trace the route that a packet takes from the source to the destination device. It sends ICMP echo request packets with increasing TTL (time-to-live) values, and records the IP address of each device that the packet passes through before reaching the destination. This helps in identifying network connectivity issues and network congestion.


8. Як називаються мережеві інтерфейси в Linux?  
  In Linux, network interfaces are named based on the interface type, followed by a number. For example, Ethernet interfaces are named eth0, eth1, eth2, etc. Wi-Fi interfaces are named wlan0, wlan1, wlan2, etc. Loopback interfaces are named lo.

9. Як за допомогою команди ifconfig вивести параметри тільки одного мережевого інтерфейсу (наприклад, eth1), а не всіх?  
  To display the parameters of only one network interface (for example, eth1) using ifconfig, you can use the following command: `ifconfig eth1`  
  This will display the IP address, netmask, and other parameters of the eth1 interface. If the interface is not currently active, the output will show only the hardware address (MAC address) of the interface.

>Висновок:
>>Готував студент Штома Д.О.
>
>

