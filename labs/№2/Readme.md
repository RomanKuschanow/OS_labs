“Київський фаховий коледж зв’язку”  
Циклова комісія Комп’ютерної інженерії

## ЗВІТ ПО ВИКОНАННЮ
## ЛАБОРАТОРНОЇ РОБОТИ №2
>з дисципліни:  
>«Операційні системи»

>**Тема:**
>“Знайомство з інтерфейсом та можливостями ОС Linux”

>**Виконали студенти групи РПЗ-03**  
>**Команда 2:**
>- Кушанов Р.Г.
>- Путін М.Г.
>- Штома Д.О.

>**Перевірив викладач**  
>Сушанова В.С.

>**Мета роботи**:
>1. Знайомство з інтерфейсами ОС Linux.
>2. Отримання практичних навиків роботи в середовищах ОС Linux та мобільної ОС – їх графічною оболонкою, входом і виходом з системи, ознайомлення зі структурою робочого столу, вивчення основних дій та налаштувань при роботі в системі

>**Матеріальне забезпечення занять**
>1. ЕОМ типу IBM PC.
>2. ОС сімейства Windows (Windows 7).
>3. Віртуальна машина – Virtual Box (Oracle).
>4. Операційна система GNU/Linux – CentOS.
>5. Сайт мережевої академії Cisco netacad.com та його онлайн курси по Linux5. 

***

### Завдання для попередньої підготовки.
1. Прочитайте короткі теоретичні відомості до лабораторної роботи та зробіть невеликий словник базових англійських термінів з питань класифікації віртуальних середовищ.
>Готував студент Штома Д.О.

| Термін англійською   | Термін українською |
|:---------------------|-------------------:|
|||

2. Дайте визначення наступним поняттям:
>Готував студент Путін М.Г.
  - CLI-режим 
    - CLI-mode: CLI stands for "Command Line Interface," which is a type of user interface that allows users to interact with a computer system through typed text commands. CLI-mode refers to a state or mode in which a computer system is operating solely through this type of interface, with no graphical user interface (GUI) components visible. CLI-mode is often used in server administration, software development, and other technical tasks that require fine-grained control over system processes.
  - Термінал на основі графічного інтерфейсу користувача
    - Terminal based on the graphical user interface: A terminal is a program that allows users to access a command-line interface on a computer system. In a graphical user interface (GUI) environment, a terminal program can be used to provide a CLI-mode experience within a window or other graphical element. This type of terminal is often referred to as a "terminal emulator," since it emulates the behavior of a traditional hardware terminal (which was a physical device used to communicate with computer systems in the early days of computing). Terminal programs may offer additional features such as tabs, color coding, and copy/paste functionality.
  - Віртуальний термінал
    - Virtual terminal: A virtual terminal (VT) is a software interface that allows multiple text-mode sessions to run concurrently on a computer system. Each virtual terminal can be thought of as a separate CLI-mode environment, with its own login prompt, command history, and other features. Virtual terminals are often used in Unix-like operating systems such as Linux, where they provide a way for multiple users to access a shared system without interfering with each other's work. In a GUI environment, virtual terminals can be accessed through a terminal emulator program, as described above.
    
### Хід роботи

