>Виконали студенти групи РПЗ-03  
>Команда 2:
>
>Кушанов Р.Г.  
>Путін М.Г.  
>Штома Д.О.

1. В робочому просторі операційної системи необхідно встановити декілька командних інтерпретаторів (окрім bash ще 2 на ваш вибір):

>Готував студент Штома Д.О.

- What commands can be used to do this;

Installing multiple command prompts:
To install additional command prompts on the Linux operating system, you need to use the package installation commands. Depending on your Linux distribution, these commands may differ.

For Debian and Ubuntu:

       sudo apt-get update
       sudo apt-get install zsh
       sudo apt-get install fish
       
For Fedora:

      sudo dnf install zsh
      sudo dnf install fish
      
For CentOS and RHEL:

      sudo yum install zsh
      sudo yum install fish

- Describe briefly the capabilities of each of them.

a) Zsh (Z Shell):

Zsh is an enhanced version of the Bourne Shell (sh) that includes numerous improvements and additional features. The main features of Zsh include:

    1.Sophisticated command autocomplete, making command entry faster and more convenient.
    2.Advanced script handler with many new commands and built-in functions.
    3.Advanced globbing (templates for files).
    4.Flexible customization, which allows users to customize Zsh for their needs.
    5.Themes and plugins that allow users to change the appearance and functionality of Zsh.

b) Fish (Friendly Interactive SHell):

Fish is an interactive command shell designed to provide a comfortable user experience and productivity. The main features of Fish include:

    1. Intuitive command autocomplete and syntax highlighting.
    2. Interactive search in the command history, allowing you to easily find previous commands.
    3. Built-in support for themes and styles to customize the appearance of the interpreter.
    4. Extended support for functions and event handlers.    
    5. Flexible configuration of variables and functions without the need to edit configuration files.
    6. Web interface for customizing the appearance and behavior of Fish.
    
Both shells, Zsh and Fish, offer modern features and improvements over traditional shells such as Bash. They provide a more productive work environment and intuitive tools for completing tasks.

Once you have Zsh and Fish installed, you can switch between them and Bash using the following commands:

    - To switch to Zsh: zsh
    - To switch to Fish: fish
    - To return to Bash: exit (or bash if you want to stay in the current session)
    
If you want to change your default shell to one of the installed shells, run the following command:

    - To change to Zsh: chsh -s $(which zsh)
    - To change to Fish: chsh -s $(which fish)
   
After running these commands, you will need to log out of the current session and log back in to see the changes.
    
2. Необхідно створити 10 нових користувачі в вашій системі та розподілити їх по групам:

>Готував студент Кушанов Р.Г.

- Technical support (технічна підтримка, системні адміністратори);
- Developers (розробники, технічні спеціалісти свого профілю);
- Financiers (бухгалтерія, економісти тощо);
- Founders (керівництво);
- Guests (гості).



3. Для кожного з користувачів визначити його командний інтерпретатор за замовчуванням:

>Готував студент Кушанов Р.Г.

- Technical support – bash;
- Developers – командний інтерпретатор 1 (завдання 1);
- Financiers – заборонити доступ до командних інтерпретаторів;
- Founders – командний інтерпретатор 2 (завдання 1);
- Guests – заборонити доступ до командних інтерпретаторів.



4. Продемонструвати приклади роботи кожної групи користувачів у своєму командному інтерпретаторі – наприклад збір відомостей про систему, визначення базової конфігурації, системної дати, поточних каталогів тощо.

>Готував студент Путін М.Г.

Let's show examples of how each user group works in its own command prompt.

Technical support (bash):

Gather information about the system:

      uname -a

Defining the basic configuration:

      lshw

System date:

      date

Current directory:

      pwd

Developers (zsh):

Gather information about the system:

      uname -a.

Defining the basic configuration:

      lshw

System date:

      date

Current directory:

      pwd

Founders (fish):

Collects information about the system:

      uname -a.

Defining the basic configuration:

      lshw

System date:

      date

Current directory:

      pwd


