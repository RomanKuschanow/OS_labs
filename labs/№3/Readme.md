“Київський фаховий коледж зв’язку”  
Циклова комісія Комп’ютерної інженерії

## ЗВІТ ПО ВИКОНАННЮ
## ЛАБОРАТОРНОЇ РОБОТИ №3
>з дисципліни:  
>«Операційні системи»

>**Тема:** 
>“Знайомство з базовими командами CLI-режиму в Linux”

>**Виконали студенти групи РПЗ-03**  
>**Команда 2:**
>- Кушанов Р.Г.
>- Путін М.Г.
>- Штома Д.О.

>**Перевірив викладач**  
>Сушанова В.С.

>**Мета роботи**:
>1. Знайомство з базовими командами CLI-режиму в Linux.
>2. Знайомство з базовими текстовими командами в термінальному режимі роботи в різних ОС.2. 


>**Матеріальне забезпечення занять**
>1. ЕОМ типу IBM PC.
>2. ОС сімейства Windows (Windows 7).
>3. Віртуальна машина – Virtual Box (Oracle).
>4. Операційна система GNU/Linux – CentOS.4. 


***

### Завдання для попередньої підготовки.
1. Прочитайте короткі теоретичні відомості до лабораторної роботи та зробіть невеликий словник базових англійських термінів з питань класифікації віртуальних середовищ.

>Готував студент Кушанов Р.Г.

| Термін англійською | Термін українською |
|:-------------------|-------------------:|
|terminal            |            термінал|
|shell               |            оболонка|
|interpreter         |       інтерпретатор|
|environment         |          середовище|
|prompt              |            підказка|
|directory           |             каталог|
|executed            |            виконано|
|variables           |              змінні|
|accept              |          погодитися|
|expand              |           розширити|

2. Дайте відповіді на наступні питання:

>Готував студент Кушанов Р.Г.

  - Яку базову інформацію надає рядок запрошення prompt?
  
    The prompt usually contains information about the user and the system
  
  - Для чого команді потрібні параметри та аргументи?
  
    Argument - what the command will work with  
    Parameter - additional information about what exactly the command should do
  
  - Яке призначення команд ls, які параметри та аргументи вона може мати? Наведіть 3 приклади.
  
    The `ls` command is used to display a list of files and directories in the current working directory.
  
    Here are some examples:
  
    - Display detailed information about files and directories with the `-l` option.
    - Display a list of files and directories sorted by modification date with the `-t` option.
    - Display a list of files and directories with a given extension with an argument containing that extension. For example, to display a list of files with the extension `.txt`, you need to enter the `ls *.txt`
  
  - Яким чином можна використати історію команд, які переваги це надає?
    
    The command history is stored in the command buffer and can be accessed using the up arrow and down arrow keys on the keyboard.
  
    The main advantages of using command history:

    - Quick access to previously typed commands: Using command history allows you to quickly find and repeat previously typed commands without having to retype them.
    - Time Saving and Convenience: Using command history saves time and convenience by not having to repeat long or complex commands over and over again.
    - Error correction: Command history also makes it easy to find and correct errors in previous commands without retyping the entire command.
    - Improved productivity: Using command history allows you to speed up your work with the operating system and applications, reducing the time and effort required to retype commands.
  
  - Яке призначення команди echo?
  
    The "echo" command is used to display text on the screen. It allows you to display text messages on the terminal screen or output them to the output data stream.
  
    In addition, the "echo" command can be used in scripts to output the values of variables, as well as to create files and write data to them.
  
  - Охарактеризуйте поняття змінної в оболонці Bash, які типи змінних вона підтримує?
  
    In the Bash shell, a variable is a name used to store a value. Variables allow you to store data that can be used in programs and scripts. Variables can hold different types of data, such as strings, numbers, arrays, booleans, etc.

    In Bash, variables can be divided into three types:

    - Environment variables are variables that are stored in the system environment and are available to all processes running on the system. Environment variables can be set using the `export` command.
    - Local context variables (local variables) are variables that are available only within the current script or function in which they were defined.
    - Positional parameters are variables that contain arguments passed to an executable program or script at startup. The first nine positional parameters are labeled as $1, $2, $3, ..., $9.
  
  - Яке призначення команд env, export та unset?
  
    The `env` command is used to display the current environment variables or to run a command in a modified environment. It can be used to set environment variables for a specific command without affecting the current environment.

    The `export` command is used to set environment variables in the current shell session or to mark variables for export to child processes. When a variable is marked for export using the export command, it becomes part of the environment and is passed on to any child processes.

    The `unset` command is used to remove variables and functions from the current shell session or from the environment. When a variable is unset using the unset command, it is no longer available for use in the current shell session or in any child processes.
  
  - Які команди для отримання довідки по командам в терміналі ви знаєте?

    There are several ways to get help about commands in the terminal, including:

    - `man` - command to display command help in the terminal. For help, run the `man` command with the name of the command.
    - `--help` - Most commands have a `--help` option that displays a brief description of the command and a list of available options.
    - `help` - This command displays help on built-in Bash shell commands. Run `help` without parameters to get a list of built-in Bash commands, or run `help` with the name of a command to get help about a built-in command.
    - `apropos` - this command searches for commands matching the specified keyword in the help text. Run the `apropos` command with a keyword to get a list of commands associated with that keyword.
    - `whatis` - this command displays a brief description of the command. Run the `whatis` command with the command name to get a brief description.
  
