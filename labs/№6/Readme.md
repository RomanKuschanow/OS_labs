“Київський фаховий коледж зв’язку”  
Циклова комісія Комп’ютерної інженерії

## ЗВІТ ПО ВИКОНАННЮ
## ЛАБОРАТОРНОЇ РОБОТИ №6
>з дисципліни:  
>«Операційні системи»

>**Тема:** 
>“Команди Linux для архівування та стиснення даних. Робота з текстом”

>**Виконали студенти групи РПЗ-03**  
>**Команда 2:**
>- Кушанов Р.Г.
>- Путін М.Г.
>- Штома Д.О.

>**Перевірив викладач**  
>Сушанова В.С.

>**Мета роботи**:
>1. Отримання практичних навиків роботи з командною оболонкою Bash.
>2. Знайомство з базовими командами для архівування та стиснення даних.
>3. Знайомство з базовими діями при роботі з текстом у терміналі.

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
|compress            |            стискати|
|directories         |               папки|
|archiving           |          архівувати|
|formatted           |     відформатований|
|lossless            |           без втрат|
|utility             |          корисність|
|sequential          |         послідовний|
|deflate             |               здути|
|protocol            |            протокол|
|advantages          |            переваги|

2. Дайте відповіді на наступні питання:
  
  >Готував студент Кушанов Р.Г.
  
  - Яке призначення команд `tar`, `xz`, `zip`, `bzip`, `gzip`? Зробіть короткий опис кожної команди та виділіть їх основні параметри. Яким чином їх можна встановити.
  
  These commands are used to archive and compress files
  
  The tar (Tape Archive) command is used to archive files and directories as a single file. Main parameters:

  `-c`: create an archive
  `-x`: unzip the archive
  `-f`: specify the name of the archive file
  `-v`: display the list of files to be archived/unzipped
  
  `tar` is usually installed with the system, but additional features of the command, such as support for different archive formats, can be installed using additional packages.
  
  The xz command is used to compress files. It uses the LZMA compression algorithm, which provides a high level of compression. Main parameters:

  `-c`: output the result to standard output
  `-d`: extract the file
  `-z`: use a gzip-like compression algorithm

  xz is usually installed with the system, but can be installed separately via your OS's package manager.
  
 The `zip` command is used to archive and compress files. It uses the ZIP format, which is one of the most common archive formats in the Windows environment. Main parameters:

  `-r`: recursively add files from subdirectories
  `-u`: update the archive, adding only new files to it
  `-d`: delete file from archive
  
  - Наведіть три приклади реалізації архівування та стискання даних різними командами.
  
  `tar -czvf myfolder.tar.gz myfolder`
  `zip myfile.zip myfile.txt`
  `bzip2 -dk myarchive.bz2`
  
  - Яке призначення команд cat, less, more, head and tail? Зробіть короткий опис кожної команди та виділіть їх основні параметри. Яким чином їх можна встановити
  
  These commands are used to view and edit text files. The main purpose of these commands is to allow the user to view and edit large files without having to open them in an editor.
  
  The command `cat` (Concatenate) is used to output the contents of text files to the console. Main parameters:

  `-n`: output line numbers
  `-s`: merge consecutive empty lines into one
  `-E`: show the end of each line with a $ character
  
  `cat` is usually installed with the system, but can be installed separately via your OS's package manager.
  
  The `less` command is used to view text files, allowing the user to easily navigate through the file. Main parameters:

  `-N`: display line numbers
  `-S`: disable wrapping of lines that do not fit in the window
  `-F`: Automatically exit if the entire file is displayed
  
  `less` is usually installed with the system, but can be installed separately through your OS's package manager.
  
  The more command is similar to `less', but usually less powerful. It is used to gradually output text files to the console. Main parameters:

  `-n`: display line numbers
  `-d`: Wait for a command from the user before going to the next screen
  `-c`: clear the screen before displaying the next screen
  
  `more` is usually installed with the system, but can be installed separately via your OS's package manager.

  The `head` command is used to output the first few lines
  
  - Поясніть принципи роботи командної оболонки з каналами, потоками та фільтрами
  
  The shell in the Linux operating system has built-in support for handling I/O streams and using pipes to transfer data between processes. This allows you to combine different commands to get more complex data processing results.

  Channels allow the output of one command to be passed as input to another command. For example, if we want to list the files in the current directory and sort it alphabetically, we can use the channel | to pass the output of the `ls` command as input to the `sort` command
  
  I/O streams (stdin, stdout, stderr) are standard data streams used to interact with commands on the command line. The shell automatically binds standard input (stdin) to the keyboard, and standard output (stdout) and standard error stream (stderr) to the screen.
  
  - Яке призначення команди grep?
  
  The `grep` (Global Regular Expression Print) command is used to search input data using a specific string or regular expression.

### Хід роботи

1. Опрацюйте всі приклади команд, що представлені у лабораторних роботах курсу NDG Linux Essentials-Lab 9: Archiving and Compression та Lab 10: Working With Text. Створіть таблицю для опису цих команд

>Готував студент Путін М.Г.

| Назва команди | Її призначення та функціональність |
|:--------------|:-----------------------------------|
|`mkdir mybackups`|Створення нової директорії mybackups у домашньому каталозі користувача|
| `tar -cvf mybackups/udev.tar /etc/udev `|Команда tar використовується для об’єднання кількох файлів в один файл. В даному випадку вміст директорії /etc/udev буде збережено в архів udev.tar у директорії mybackups. Параметр -c повідомляє команді tar створити файл tar. Параметр -v означає "verbose", який наказує команді tar продемонструвати, що вона робить. Параметр -f використовується для вказівки назви файлу tar.|
| `tar` | Originally, tar was used to archive data on tape devices. But it also allows you to write the output to a file, and this method has become widely used in Linux for its intended purpose |
| `gzip` | The gzip command is designed for lossless data compression using the utility of the same name, which uses the Lempel-Ziv algorithm (LZ77) with Huffman encoding. The purpose of using this utility is to save disk space. |
| `bzip2` | The bzip2 command is designed to compress data without loss using a utility that uses the Barrows-Wheeler algorithm. The purpose of using this utility is to save disk space. |
| `xz` | the XZXZ Utils command is a tool for developing high compression ratios for the POSIX platform |
| `unzx` | command in Linux terminal is used to extract files from archives created by zx |
| `zip` | This command includes only files ending in .c in the current directory and its subdirectories. |
| `unzip` | Unzip files from the ZIP archive (a / s) (you can specify several through a space |
| `>` | Used to redirect the `stdout` from first command to rewrite the file |
| `>>` | Used to redirect the `stdout` from first command to append the new output in the end of file |
| find | command starts the search in the directory specified and recursively search all of the subdirectories. |
| `2>` | Used to redirect the `stderr` error message to a file |
| `tr` | Used to translate the characters |
| `cut` | Used to extract specific columns or fields of text from a file or input stream. |
| `more` and `less`| Allows for the user to the view data a "page" or a line at a time. |
| `head` | Used to display the top part of a file. By default, the head command will display the first ten lines of the file |
| `tail` | displays the last ten lines of the file |
| `grep` | Will print the entire line containing the match in file, that given by an argument, that can use some of regular expressions|
| `egrep` | Will print the entire line containing the match in file, that given by an argument, that can use all parts of regular expressions |

2. Ознайомтесь з командою tar та за її допомогою виконати у терміналі наступні дії:

>Готував студент Путін М.Г.

  - створити файл з розширенням .tar;
  - створити файл з розширенням .tar, що складається з декількох файлів і каталогів одночасно;
  - перегляду вмісту файлу;
  - витягти вміст файлу tar;
 ![Alt Text](./img/img_1.png?raw=true "Optional Title")
  - створити архівний файл tar, стиснений за допомогою bzip;
  - витягти вміст файлу tar bzip;
  ![Alt Text](./img/img_2.png?raw=true "Optional Title")
  - створити архівний tar файл, стисненого за допомогою gzip;
  - витягти вміст файлу tar gzip.
  ![Alt Text](./img/img_3.png?raw=true "Optional Title")

3. Як буде відбуватись перенаправлення потоків виведення в bash для наступних дій з командами
(позначено як cmd) та файлами (позначено як file):

>Готував студент Штома Д.О.

|Команда             | Що виконує команда?                |
|:-------------------|:-----------------------------------|
|cmd 1> file         |Команда записує виведення в файл file, переписуючи вміст файлу.|
|cmd > file          |Команда записує виведення в файл file, переписуючи вміст файлу. Ця команда еквівалентна команді cmd 1> file.|
|cmd 2> file         |Команда записує помилки в файл file, переписуючи вміст файлу.|
|cmd >> file         |Команда додає виведення в кінець файлу file.|
|cmd &> file         |Команда записує і виведення, і помилки в файл file, переписуючи вміст файлу. Ця команда еквівалентна команді cmd > file 2>&1.|
|cmd > file 2>&1     |Команда перенаправляє виведення в файл file і помилки в той же самий файл. Ця команда еквівалентна команді cmd &> file.|
|cmd >> file 2>&1    |Команда додає виведення і помилки в кінець файлу file.|
|cmd 2>&1 > /dev/null|Команда перенаправляє помилки на stdout і затем відхиляє (відправляє в нікуди) виведення.|
|cmd 2> /dev/null    |Команда відправляє помилки в нікуди.|
|cmd1 \| cmd2        |Команда передає виведення з cmd1 у вхід cmd2.|
|cmd1 2>&1 \| cmd2   |Команда перенаправляє і виведення, і помилки з cmd1 на stdout і передає їх як вхід у cmd2.|

4. Розгляньте наведені нижче приклади та поясніть, що виконують дані команди та який тип перенаправлення потоків вони використовують:

>Готував студент Штома Д.О.

|Команда (контейнер команд)| Що виконує команда?|Який потік перенаправлення?|
|:-------------------------|:-------------------|:--------------------------|
|$echo "It is a new story." > story|Записує рядок "It is a new story." в файл з іменем "story".|>|
|$ date > date.txt|Записує поточну дату та час в файл з іменем "date.txt".|>|
|$ cat file1 file2 file3 > bigfile|Об'єднує вміст трьох файлів (file1, file2, file3) в файл з іменем "bigfile".|>|
|$ls -l >> directory|Додає вміст виведення команди ls -l в кінець файлу з іменем "directory"|>>|
|$ sort < file1_unsorted > file2_sorted|Сортує вміст файлу "file1_unsorted" та записує його в файл з іменем "file2_sorted".|<, >|
|$ find -name '*.txt' > file.txt 2> /dev/null|Знаходить всі файли з розширенням .txt та записує їх імена в файл з іменем "file.txt". Перенаправляє потік помилок (stderr) в нікуди.|>, 2> (stderr перенаправляється в /dev/null)|
|$ cat file1_unsorted \| sort > file2_sorted|Сортує вміст файлу "file1_unsorted" та записує його в файл з іменем "file2_sorted".|`|
|$ cat myfile \| grep student \| wc -l|Зчитує вміст файлу "myfile", знаходить рядки, які містять слово "student" та обчислює їх кількість.|`|


### Контрольні запитання

>Готував студент Кушанов Р.Г.

1. Надайте порівняльну характеристику процесам стискання та архівування.

  Archiving is the process of creating a single file that contains multiple files or directories. Archiving is typically used to store or transfer a group of files in order to preserve their structure and relationships between them.
  
  Compression is the process of reducing the size of a file or data by removing redundant information. Compression can be lossless or lossy.

2. Які програми, окрім наведених в роботі, можуть використовуватись для стискання та архівування файлів та каталогів в ОС Linux? Наведіть приклади та їх короткий опис.

  `7zip` is an open source program that supports many compression and archiving formats, including 7z, ZIP, TAR, and WIM. It has a high degree of compression and can work with encrypted archives.

  `PeaZip` is an open source program that supports many compression and archiving formats, including 7z, ZIP, TAR, GZ, and XZ. It has a graphical user interface and can be used to create archives, unpack and view their contents.

  `rar` is a program for compressing and archiving files that supports the RAR format. It has a high degree of compression and can work with encrypted archives.

3. Порівняйте алгоритми стискання, що використовуються в командах (програмах), використовуваних в Linux. Які з алгоритмів можна вважати найшвидшим та найефективнішим?

|Алгоритм стискання|Швидкість|Ступінь стиснення  |Використання ресурсів|
|:-----------------|:--------|:------------------|:--------------------|
|gzip              |Швидкий  |Низький            |Низьке               |
|bzip2             |Помірний |Високий            |Високе               |
|xz                |Повільний|Надзвичайно високий|Високе               |

>Висновок:
>>Готував студент Кушанов Р.Г.
>
>In this lab, we learned about the existing ways to compress and archive files in Linux, and tried them out in practice.

