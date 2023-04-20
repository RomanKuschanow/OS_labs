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

To create new users and assign them to groups, you first need to create the appropriate groups, and then create users and add them to the appropriate groups. Here's how to do it:

Create groups:

      sudo groupadd techsupport
      sudo groupadd developers
      sudo groupadd financiers
      sudo groupadd founders
      sudo groupadd guests

Create users and add them to the appropriate groups:


      # techsupport
      sudo useradd -m -G techsupport user1
      sudo useradd -m -G techsupport user2

      # Developers
      sudo useradd -m -G developers user3
      sudo useradd -m -G developers user4
      sudo useradd -m -G developers user5

      # Financiers
      sudo useradd -m -G financiers user6
      sudo useradd -m -G financiers user7

      # Founders
      sudo useradd -m -G founders user8
      sudo useradd -m -G founders user9

      # Guests
      sudo useradd -m -G guests user10

Set passwords for new users:

      sudo passwd user1
      sudo passwd user2
      sudo passwd user3
      sudo passwd user4
      sudo passwd user5
      sudo passwd user6
      sudo passwd user7
      sudo passwd user8
      sudo passwd user9
      sudo passwd user10
      
Check the groups to which the users belong:

      groups user1
      groups user2
      groups user3
      groups user4
      groups user5
      groups user6
      groups user7
      groups user8
      groups user9
      groups user10

3. Для кожного з користувачів визначити його командний інтерпретатор за замовчуванням:

>Готував студент Кушанов Р.Г.

- Technical support – bash;
- Developers – командний інтерпретатор 1 (завдання 1);
- Financiers – заборонити доступ до командних інтерпретаторів;
- Founders – командний інтерпретатор 2 (завдання 1);
- Guests – заборонити доступ до командних інтерпретаторів.

Use the following commands to set the default command prompt for users. In this example, we are using zsh as command prompt 1 and fish as command prompt 2:

Technical support - bash:

        sudo usermod -s /bin/bash user1
        sudo usermod -s /bin/bash user2
        
Developers - command prompt 1 (zsh):

        sudo usermod -s /bin/zsh user3
        sudo usermod -s /bin/zsh user4
        sudo usermod -s /bin/zsh user5
        
Financiers - deny access to command prompts (use /usr/sbin/nologin to deny entry):

        sudo usermod -s /usr/sbin/nologin user6
        sudo usermod -s /usr/sbin/nologin user7
        
Founders - command prompt 2 (fish):

        sudo usermod -s /bin/fish user8
        sudo usermod -s /bin/fish user9
        
Guests - deny access to command prompts (use /usr/sbin/nologin to deny entry):

        sudo usermod -s /usr/sbin/nologin user10



4. Продемонструвати приклади роботи кожної групи користувачів у своєму командному інтерпретаторі – наприклад збір відомостей про систему, визначення базової конфігурації, системної дати, поточних каталогів тощо.

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


>Готував студент Путін М.Г.
