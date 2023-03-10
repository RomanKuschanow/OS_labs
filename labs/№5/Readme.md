“Київський фаховий коледж зв’язку”  
Циклова комісія Комп’ютерної інженерії

## ЗВІТ ПО ВИКОНАННЮ
## ЛАБОРАТОРНОЇ РОБОТИ №5
>з дисципліни:  
>«Операційні системи»

>**Тема:** 
>“Знайомство з командами навігації по файловій системі та керування файлами та каталогами”

>**Виконали студенти групи РПЗ-03**  
>**Команда 2:**
>- Кушанов Р.Г.
>- Путін М.Г.
>- Штома Д.О.

>**Перевірив викладач**  
>Сушанова В.С.

>**Мета роботи**:
>1. Отримання практичних навиків роботи з командною оболонкою Bash.
>2. Знайомство з базовими командами навігації по файловій системі.
>3. Знайомство з базовими командами для керування файлами та каталогами.

>**Матеріальне забезпечення занять**
>1. ЕОМ типу IBM PC.
>2. ОС сімейства Windows (Windows 7).
>3. Віртуальна машина – Virtual Box (Oracle).
>4. Операційна система GNU/Linux – CentOS.
>5. Сайт мережевої академії Cisco netacad.com та його онлайн курси по Linux


***

### Завдання для попередньої підготовки.
1. Прочитайте короткі теоретичні відомості до лабораторної роботи та зробіть невеличкий словник базових англійських термінів з питань призначення команд та їх параметрів.

>Готував студент Кушанов Р.Г.

| Термін англійською | Термін українською |
|:-------------------|-------------------:|
|Store               |Зберігати           |
|Data                |Інформація          |
|Directories         |Каталоги            |
|Hierarchy           |Ієрархія            |
|Filesystem          |Файлова система     |
|Configuration       |Конфігурація        |
|Represent           |Представляти        |
|Destination         |Місце призначення   |
|Interactive         |Інтерактивний       |
|Multiple            |Множинний           |

2. Дайте відповіді на наступні питання:
  
  >Готував студент Кушанов Р.Г.
  
  - Порівняйте файлові структури Windows-подібної та Linux-подібної системи.


    - Windows file names can contain up to 255 characters and can include spaces and special characters. In Linux, file names are case-sensitive, can contain up to 255 characters, and cannot contain spaces.

    - Windows assigns a drive letter (C:, D:, etc.) to each storage device, whereas Linux treats all devices as part of the file system hierarchy.

    - In Windows, file extensions are used to indicate the file type, such as .docx for a Microsoft Word document. In Linux, file extensions are optional, and file type is determined by the file's contents.

    - Windows uses a hidden attribute to hide files from view, whereas Linux uses a dot (.) at the beginning of the file name to indicate that the file is hidden.

    - In Windows, system files are typically located in the Windows directory, whereas in Linux, system files are located in specific directories, such as /bin or /etc.

    - In Linux, each file has a set of permissions that determines who can read, write, or execute the file. Windows also has file permissions, but they are more limited and less granular than Linux permissions.
  
  - Розкрийте поняття FHS. Як даний стандарт використовується в контексті файлових систем?
  
    FHS stands for the Filesystem Hierarchy Standard, which is a set of guidelines that define the directory structure of Linux and other Unix-like operating systems. The FHS was created to establish a uniform file system structure across different Linux distributions and to ensure that applications and system services can find necessary files in predictable locations.

    Following the FHS guidelines ensures that applications and services can find the files and libraries they need in a consistent and predictable location. This makes it easier to manage and maintain Linux systems, and helps ensure compatibility across different Linux distributions.
  
  - Перерахуйте основні команди для роботи з файлами та каталогами в Linux: створення, переміщення, копіювання, видалення.

    - `ls` - This command lists the files and directories in the current directory.
    - `cd` - This command changes the current working directory.
    - `pwd` - This command prints the current working directory.
    - `mkdir` - This command creates a new directory.
    - `rm` - This command removes a file or directory.

### Хід роботи

1. Опрацюйте всі приклади команд, що представлені у лабораторних роботах курсу NDG Linux Essentials-Lab 7: Navigating the Filesystem та Lab 8: Managing Files and Directories. Створіть таблицю для опису цих команд

>Готував студент Путін М.Г.

|Назва команди|Її призначення та функціональність|
|:------------|:---------------------------------|
|pwd          |Визначає місце знаходження користувача у файловій системі, показує поточну робочу директорію (print working directory)|
|cd Documents |Команда cd здійснює перехід до каталогу, який у неї вказаний як аргумент. В даному випадку це каталог Documents|

2. Робота в в терміналі (закріплення практичних навичок)

>Готував студент Путін М.Г.

- Визначте ваш поточний робочий каталог;
- Перейдіть до кореневого каталогу та визначте Ваш поточний робочий каталог (дві команди);
- Перегляньте вміст поточного каталогу у довгому форматі (скористайтесь відповідним ключем команди ls);
- Перейдіть до каталогу /usr/share та визначте Ваш поточний робочий каталог (дві команди)
- Перегляньте вміст поточного каталогу включаючи і приховані файли (hidden files)(скористайтесь відповідним ключем команди ls);
- Перейдіть до каталогу /etc;
- Перегляньте вміст даного каталогу, але щоб виводило тільки назви файлів, що починаються з літери вашого імені;
- Перегляньте вміст даного каталогу, але щоб виводило тільки файли, назви яких складаються з 6 літер;
- Перегляньте вміст даного каталогу, але щоб виводило тільки файли, назви яких закінчуються на літери ваших імен, наприклад якщо ваші імена Ivan, Anna, Maks, то вибірку робиму, щоб назви файлів закінчувались на літери [i,a,m];
- Перейдіть до домашнього каталогу поточного користувача та перегляньте його вміст у рекурсивному (зворотному до алфавітного) форматі (виконати цю дію через конвеєр команд);
- В поточній директорії створити директорію з назвою вашої групи;