1. Робота в графічному режимі в ОС сімейства Linux (робота з інтернет-джерелами):
    1.Розгляньте структуру робочого простору користувача Ubuntu, та опишіть основні його компоненти:
    >Готував студент Кушанов Р.Г.

      - Меню Applications: 
      - Меню System
      - Навігаційний простір Activities overview
     
     The Application menu is located in the control panel, and looks like a square with nine dots. If you open it, a menu of installed programs will be expanded. From there, you can open them and add them to the Quick Access panel.
     
     The System menu is located on the right on the top panel, and contains a basic set of functions for system management: shutdown, user lock, system sound control, settings button, power saving and network connection management options.
     
     The Activities tab is located on the top left and allows you to switch workspaces (similar to desktops in Windows)
     
    
    2. Запуск програм. Дослідіть можливості запуску додатків різними способами (описати спосіб і по можливості показати скріншоти):
    >Готував студент Кушанов Р.Г.
    
      - Запуск програм через панель швидкого запуску
      - Запуск програм через пошук в меню
      - Запуск програм через глобальне меню
      
      Перший варіант:  
      Натиснути на іконку потрібної програми та дочекатися завантаження  
      ![Запуск через панель швидкого запуску](https://i.imgur.com/CQ0fF2R.png)
      
      Другий варіант:  
      Ввести у пошук назву програми та натиснути на іконку  
      ![Запуск через пошук в меню](https://i.imgur.com/5g1fzES.png)
      
      Третій варіант:  
      Знайти у меню необхидну програму та натиснути на її іконку  
      ![Запуск через глобальне меню](https://i.imgur.com/lzF6xlz.png)
      
    3. Вихід з системи та завершення роботи в Linux. Як виконати в графічному інтерфейсі наступні дії (наведіть скріни):
    >Готував студент Кушанов Р.Г.
    
      - Зміна користувача на root
      - Перезавантаження системи
      - Вимкнення системи
      
      Для зміни користувача на root у графічній оболонці необхідно прописати декілька команд у консолі. Я вже їх прописав, покажу лише сам процес зміни користувача:  
      Вийти с поточного користувача  
      ![](https://i.imgur.com/ltpXqNM.png)
      
      Натиснути "Not listed?"  
      ![](https://i.imgur.com/QDQ10LP.png)
      
      Ввести "root", та на наступному єкрані пароль  
      ![](https://i.imgur.com/52ocHaX.png)
      
      
      Для перезавантаження системи необхідно натиснути на відповідну клавишу у меню системи:  
      ![](https://i.imgur.com/njtSFLh.png)
      
      
      Для вимкнення системи необхідно натиснути на відповідну клавишу у меню системи:  
      ![](https://i.imgur.com/QQTQWPN.png)
      
2. Робота в середовищі мобільної ОС.
    1. Опишіть головне меню вашої мобільної ОС, який графічний інтерфейс вона використовує?
    >Готував студент Штома Д.О.

    
    
    2. Опишіть меню налаштувань компонентів мобільного телефону.
    >Готував студент Штома Д.О.

    
    
    3. Використання комбінацій клавіш для виконання спеціальних дій.
    >Готував студент Путін М.Г.
    - You can use keyboard shortcuts in TalkBack to use features such as speaking text, navigating the screen, and managing settings. Also, if you connect keyboard to phone and depending on the app, you may be able to use keyboard shortcuts to perform certain actions. For example, in Gmail, you can use the "R" key to reply to an email.
    
    
    4. Вхід у систему та завершення роботи пристрою. Особливості налаштувань живлення батареї.
    >Готував студент Путін М.Г.
    
    To log in to your Android phone, you will need to enter your passcode, pattern, or use biometric authentication, such as fingerprint or facial recognition, depending on how you have set up your device's security features.

    To shut down your Android phone, you can press and hold the Power button until the "Power off" option appears on the screen. Tap the "Power off" option to turn off your device. If your device is unresponsive or frozen, you can try a forced restart by pressing and holding the Power and Volume Down buttons simultaneously for about 10 seconds until the device restarts.

  As for battery power settings, there are several features available in the Android settings that allow you to manage and optimize your device's battery usage:

    Battery Saver: This feature reduces your device's performance and limits background app activity to conserve battery life when the battery level drops below a certain threshold.

    Adaptive Battery: This feature uses machine learning to optimize your device's battery usage by identifying and limiting the activity of infrequently used apps.

    Battery Usage: This option shows you which apps are using the most battery power and allows you to restrict their activity when the screen is off or in the background.

    Battery Optimization: This option allows you to select specific apps that you want to optimize for battery usage.

    Battery Health: This option displays your device's current battery health status and provides recommendations to prolong battery life.
    
>Висновок:
>>Готував студент Штома Д.О.
