>Виконали студенти групи РПЗ-03  
>Команда 2:
>
>Кушанов Р.Г.  
>Путін М.Г.  
>Штома Д.О.

1. Встановіть на своїй домашній робочій станції гіпервізор ІІ типу – Virtual Box, VMWare Workstation, Hyper-V (або інший на Ваш вибір).

    1) Download an Ubuntu image
    2) Download and install VirtualBox
    
>Готував студент Путін М.Г.


2. Опишіть набір базових дій в встановленому Вами гіпервізорі:

>Готував студент Путін М.Г.

- Створення нової віртуальної машини;

  1) To create a new virtual we need to click on "create"
  ![Alt Text](./screenshots/img_1.png?raw=true "Optional Title")
  
  2) Enter the name and select the Ubuntu image we downloaded
  ![Alt Text](./screenshots/img_2.png?raw=true "Optional Title")

- Вибір/додавання доступного для віртуальної машини обладнання;

  After installing, we need to right click on our virtual to go the settings and in this menus we can select everything we need to select or add for our virtual
  
  ![Alt Text](./screenshots/img_3.png?raw=true "Optional Title")
  
- Налаштування мережі та підключення до точок Wi-Fi;

  In settings we can go to menu "network" and select "enable network adapter"
  ![Alt Text](./screenshots/img_4.png?raw=true "Optional Title")

- Можливість роботи з зовнішніми носіями (flash-пам’ять).

  For external media, we also need to go into settings and select the usb-port that is available.
  ![Alt Text](./screenshots/img_5.png?raw=true "Optional Title")


3. Встановіть в вашому гіпервізорі операційну систему GNU/Linux CentOS (або інший зручний Вам дистрибутив) у базовій конфігурації з графічною оболонкою.

>Готував студент Кушанов Р.Г.

I installed Ubuntu 20.04.1 LTS on my virtual machine. To do this, you need to go to the official ubuntu website and download the Ubuntu Desktop image. Then, when you create a new virtual machine, you need to choose a pre-booted image, and the rest of the settings are made as you wish. Next, you need to wait for the installation. Once the new OS is set up, you need to update the packages. To do this, press Ctrl+Alt+F3/F4/F5/F6/F7 to launch the virtual console and enter the commands apt-get update and apt-get upgrade

![update](https://i.imgur.com/RZz73Az.png)

After that, press Ctrl+Alt+F1/F2 to return to the graphical interface. Now you can use the visual terminal (in my case, before these operations, the visual terminal did not start at all)

4. Створіть другу віртуальну машину та виконайте для неї наступні дії:

>Готував студент Штома Д.О.

- Встановіть у мінімальній конфігурації з термінальним вводом-виводом без графічного інтерфейсу операційну систему GNU/Linux CentOS ;

This was demonstrated above.

- Встановіть графічну оболонку GNOME поверх встановленої в попередньому пункті ОС;

 ![Alt Text](./img/img_1.jpg?raw=true "Optional Title")
 
 ![Alt Text](./img/img_2.jpg?raw=true "Optional Title")
 
 ![Alt Text](./img/img_3.jpg?raw=true "Optional Title")
 
 ![Alt Text](./img/img_4.jpg?raw=true "Optional Title")
 
- Встановіть додатково ще другу графічну оболонку (їх можливий перелік можна знайти в лабораторній роботі №1) та порівняйте її можливості з GNOME. 

I installed KDE Plasma as an example.

 ![Alt Text](./img/img_5.jpg?raw=true "Optional Title")
 
 ![Alt Text](./img/img_6.jpg?raw=true "Optional Title")
 
 ![Alt Text](./img/img_7.jpg?raw=true "Optional Title")
 
 GNOME and KDE Plasma are two of the most popular graphical desktop environments in the Linux environment. Both of them have their advantages and disadvantages, but there is no better one, as each of them depends on the user's requirements and personal preferences.

 GNOME is a simple, user-friendly and ergonomic shell with a clean and minimalistic interface. It has many useful features, such as a notification system, search function, multi-touch, and much more. GNOME also has the largest number of extensions that allow users to customize the shell to their liking.

 KDE Plasma is a shell with a lot of features and customization. It allows users to customize the shell to their liking, has a large number of controls, and allows them to work with multiple desktops simultaneously. KDE Plasma also comes with built-in applications such as a terminal, text editor, and Google Account.

