>Виконали студенти групи РПЗ-03  
>Команда 2:
>
>Кушанов Р.Г.  
>Путін М.Г.  
>Штома Д.О.

1. При роботі з персональним комп’ютером дуже часто виникає необхідність підключати периферійне обладнання. На прикладі принтера та флешки опишіть який механізм має ОС Linux для роботи з ними.

>Готував студент Штома Д.О. та Путін М.Г.

  - В чому суть операції монтування, для чого вона використовується та як?
  
  The Linux operating system has built-in support for peripherals such as printers and flash drives. When you connect a Linux-supported peripheral, the operating system automatically recognizes it and displays a message.
To work with a printer in Linux, you need to install the printer driver and configure it. For this purpose, special programs such as CUPS (Common Unix Printing System) are used. Once the driver is configured, the printer can be used to print documents.

  When working with a flash drive in Linux, you must first connect it to your computer. After that, Linux automatically recognizes the flash drive and mounts it, i.e., connects it to the file system so that it can be used as a regular disk. The files on the flash drive can be viewed and copied in the same way as regular files on a computer.

  Mounting is the process of connecting an external device to the operating system. After connecting the device, the operating system mounts it to the system file system, i.e. adds it to the directory tree that can be viewed and edited using a file manager or terminal.
Mounting is used to provide access to an external device from the operating system and to enable you to work with files on that device.


  - В чому різниця при роботі з периферією у ОС Linux та ОС Windows?
 
 In Linux and Windows, the difference in working with peripherals is how the operating systems handle the connection of external devices. In Linux,   connecting peripherals is faster and more reliable because the system automatically recognizes and mounts the device. In Windows, you need to install drivers and additional programs to work with some devices.
 
  Linux also has a more flexible system of permissions for accessing files and folders on peripherals, which allows for a higher level of data security. In     Windows, connecting peripherals can be slower and less reliable, which can lead to data loss and problems with the devices.
  In addition, Linux has a wider range of programs and tools for working with peripherals and file systems. For example, Linux has a built-in tool for        cloning and creating disk images, which allows you to work conveniently with removable media. In Windows, you need to install additional software to work     with disk images.

  To summarize, Linux and Windows operating systems have differences in working with peripherals. Linux provides faster and more reliable device  connectivity, as well as more flexible settings for permissions to access files and folders on peripherals. Windows may experience problems with connection   speed and reliability, and may have limitations on certain types of devices and file systems.
 
2. Підключіть до вашої віртуальної машини зі встановленою ОС Linux флешку та принтер (за можливості) та через графічний інтерфейс скопіюйте один файл з флешки на віртуальну машину та роздрукуйте його (такі ж самі дії повторіть, але з іншим файлом через команди в терміналі).

>Готував студент Кушанов Р.Г.

![](https://i.imgur.com/KC7l4AI.png)

To access the virtual machine to an external device, you need to select the desired devices in the usb settings, then it will be possible to access them from the child system

![](https://i.imgur.com/mDY8xvd.png)

Similarly, you can view the contents through the terminal
