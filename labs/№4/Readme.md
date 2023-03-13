“Київський фаховий коледж зв’язку”  
Циклова комісія Комп’ютерної інженерії

## ЗВІТ ПО ВИКОНАННЮ
## ЛАБОРАТОРНОЇ РОБОТИ №4
>з дисципліни:  
>«Операційні системи»

>**Тема:** 
>“Команди Linux для управління процесами”

>**Виконали студенти групи РПЗ-03**  
>**Команда 2:**
>- Кушанов Р.Г.
>- Путін М.Г.
>- Штома Д.О.

>**Перевірив викладач**  
>Сушанова В.С.

>**Мета роботи**:
>1. Отримання практичних навиків роботи з командною оболонкою Bash.
>2. Знайомство з базовими командами для управління процесами.


>**Матеріальне забезпечення занять**
>1. ЕОМ типу IBM PC.
>2. ОС сімейства Windows (Windows 7).
>3. Віртуальна машина – Virtual Box (Oracle).
>4. Операційна система GNU/Linux – CentOS.4. 


***

### Завдання для попередньої підготовки.
1. Прочитайте короткі теоретичні відомості до лабораторної роботи та зробіть невеличкий словник базових англійських термінів з питань призначення команд та їх параметрів.

>Готував студент Кушанов Р.Г.

|    Термін англійською    |  Термін українською   |
|:-------------------------|----------------------:|
|Monitoring                |Контроль               |
|Utilities                 |Утиліти                |
|Subset                    |Підмножина             |
|Available                 |Доступний              |
|Running                   |Запущений              |
|Gleaning                  |Збір                   |
|Average                   |Середній               |
|Interactive               |Інтерактивний          |
|Refuse                    |непридатний            |
|Interprocess communication|Міжпроцесна комунікація|

2. Дайте відповіді на наступні питання:
  
  >Готував студент Кушанов Р.Г.
  
  - Які команди для моніторингу стану процесів ви знаєте. Як переглянути їх можливі параметри?

    - `ps`
    - `top`
    - `htop`
    - `pstree`
    - `pgrep`
    - `lsof`
    - `strace`
    
    To view possible command options can be used the `--help` or `-h` option.  
    For example `ps --help` or `top -h`
  
  - Чи може команда `ps` у реальному часі відслідковувати стан процесів?

    The `ps` command shows the current state of the processes at the time it was run, if you add the `--watch` or `-w` option, then `ps` will start updating its output every few seconds.  
    For example `ps -efw`
  
  - За якими параметрами можливе сортування процесів в команді top? Як переключатись між ними?

    - `p`
    - `M`
    - `T`
    - `N`
    - `K`
    
    To switch between options, you just need to press the corresponding keys on the keyboard.
  
  - Які команди для завершення роботи процесів ви знаєте?

    - `kill`
    - `pkill`
    - `killall`
    - `xkill`


### Хід роботи

1. Дайте відповіді на наступні питання:

  >Готував студент Путін М.Г.

  - Як вивести вміст директорії /proc? Де вона знаходиться та для чого призначена. Охарактеризуйте інформацію про її вміст?
  To display the contents of the /proc directory, you can use the ls command: `ls /proc`
  The /proc directory is a virtual file system that is located in the root directory of a Linux system. It provides an interface to kernel data structures and information about running processes.
  
  - Як вивести інформацію про поточні сеанси користувачів. Якою командою це можна зробити?  
  To display information about the processes running within a user session, you can use the -u option followed by the username of the user whose processes you want to display. For example, to display information about the processes running within the session of the currently logged in user, you can use the following command: `ps -u $USER` 
  
  - Які дії можна зробити в терміналі за допомогою комбінацій Ctrl + C, Ctrl + D та Ctrl + Z?  
    - Ctrl + C: This combination sends the "interrupt" signal to the currently running process, which causes it to terminate.   

    - Ctrl + D: This combination sends an "end of file" (EOF) character to the terminal, which signals the end of input. This is often used to exit from a command-line shell.  

    - Ctrl + Z: This combination sends the "suspend" signal to the currently running process, which causes it to pause and be placed in the background.  
  
  - Чим відрізняється фоновий процес від звичайного. Де вони використовуються?  
    A background process is a process that is executed in the background without blocking the terminal or requiring the user to wait for it to complete. In contrast, a regular process is executed in the foreground and requires the user to wait for it to complete before proceeding. 
    Background processes are often used for long-running tasks or tasks that do not require user interaction. Examples of background processes include:  
    
    - Running a backup or file transfer task in the background while continuing to work on other tasks.  
    - Running a server or daemon process in the background that provides a service to other programs or users.  
    - Running a command that takes a long time to complete, such as compiling a large program or compressing a large file.  
    
  - Опишіть наступні команди та поясніть що вони виконують – команда jobs, bg, fg.
    - jobs: This command lists all jobs running in the current shell session, including both background and suspended jobs. Each job is assigned a unique job ID number, which can be used to refer to the job in other job control commands. The jobs command also displays the status of each job, which can be one of "running", "stopped", or "terminated".

    - bg: This command is used to move a suspended job to the background and continue running it. You can use the job ID number or the job's process ID (PID) to specify which job to move to the background. 
    
    - fg: This command is used to bring a job from the background to the foreground and continue running it. You can use the job ID number or the job's PID to specify which job to bring to the foreground. 
    
  - Якою командою можна переглянути інформацію про запущені в системи фонові процеси та задачі?  
  To view information about background processes and tasks running in the system, you can use the `ps ` command with specific options that show the status of the processes.   
  `ps aux`: This command shows a detailed list of all processes running on the system, including those running in the background.   
  `ps -ef`: This command shows a list of all processes running on the system, including those running in the background, in a tree format.
  `ps -ejH:` This command shows a list of all processes running on the system, including those running in the background, in a hierarchical format. 
  
  - Як призупинити фоновий процес, як його потім відновити та при необхідності перезапусти?  
  To pause, resume, and restart a background process, you can use the following commands:

  `kill`: This command can be used to send various signals to a process, including the "stop" signal (SIGSTOP) to pause a process and the "continue" signal (SIGCONT) to resume a paused process.  

  `bg`: This command is used to move a suspended or stopped job to the background and continue running it.  

  `fg`: This command is used to bring a job from the  background to the foreground and continue running it.  
  

