“Київський фаховий коледж зв’язку”  
Циклова комісія Комп’ютерної інженерії

## ЗВІТ ПО ВИКОНАННЮ
## ЛАБОРАТОРНОЇ РОБОТИ №7
>з дисципліни:  
>«Операційні системи»

>**Тема:** 
>“Створення скриптових сценаріїв та визначення апаратної конфігурації системи”

>**Виконали студенти групи РПЗ-03**  
>**Команда 2:**
>- Кушанов Р.Г.
>- Путін М.Г.
>- Штома Д.О.

>**Перевірив викладач**  
>Сушанова В.С.

>**Мета роботи**:
>1. Отримання практичних навиків роботи з командною оболонкою Bash.
>2. Знайомство знайомство з базовими діями при роботі зі скриптовими сценаріями.

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
|executable          |    виконуваний файл|
|access              |             доступу|
|directory           |             каталог|
|syntax              |           синтаксис|
|hash                |                 хеш|
|invoke              |           викликати|
|interpreter         |          перекладач|
|editor              |            редактор|
|prompt              |               запит|
|hashbang            |                  #!|

2. Дайте відповіді на наступні питання: 

>Готував студент Кушанов Р.Г.

  1. Охарактеризуйте поняття скриптового сценарію у командній оболонці.
  
  A shell script is a set of commands that are executed sequentially while the script is running. Scripts are commonly used to automate routine tasks to reduce the effort and time spent on performing such tasks manually. Scripts can contain branches, loops, conditional expressions, and other constructs that provide script execution flexibility and functionality.
  
  2. Яким чином створюються та редагуються скрипти, що треба зробити щоб запустити скрипт?
  
  Scripts are created in a text editor such as Vim or Nano and saved with the extension ".sh" to indicate that it is a shell script. Scripts can be run using the `sh` or `bash` command, specifying the path to the script file. Before running the script, you need to make sure that it has execute rights using the `chmod` command.
  
  3. Які основні компоненти материнської плати ви знаєте?
  
  Some of the main components of a motherboard include the processor, chipset, BIOS/UEFI, RAM and expansion slots, I/O controllers (including keyboard, mouse, USB and Ethernet ports), and GPU (in the case of embedded graphic subsystems).
  
  4. Коротко охарактеризуйте для яких пристроїв оперують поняттями MBR та GPT?
  
  MBR and GPT are disk mapping table formats. MBR (Master Boot Record) is an older format that can only support up to 4 primary partitions, one of which can be an extended partition. GPT (GUID Partition Table) is a newer format that can support up to 128 partitions and has no partition size limit.
  
  5. В чому суть операції монтування, для чого вона потрібна?
  
  A mount operation is the process of connecting an external storage device, such as a USB flash drive or external hard drive, to the operating system's file system. The connected device becomes readable and writable by the operating system, and operations can be performed on files stored on the device. Mounting also allows you to remove an external device safely, during which the operating system closes all open files and transfers control back to the external device before shutting down.

### Хід роботи

1. Опрацюйте всі приклади команд, що представлені у лабораторних роботах курсу NDG Linux Essentials -
Lab 11: Basic Scripting та Lab 12: Understanding Computer Hardware.

>Готував студент Путін М.Г.

|  Назва команди  |  Її призначення та функціональність  |
|:----------------|-------------------------------------:|
|`vi`| Editor to create basic shell scripts using basic shell commands, variables and control statements. |
|`nano`| Simple text-only editor |
|`gedit`| Graphical editor |
|`lscpu`| Determine the type of CPU |
|`free`| Shows how much RAM and swap space is being used |
|`lspci`| Shows what devices are connected to the PCI bus |
|`lsusb`| Prints list the USB connected devices |
|`lsmod`| To view the currently loaded modules |
|`fdisk`| Useful for identifying and manipulating disk storage resources on a system |

2. Створіть скриптові сценарії з виводом текстових повідомлень для користувача (продемонструйте
скріншоти):

>Готував студент Штома Д.О.

- сценарій має виводити привітання до поточного користувача вказуючи поточну дату та інформацію
про поточну систему;

- сценарій має виводити інформацію про апаратну конфігурацію поточної системи (використовуйте
команди розглянуті в Lab 12).- 


### Контрольні запитання

>Готував студент Кушанов Р.Г.

1. Яким чином у скриптах можна опрацьовувати змінні та створювати розгалужені та циклічні сценарії?
 
  ```
  variable_name=value для создания
  $name для получения значения
  ```
  
  branching:
  ```
  if [ $age -gt 18 ]
  then
    echo "You are an adult."
  else
    echo "You are a minor."
  fi
  ```
  cycle:
  ```
  for i in {1..10}
  do
    echo $i
  done

  i=1
  while [ $i -le 10 ]
  do
    echo $i
    i=$((i+1))
  done
  ```
  
2. В чому відмінність між командами arch та lscpu?

  The `arch` command returns the processor architecture on which the current processor is running.
  
  The `lscpu` command displays detailed information about the processor, including architecture, processor model, number of cores, processor speed, and other parameters.

3. Якою командою можна отримати інформацію про стан використання RAM поточною системою?

  Для отримання інформації про стан використання (RAM) в поточній системі в Linux можна використати команду `free`.

4. Які команди для перегляду стану підключення периферійних пристроїв можна використати в
терміналі?

  `lsusb`, `lspci`, `lsblk`, `df`, `dmesg`

5. Які можливості застунку gparted?

  Some of the features of GParted are:
  
   - Create, delete and edit hard disk partitions.
   - Format partitions in various file system formats, such as NTFS, FAT32, ext4, and others.
   - Moving and resizing hard disk partitions.
   - Changing the section label and system number.

>Висновок:
>>Готував студент Штома Д.О.
>
>In this lab, we learned about the existing ways to compress and archive files in Linux, and tried them out in practice.

