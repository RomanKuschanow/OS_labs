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
|||

2. Робота в в терміналі (закріплення практичних навичок) обов`язково представити свої скріншоти:
    1. Робота зі змінними (Variables) та псевдонімами (Aliases) в терміналі:
    >Готував студент Путін М.Г.

    
      - Створіть змінні, що будуть містити Ваші імена та прізвища $var_name1, $var_name2, $var_name3      
      - За допомогою команди echo виведіть імена студентів вашої команди
      - Створіть псевдоніми mycal1, mycal2, mycal3 для команди cal для автоматичного виведення календарю вашого року народження
      
      
      
    2. Робота з функціями (Functions) в терміналі:
    >Готував студент Путін М.Г.

    
      - Створіть функцію students_report, що порядково буде виводити спочатку імена студентів Вашої команди, а потім роки їх народження
      
      
    3. Робота з лапками (Quoting) в терміналі. Виведіть в командному рядку наступні речення:
     >Готував студент Штома Д.О.
     
     
      - “We create such variables as $var_name1, $var_name2, $var_name3, which stored our names Name1, Name2, Name3” (у реченні спочатку виводимо назви змінних, а потім їх вміст)
      - “We create such Aliases as mycal1, mycal2, mycal3, which can show our calendars: Calendar1, Calendar2, Calendar3” (у реченні спочатку виводимо назву команди-псевдонімів, потім вивід цих команд).
      
      
      
    4. Робота з інструкціями керування (Control Statements) в терміналі:
     >Готував студент Штома Д.О.
     
     
      - Чи можна завдання 2.1 та 2.2 ходу роботи виконати через інструкції керування без написання окремої функції, як це буде виглядати?
      
      
      
    5. Робота з командами довідки (Man Pages) в терміналі:
     >Готував студент Штома Д.О.
     
     
      - На прикладі команди uname продемонструйте як отримати довідку. На основі отриманої додаткової інформації наведіть 5 різних варіантів виводу результату інформації по даній команді з використанням 5 різних параметрів (Options)



>Висновок:
>
>>Готував студент Кушанов Р.Г.
>
>In this lab, we learned how to work with the CLI (command line interface) of Linux-based operating systems, and learned how to write functions and use variables in CLI.