2. Запустіть термінал, та в командному рядку виконайте наступні дії для ознайомлення з роботою з процесами:

  >Готував студент Штома Д.О.

  - запустіть команду top, проаналізуйте отриманий в цій команді результат та охарактеризуйте найбільш активні процеси у системі;
  - призупинити виконання команди top (треба використати комбінацію клавіш);
  - вивести інформацію про процеси за допомогою команди ps;
  - наведіть 5 прикладів з використанням різних параметрів команди ps (наприклад, вивести тільки системні процеси, вивести процеси конкретного користувача, вивести дерево процесів тощо). Опишіть, що саме роблять обрані Вами параметри
  - передивіться чи є у Вас запущені фонові процеси, які саме?
  - відновити виконання призупиненого фонового процесу спочатку у позиції “на передньому плані” (foreground), потім ще раз його призупинити, а потім відновити його виконання у позиції “на задньому плані” (background)
  - завершити роботу даного фонового процесу


### Контрольні запитання

>Готував студент Путін М.Г.

1. Яке призначення директорії /proc в системах Linux. Яку інформацію вона зберігає?   
  The /proc directory contains a variety of files and subdirectories that provide information about the system's hardware and software, as well as information about running processes. The most commonly used directories in the /proc filesystem:

  `/proc/cpuinfo`: contains information about the CPU(s) installed on the system.  
  `/proc/meminfo`: contains information about the system's memory usage.  
  `/proc/net`: contains information about network interfaces and statistics.  
  `/proc/sys`: contains various system settings that can be modified at runtime.  
  `/proc/PID`: contains information about a specific process, where PID is the process ID.  

2. Як серед будь-яких трьох процесів динамічно визначати, який з них в поточний момент часу використовує найбільший обсяг пам'яті? Який відсоток пам’яті він споживає від загального обсягу?  
To dynamically determine which of any three processes is currently using the most memory and what percentage of memory it consumes of the total amount, we can use the `top` command.  
Also we can sort the list by memory usage by pressing the M key.  
To limit the output of top to only the top three processes by memory usage, we should press the 1 key to display all CPUs, and then press the Shift + N keys to limit the output to the top three processes

4. Як отримати ієрархію батьківських процесів в системах Linux? Наведіть її структуру та
охарактеризуйте.  
To get the hierarchy of parent processes in Linux systems, we can use the `pstree` command. The `pstree` command displays the processes on the system in a tree format, with the root process at the top of the tree and child processes listed below their parent processes.  
There is hierarchy I have in ubuntu bash:  
```
init─┬─init───bash───pstree
     └─{init}
```
The `init` process is the first process that is started by the system when it boots up, and it has a PID (Process ID) of 1. In this case, the init process has launched a Bash shell, which in turn is running the pstree command.

The `{init}` process is a child process of init and is not listed in the process table because it is a kernel thread. Kernel threads are created by the kernel itself and are not associated with a user space process. The `{init}` process is used by the kernel to perform various system tasks.

And the last one - the process tree represents a `Bash shell` running the `pstree` command, launched by the init process

4. Чим відрізняється команда top від ps?

The differences between the `top` and `ps` command are here:  
  - `top` are interactive command-line utility, while `ps` isn't.
  - `top` displays information in a dynamic way, allowing to view information in real-time.
  - `top` provides a more comprehensive set of information about processes.
  - `top` allows to perform actions on processes

>Готував студент Штома Д.О.

5. Які додаткові можливості реалізує htop в порівнянні з top?
6. Опишіть компоненти вашої мобільної ОС для здійснення моніторингу запущених в системі процесів?
7. Чи підтримує Ваша мобільна ОС термінальне керування роботою процесів, опишіть як саме.
8. Чи можливо поставити сторонні програмні засоби, що дозволяють організувати управління та моніторинг роботою процесів у Вашому мобільному телефоні. Коротко опишіть їх.

>Висновок:
>
>>Готував студент Кушанов Р.Г.
>
>In this lab, we gained experience using various commands to control processes and monitor their status, such as: `ps`, `top`, `kill`.