### Хід роботи

1. Опрацюйте всі приклади команд, що представлені у лабораторній роботі курсу NDG Linux Essentials Lab 5: Command Line Skills та Lab 6: Getting Help. Створіть таблицю для опису цих команд
>Готував студент Путін М.Г.


|Назва команди|Її призначення та функціональність|
|:------------|---------------------------------:|
|ls           |Виводить інформації про каталоги та файли. За замовчуванням без аргументів відображає інформацію для поточного каталогу|
|ls -l        |Використанні параметру -l в команді ls дозволяє відобразити інформацію про файли, розташовані в поточному робочому каталозі, у довгому форматі, який надає більш розширену додаткову інформацію|
|ls -l /tmp   |Використання аргументу /tmp в поєднанні з параметром -l в команді ls дозволяє відобразити детальну інформацію про файли в каталозі /tmp.|
|whoami       |The output of the whoami command, sysadmin, displays the user name of the current user. Although in this case your username is displayed in the prompt, this command could be used to obtain this information in a situation when the prompt did not contain this information.|
|  uname      | Execute the uname command again twice in the terminal, once with the option -n and again with the option --nodename. This will display the network node hostname, also found in the prompt. |
|pwd          | The current directory in the example above is /home/sysadmin. This is also referred to as your home directory, a special place where you have control of files and other users normally have no access. By default, this directory is named the same as your username and is located underneath the /home directory.  |
|history      | To view a limited number of commands, the history command can take a number as a parameter to display exactly that many recent entries.  |
|!9           |To execute a command again, type the exclamation point and the history list number. For example, to execute the 9th command in your history list  |
|echo Hello Student|The echo command can be used to print text and the value of a variable, and to show how the shell environment expands metacharacters (more on metacharacters later in this lab)    |
|echo $PATH   | The PATH variable is displayed by placing a $ character in front of the name of the variable.  |
|which date   | The output of the which command tells you that when you execute the date command, the system will run the command /bin/date. The which command makes use of the PATH variable to determine the location of the date command. |
| type command| The type command identifies the cd command as an internal command  |
|which ls     | External commands are binary executables stored in directories that are searched by the shell. If a user types the ls command, the shell searches through the directories that are listed in the PATH variable to try to find a file named ls that it can execute. Use the which command to display the full path to the ls command. |
|Aliases      |  Aliases can be used to map longer commands to shorter key sequences. When the shell sees an alias being executed, it substitutes the longer sequence before proceeding to interpret commands.  |
|date         | Execute commands in the bash shell by typing the command and then pressing the Enter key.  |
| man date    | To learn more about commands, access the manual page for the command with the man command.    |
|/file        |  Searches are not case sensitive and do not "wrap" around from the bottom to top, or vice versa. Start a forward search for the word "file" by typing:  |
| man -k password |   In some cases you may not remember the exact name of the command. In these cases you can use the -k option to the man command and provide a keyword argument. For example, execute the following command to display a summary of all man pages that have the keyword "password" in the description:  |
| apropos password  | Note that the apropos command is another way of viewing man page summaries with a keyword. Type the following command:  |
|man -f passwd   | There are often multiple man pages with the same name. For example, the following command shows three pages for passwd. Execute the following command to view the man pages for the word passwd:  |
| whatis passwd |  Instead of using man -f to display all man page sections for a name, you can also use the whatis command:  |
| info date   | Almost all system features (commands, system files, etc.) have man pages. Some of these features also have a more advanced feature called info pages. For example, execute the following command: |
| date --help | Another way of getting help is by using the --help option to a command. Most commands allow you to pass an argument of --help to view basic command usage:  |