>Готував студент Штома Д.О.

- Переглянути оновлений вміст домашнього каталогу поточного користувача. Скористайтесь ключем -r команди ls, яку інформацію ви отримаєте?
- Перейдіть у створену вами директорію з назвою Вашої групи та створіть у ній порожній файл
lab5
- Створити в даній директорії 3 директорії з прізвищами студентів вашої команди surname1, surname2, surname3* (команда mkdir мульти аргумента, тому всі три каталоги можна створити однією командою);
- Перейдіть у перший підкаталог surname1 та створіть порожній файл з ім'ям першого студента name1;
- За допомогою команди echo &quot;Hello, my name is Name1&quot; &gt; name1 внесіть у цей файл дані про
студента (символ &gt; дозволяє вивід команди echo перенаправити одразу у файл name1;
- Перегляньте вміст файлу name1 за допомогою команди cat name1 (має містити щойно введену Вами інформацію)
- Зробіть копію першого файлу name1 та перейменуйте її у файл з другим ім&#39;ям студенту Вашої команди name2;
- Перегляньте вміст каталогу, обидва файли мають з&#39;явитися;
- Перегляньте вміст другого файлу cat name2 (він має поки що містити повну копію вмісту файлу name1)
- Замініть зміст файлу name2, щоб він містив відповідне ім&#39;я другого студента за допомогою команди echo &quot;Hello, my name is Name2&quot; &gt; name2
- Перегляньте вміст другого файлу cat name2 (він вже має містити оновлену інформацію)
- Перемістіть файл name2 у директорію surname2;
- Зробіть копію першого файлу name1 та перейменуйте її у файл з третім ім&#39;ям студенту Вашої команди name3;
- Перемістіть файл name3 у директорію surname3;
- Перейдіть до директорії surname3;
- Перегляньте вміст третього файлу командою cat name3 (він має містити дані про другого
студента)
- Замініть зміст файлу name3, щоб він містив відповідне ім&#39;я третього студента за допомогою команди echo &quot;Hello, my name is Name3&quot; &gt; name3
- Перегляньте вміст файлу за допомогою cat name3 (він вже має містити оновлену інформацію)
- Поверніться до домашнього каталогу користувача;
- Перегляньте вміст даного каталогу, але щоб виводило тільки Ваш підкаталог з назвою групи та весь його вміст (підкаталоги surname1, surname2, surname3 та файли name1, name2, name3) до того ж файли та катлоги були відкоремлені кольорами (скористайтесь відповідним ключем -R команди ls та не забудьте використати спеціальний glob-шаблон [імя каталогу]*)

3. Опишіть дії, які виконують команди для переміщення по системі каталогів:

>Готував студент Кушанов Р.Г.

  - команда `cd /`

    This command changes the current working directory to the root directory of the file system. This is the top-level directory that contains all other directories and files.
  
  - команда `cd /home`

    This command changes the current working directory to the "home" directory. This is the directory where user home directories are typically located.
  
  - команда `cd ~`

    This command changes the current working directory to the current user's home directory. The tilde (~) represents the user's home directory.
  
  - команда `cd` (без аргумента)

    This command changes the current working directory to the user's home directory.
  
  - команда `cd ..`

    This command moves the current working directory up one level in the directory hierarchy.
  
  - команда `cd ../..`

    This command moves the current working directory up two levels in the directory hierarchy.
  
  - команда `cd`

    This command changes the current working directory to the user's home directory. It is equivalent to `cd ~`.

### Контрольні запитання

>Готував студент Кушанов Р.Г.

1. Як можна переглянути шлях до домашньої директорії користувача за допомогою команди echo? Існує 2 способи, наведіть обидва приклади у терміналі

  ![](https://i.imgur.com/DivcNIx.png)

2. Чи можна переглянути вміст кореневого каталогу, перебуваючи у домашньому каталозі користувача без переходу у кореневий каталог? Продемонструйте це в командному рядку.

  ![](https://i.imgur.com/L04gPtZ.png)

3. Яким чином в терміналі можна додати інформацію в порожній файл?

  `echo "This is some information to add to the file" > filename.txt`

4. Як скопіювати та видалити існуючий каталог? Чи буде відмінність в командах, якщо каталог буде не порожній при цьому

  - `cp source_directory target_directory` to copy an empty directory
  - `cp -r source_directory target_directory` to copy a non-empty directory
  - `rmdir directory_name` to removing an empty directory
  - `rm -r directory_name` to remove a non-empty directory

5. У якому з наведених нижче прикладів відбувається переміщення файлу? його перейменування? одночасно обидві дії?
  - `mv /work/tech/comp.png. /Desktop` – moving
  
  - `mv /work/tech/comp.png. /work/tech/my_car.png` – renaming
  - `mv /work/tech/comp.png. /Desktop/computer.png` – moving and renaming

>Висновок:
>
>>Готував студент Штома Д.О.
>

