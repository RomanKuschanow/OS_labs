>Виконали студенти групи РПЗ-03  
>Команда 2:
>
>Кушанов Р.Г.  
>Путін М.Г.  
>Штома Д.О.

1. В ході роботи досить часто виникає необхідність встановлювати нові програми та додатки. Для цього необхідно в терміналі вміти працювати з менеджерами пакетів:

>Готував студент Путін М.Г.

  - Дайте розгорнуте визначення таким поняттям як «пакет» та «репозиторій».
  - Надайте короткий огляд існуючих менеджерів пакетів у Linux. Охарактеризуйте їх основні можливості.
 
2. Визначте який менеджер пакетів використовує ваш дистрибутив Linux. Опишіть основні команди для роботи з ним:

>Готував студент Штома Д.О.

  In Ubuntu and other Linux distributions that use the APT (Advanced Package Tool) package manager, you can use the following commands to perform the tasks described above:

Search for packages: 
- sudo apt search package_name

Downloading packages: 
- sudo apt download package_name

Installing packages: 
- sudo apt install package_name

Adding a new repository: 
- sudo add-apt-repository repository - sudo apt update

Viewing installed packages:
- dpkg --list

View available packages: 
- sudo apt-cache pkgnames

Remove packages: 
- sudo apt remove package_name 
- sudo apt autoremove

Update the package manager and installed packages:
-sudo apt update -sudo apt upgrade

3. Встановіть у терміналі через менеджер пакетів на свою систему:

>Готував студент Путін М.Г.

  - Новий відео- чи аудіоплейер.
  - Середовище для мови програмування, що ви вивчаєте.

4. Яким чином можна встановити нові програми через магазини додатків та менеджери пакетів у графічному середовищі. Наведіть свої приклади.

>Готував студент Кушанов Р.Г.

![](https://i.imgur.com/Dlh2GLh.png)  
To install packages through the graphical shell, you need to open the "Ubuntu Software" application

![](https://i.imgur.com/BzZFX3s.png)  
Next, click on the search icon

![](https://i.imgur.com/BITqoAS.png)  
And enter the name of the required application

![](https://i.imgur.com/nYQUlTs.png)  
By clicking on the desired application, the page of this application will be displayed, where you can install it by pressing the "Install" button

![](https://i.imgur.com/v8VpOmy.png)  
There is also an option through the terminal: enter the command `apt install <name>`

![](https://i.imgur.com/RXPxQHe.png)  
And to the question "whether to start the installation" we answer `y`
