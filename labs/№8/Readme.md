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
|implementation      |        впровадження|
|kernel              |                ядро|
|management          |          управління|
|hierarchy           |            ієрархія|
|guideline           |         керівництво|
|governed            |           керований|
|allocating          |           виділення|
|addressing          |           адресація|
|executing           |           виконання|
|produce             |           виробляти|

2. Дайте відповіді на наступні питання: 

>Готував студент Кушанов Р.Г.

  - Розкрийте поняття “псевдо файлової системи”, для чого воно потрібно системі?
  
    A pseudo file system is a type of file system that does not contain actual data on a physical storage device. Instead, it provides an interface for accessing various system resources, such as processes, memory usage, and network statistics, through a file-like structure. It is necessary for the system because it allows processes and applications to access and modify system information in a standardized and consistent way, without needing to implement specific system calls for each resource.
  
  - Чому користувачі не так часто звертаються на пряму до каталогу `/proc`, яким чином з нього можна отримати інформацію?
  
    Users do not frequently access the `/proc` directory directly because it contains system information in a non-human-readable format, with files and directories representing different aspects of the system. Information can be obtained from it using command-line utilities such as ps, top, and free, which provide summarized information on processes, resource usage, and system memory. Additionally, the contents of specific files in `/proc`, such as `/proc/cmdline` and `/proc/meminfo`, can be accessed directly to obtain more detailed information.
  
  - Яке призначення файлів `/proc/cmdline`, `/proc/meminfo` та `/proc/modules`?
  
    The file `/proc/cmdline` contains the kernel command line parameters that were used to boot the system, including options such as the root file system and kernel parameters. The file `/proc/meminfo` provides information on the system's memory usage, including total memory, free memory, and usage by various system components. The file `/proc/modules` lists the currently loaded kernel modules and their dependencies.
  
  - Яке призначення команди free?
  
    The free command is a utility that provides information on the system's memory usage, including total memory, free memory, and usage by various system components. It can be used to diagnose memory issues, identify memory-hungry processes, and monitor system performance.
  
  - Для чого потрібні лог-файли, наведіть приклади їх застосування?
  
    Log files are files that record system events, errors, and messages, which can be used for debugging, monitoring, and auditing purposes. Examples of their use include system logs such as /var/log/syslog, which records general system events and errors, and application logs, such as Apache web server logs, which record requests, errors, and other information related to web server activity.
  
  - Яке призначення файлу `/var/log/dmesg`?
  
    The file `/var/log/dmesg` contains the output of the kernel's ring buffer, which records system messages during boot time and other kernel events. It can be used to diagnose system issues, identify hardware problems, and monitor system performance.
  
  - Для чого розроблено `FHS`?
  
    The Filesystem Hierarchy Standard (`FHS`) is a standard that defines the organization and layout of file systems in Linux and other Unix-like systems. It was developed to provide a standardized and consistent file system structure across different Linux distributions, simplifying software development and management, and ensuring compatibility across different systems.
  
  - Які основні команди є у Linux для перегляду та конфігурації мережі
  
    Some of the main commands in Linux for viewing and configuring the network include `ifconfig`, `ip`, and `netstat`. `ifconfig` is used to configure network interfaces, view their settings, and check their status. `ip` is a more advanced utility that provides more detailed information on network interfaces and their configuration, routing tables, and other networking information. netstat provides information on network connections and socket information, including listening ports and active connections. Other useful commands include `ping`, `traceroute`, and `nslookup`, which are used for network testing and troubleshooting.

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



2. Виконайте практичні завдання у терміналі:

>Готував студент Штома Д.О.

  - в даній лабораторній роботі використовувалась команда cat, дослідіть її можливості та опишіть для яких задач вона призначена;
  
  The cat command (short for "concatenate") is a standard Unix/Linux command that is designed to display, create, copy, and merge text files. The main features of the command include:
  
    1. displaying the contents of files;
    2. creating new files;
    3. redirecting the contents of one file to another;
    4. merge several files into one.
  
  
  - продемонструйте приклади, коли команда cat використовується для створення файлу, перегляду вмісту файлу, перенаправлення інформації у інший файл, склеювання декількох файлів в один;
  
  Examples of using the cat command:

creating a file:

     cat > newfile.txt Hello, world! (press Ctrl + D to complete the input)

view the contents of the file:

       cat newfile.txt

redirect information to another file:

       cat newfile.txt > anotherfile.txt

combine several files into one:

       cat file1.txt file2.txt > mergedfile.txt
  
  
  - які параметри команди cat треба використати, щоб пронумерувати рядки файлу, відобразити недруковані символи, видалити порожні рядки?
  
  The parameters of the cat:
  
number the lines of the file:

     cat -n filename.txt

display unprintable characters:

     cat -v filename.txt

remove empty lines:

     cat -s filename.txt
   
  - описати можливості команди dig і навести приклади;
  
  The dig command (short for "Domain Information Groper") is a useful tool for obtaining information about DNS records. It allows you to make DNS queries and receive responses from DNS servers.


An example of using the dig command:


     dig example.com

  
  - опишіть можливості команди netstat та наведіть приклади;.


 The netstat command (short for Network Statistics) allows you to monitor network and connection statistics. You can view active connections, listening ports, network protocol statistics, and more.
 
Examples of using the netstat command:

To view active connections:

     netstat -a
     
to view the listened ports:


     netstat -l

view statistics of network protocols:


     netstat -s
     
show processes related to active connections:


     netstat -p
     
view active connections with addresses displayed in character format:


     netstat -n
     
show routing information:


     netstat -r


### Контрольні запитання

>Готував студент Кушанов Р.Г.

1. Як пов'язані між собою команди `cat` та `tac`?

   The commands `cat` and `tac` are related in that they both read and display the contents of files. However, the main difference between them is the order in which they display the contents. The cat command displays the contents of a file from beginning to end, while the tac command displays the contents of a file from end to beginning.

2. Що робить команда `ss`?

   The `ss` command is a utility used to display information about active network connections, listening ports, and sockets. It is similar to the netstat command, but provides more detailed information and is generally faster and more efficient.

3. В чому відмінність між командами `ps --forest` та `pstree`?

   The `ps --forest` command displays the process tree in a hierarchical format, showing the relationships between parent and child processes. The `pstree` command does the same thing, but displays the process tree in a more visually-appealing format using ASCII characters.

4. У яких каталогах зберігаються налаштування системи?

   System settings are stored in various directories, depending on the specific setting and the Linux distribution being used. Some common directories for system settings include `/etc`, `/usr/share`, `/var`, and `/usr/lib`.

5. У яких каталогах можна знайти встановлені в системі програми, доступні для користувача?

   Installed programs available to the user can be found in directories such as `/usr/bin`, `/usr/local/bin`, and `/opt`.

6. У яких каталогах можна знайти встановлені системні програми і програми призначені для виконання суперкористувачем?

   System programs and programs intended for superuser execution can be found in directories such as `/bin`, `/sbin`, `/usr/sbin`, and `/usr/libexec`. These directories typically contain system utilities and important system executables that are required for the proper functioning of the system.
 
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

