>Виконали студенти групи РПЗ-03  
>Команда 2:
>
>Кушанов Р.Г.  
>Путін М.Г.  
>Штома Д.О.

1. В робочому середовищі віртуальної машини Virtual Box, VMWare Workstation (або інший на Ваш вибір) необхідно виконати:

>Готував студент Кушанов Р.Г.

  - Клонування вашої віртуальної робочої ОС (Work-case 2). Яким чином це можна зробити? Продемонструйте всі етапи;
  
  ![](https://i.imgur.com/DugCqfn.png)  
  At the first stage, you need to select the "images" section  
  
  ![](https://i.imgur.com/cbaoaT4.png)  
  Next, you need to click on the "Clone" button
  
  ![](https://i.imgur.com/uWFQBVC.png)  
  This screen should have a name for the clone and a path for its location
  
  ![](https://i.imgur.com/RXrhS88.png)  
  Next, you need to select the type of cloning
  
  ![](https://i.imgur.com/Ppd4taL.png)  
  And then wait for the cloning to finish
  
  ![](https://i.imgur.com/ZLTecVT.png)  
  The system clone will appear in the list of available systems
  
  
  - Може виникнути необхідність перенесення (клонування) ОС у інше віртуальне середовище. Які треба виконати дії для експорту вашої віртуальної робочої ОС?
  
  ![](https://i.imgur.com/YkT41kS.png)  
  From the File menu, select "Export Configurations"
  
  ![](https://i.imgur.com/sc08qwh.png)  
  In the window that appears, select the system to export
  
  ![](https://i.imgur.com/nWfYXRC.png)  
  Next, choose a location
  
  ![](https://i.imgur.com/R1lJ4Uk.png)  
  In this menu click "done"
  

2. В ході роботи одна робоча віртуальна машина може взаємодіяти з іншою. Для цього необхідно між ними розгорнути мережу. Опишіть які типи організації мережевих з’єднань підтримуються в середовищі віртуальних машин, в чому особливість кожного з них:

>Готував студент Путін М.Г.

  - Трансляція мережевих адрес (NAT):  
  NAT (Network Address Translation) network allows virtual machines to communicate with the external network, but not with each other. This is useful when you want to isolate virtual machines from each other while still providing them with internet access.
  - Мережевий міст (Bridged):
    This type of network connection allows virtual machines to communicate with the external network and other machines on the same network as the host machine. In a bridged network, the virtual machine is connected to the physical network adapter of the host machine, which allows it to use the same network as the host.
  - Віртуальний адаптер хоста (Host-only):  
    This is a private network that only allows communication between the virtual machines and the host machine. Host-only networks are useful when you want to test network configurations or services without exposing them to the outside world.
  - Внутрішня мережа (Internal Network):  
    This type of network connection only allows communication between virtual machines on the same host machine. It does not allow communication with the external network or the host machine.  
      
    Each type of network connection has its own unique features and use cases, depending on the specific needs of the virtual machine environment. Host-only networks are useful for testing and development, while bridged networks are useful for production environments where virtual machines need access to the external network. NAT networks are useful for providing internet access to virtual machines while maintaining isolation, and internal networks are useful for creating private networks between virtual machines on the same host.
 
3. Розгорніть мережу між вашою робочою ОС та її клоном (завдання 1):

>Готував студент Кушанов Р.Г.

  - Продемонструйте базові команди для налаштування мережевих параметрів ОС, поясніть, що вони виконують.

    ![](https://i.imgur.com/dZUkh3c.png)    
    ![](https://i.imgur.com/573btCd.png)  
    Both vital machines have two adapters, 1 for internet access, the other for LAN communication

  - Обидві ОС мають мати вихід у мережу Інтернет. Відкрийте браузер та перегляньте будь-яке відео в youtube

    ![](https://i.imgur.com/1vqQi6n.png)  
    Both machines have Internet access

  - Налаштуйте та продемонструйте обмін повідомленнями між двома ОС по локальній мережі. Які команди в терміналі при цьому необхідно ввести?
    
    ![](https://i.imgur.com/Ef0fNv3.png)  
    Для обмена сообщениями необходимо на одной машине начать слушать ip4 аддресс с нужним портом, а на другой открыть этот порт для передачи данних
    
  - Налаштуйте спільну мережеву папку для обох ОС. Спробуйте скопіювати файли з цієї директорії в домашній каталог користувача (віртуальна робоча ОС) та на робочій стіл (клон віртуальної робочої ОС).

    ![](https://i.imgur.com/WxYpfgJ.png)  
    To create a shared directory, you need to create a folder, and select "local network share" in the context menu
    
    ![](https://i.imgur.com/aILj8Ei.png)
    On another machine, in the "other locations" section, a folder will appear with the name of the computer from which the shared folder was made
    
    ![](https://i.imgur.com/NEjJsUO.png)  
    I moved the tree picture to a folder
    
    ![](https://i.imgur.com/RzjdMz6.png)
    And she showed up at her original location
 
4. Яким чином можна організувати обмін інформацією між вашою основною ОС (наприклад Windows) та віртуальними ОС? Скопіюйте довільний аудіо-файл з вашої основної ОС на робочий стіл віртуальної ОС та її клона. Як зробити зворотну дію, коли треба документ з робочого столу віртуальної ОС скопіювати до вашої основної робочої ОС?

>Готував студент Штома Д.О.

To organize the exchange of information between the main Windows OS and the Ubuntu virtual OS using Guest Editions, you need to configure the virtual machine by installing Guest Additions. You can do this by going to the Devices menu in the virtual machine window and selecting Insert Guest Additions CD image.
Once Guest Additions is installed, you can use the file and clipboard sharing features. To copy an audio file from the main OS to the Ubuntu virtual OS desktop, you need to open the folder containing the audio file on the main OS and then copy the file to the clipboard (by right-clicking and selecting "Copy" or using the keyboard shortcut Ctrl+C).
Then open the Ubuntu virtual OS and go to the desktop. Right-click and select "Paste" or use the keyboard shortcut Ctrl+V to paste the audio file from the clipboard to the desktop of the virtual OS.
To copy a document from the virtual OS desktop to the main Windows OS, you need to open the folder where the document is stored on the virtual OS, copy the file to the clipboard, and then switch to the main OS and paste the file from the clipboard into the desired folder on the main OS. To do this, you can open the folder on the main OS and right-click, select "Paste" or use the keyboard shortcut Ctrl+V.

Step 1 : Go to the settings
![](https://i.imgur.com/dMRxa7F.png)  

Step 2: Сreate a shared folder
![](https://i.imgur.com/rt4o2TZ.png)  

Step 3: Аdd Guest Additions
![](https://i.imgur.com/LlmjgPH.png)  

Unfortunately, due to an error, I cannot demonstrate the result of performing ooperations :(
Next, we would have to unzip and install Guest Additions, after which a shared chars folder would appear on the main and secondary operating system to exchange files.