2. Робота в в терміналі (закріплення практичних навичок) обов`язково представити свої скріншоти:
    1. Робота зі змінними (Variables) та псевдонімами (Aliases) в терміналі:
    >Готував студент Путін М.Г.

    
      - Створіть змінні, що будуть містити Ваші імена та прізвища $var_name1, $var_name2, $var_name3
      
      ![Alt Text](./img/img_5.png?raw=true "Optional Title")
      - За допомогою команди echo виведіть імена студентів вашої команди
      ![Alt Text](./img/img_6.png?raw=true "Optional Title")
      - Створіть псевдоніми mycal1, mycal2, mycal3 для команди cal для автоматичного виведення календарю вашого року народження 
      
      ![Alt Text](./img/img_7.png?raw=true "Optional Title")
      
      
      
    2. Робота з функціями (Functions) в терміналі:
    >Готував студент Путін М.Г.

    
      - Створіть функцію students_report, що порядково буде виводити спочатку імена студентів Вашої команди, а потім роки їх народження
      ![Alt Text](./img/img_8.png?raw=true "Optional Title")
      
      
    3. Робота з лапками (Quoting) в терміналі. Виведіть в командному рядку наступні речення:
     >Готував студент Штома Д.О.
     
     
      - “We create such variables as $var_name1, $var_name2, $var_name3, which stored our names Name1, Name2, Name3” (у реченні спочатку виводимо назви змінних, а потім їх вміст)
      ![Alt Text](./img/img_1.jpg?raw=true "Optional Title")
      
      - “We create such Aliases as mycal1, mycal2, mycal3, which can show our calendars: Calendar1, Calendar2, Calendar3” (у реченні спочатку виводимо назву команди-псевдонімів, потім вивід цих команд).
      ![Alt Text](./img/img_2.jpg?raw=true "Optional Title")
      
      
      
    4. Робота з інструкціями керування (Control Statements) в терміналі:
     >Готував студент Штома Д.О.
     
     
     
      - Чи можна завдання 2.1 та 2.2 ходу роботи виконати через інструкції керування без написання окремої функції, як це буде виглядати?
      
      ![Alt Text](./img/img_3.jpg?raw=true "Optional Title")
      
    5. Робота з командами довідки (Man Pages) в терміналі:
     >Готував студент Штома Д.О.
     
     
      - На прикладі команди uname продемонструйте як отримати довідку. На основі отриманої додаткової інформації наведіть 5 різних варіантів виводу результату інформації по даній команді з використанням 5 різних параметрів (Options)
      ![Alt Text](./img/img_4.jpg?raw=true "Optional Title")

Answers to control questions:
1) There are several types of commands in the Bash shell, including:
    - Built-in commands: These are commands that are built into the shell itself, such as cd (change directory) and echo (print to screen).
    - External commands: These are commands that are separate programs installed on the system, such as ls (list files) and grep (search for text in a file).
    - Alias commands: These are custom shortcuts that can be created by the user to execute a longer command with a shorter name.
    - Function commands: These are custom commands created by the user using shell programming constructs.
2) Environment variables are variables that are set in the shell's environment and are accessible to any program or command run in that environment. They are used to store information that may be needed by multiple programs or commands. Some common environment variables include PATH (which stores a list of directories to search for executables), HOME (which stores the path to the user's home directory), and USER (which stores the username of the current user). Environment variables can be viewed in the terminal using the command "printenv" or by using the command "echo" with the variable name preceded by a "$" sign (e.g., "echo $PATH").

3) The variable $PS1 is a shell variable that defines the prompt string that is displayed before each command in the terminal. The default value of $PS1 is "\s-\v$ ", which displays the name of the shell and its version number, followed by a dollar sign. The contents of $PS1 can be viewed in the terminal by using the command "echo $PS1".

4) The value of $PS1 can be changed by assigning a new value to it using the "export" command. For example, to set $PS1 to display the current working directory, you could use the command "export PS1='\w$ '". The new prompt will be displayed the next time a command is entered. To change the value of $PS1 permanently, the new value can be added to the user's shell configuration file (such as ~/.bashrc or ~/.bash_profile).

5) Quotation marks are used in the Bash shell to group words together as a single argument, especially when the words contain spaces or other special characters. There are two types of quotation marks: single quotes ('...') and double quotes ("..."). Single quotes preserve the literal value of all characters within the quotes, while double quotes allow certain characters (such as variables) to be expanded. Backslashes () can also be used to escape special characters within quotes.

6) Control instructions (also called control structures) are used in Bash programming to execute commands conditionally or repeatedly. Some common types of control instructions include:

    - if/else statements: These allow the execution of certain commands based on a specified condition.
    - for loops: These allow a set of commands to be executed for each element in a list or range.
    - while loops: These allow a set of commands to be executed repeatedly as long as a certain condition is true.
    - case statements: These allow the execution of certain commands based on a specified pattern.
7) The Bash prompt line typically ends with a dollar sign ($) for a regular user, or a hash symbol (#) for the root user. The difference between the two is that the hash symbol indicates that the user has superuser privileges and can execute commands that require root access.

8) The whereis and locate commands are used to locate files on the system. The whereis command searches for executable files, source files, and manual pages for a specified command or program, while the locate command searches for files and directories on the system based on a specified pattern. The main difference between the two is that whereis searches only a few specific directories on the system, whereas locate searches the entire system's database of filenames and paths. This makes locate much faster, but it may not always find the most up-to-date information if the system's database has not been updated recently. Additionally, the whereis command only searches for files related to a specific command or program, while the locate command can be used to search for any file or directory on the system that matches a specified pattern. Both commands are useful for finding the location of files or programs on the system, and can help users locate files that they may need to modify or delete.


>Висновок:
>
>>Готував студент Кушанов Р.Г.
>
>In this lab, we learned how to work with the CLI (command line interface) of Linux-based operating systems, and learned how to write functions and use variables in CLI.
