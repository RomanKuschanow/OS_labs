“Київський фаховий коледж зв’язку”  
Циклова комісія Комп’ютерної інженерії

## ЗВІТ ПО ВИКОНАННЮ
## ЛАБОРАТОРНОЇ РОБОТИ №1
>з дисципліни:  
>«Операційні системи»

> **Тема:** Знайомство з робочим середовищем віртуальних машин та особливостями операційної системи Linux

>**Виконали студенти групи РПЗ-03**  
>**Команда 2:**
>- Кушанов Р.Г.
>- Путін М.Г.
>- Штома Д.О.

>**Перевірив викладач**  
>Сушанова В.С.

>**Мета роботи**:
>1. Знайомство з гіпервізорами різного типу, віртуалізацією при роботі з операційними системами.
>2. Знайомство з основними видами сучасних ОС, короткий огляд їх можливостей.

>**Матеріальне забезпечення занять**
>1. ЕОМ типу IBM PC.
>2. ОС сімейства Windows (Windows 7).
>3. Віртуальна машина – Virtual Box (Oracle).
>4. Операційна система GNU/Linux – CentOS.
>5. Сайт мережевої академії Cisco netacad.com та його онлайн курси по Linux5. 

***

### Завдання для попередньої підготовки.
1. Прочитайте короткі теоретичні відомості до лабораторної роботи та зробіть невеликий словник базових англійських термінів з питань класифікації віртуальних середовищ.
>Таблиця доповнювалася кожним зі студентів команди

| Термін англійською   | Термін українською |
|:---------------------|-------------------:|
|shared hosting        |спільний хостинг    |
|machine simulator     |машинний емулятор   |
|binary translation    |бінарний транслятор |
|hipervizor            |гіпервізор          |
|host operating system |головна ОС          |
|guest operating system|гостьова ОС         |
|kernel                |ядро                |
|distibution           |розподілення        |
|embrace               |надбудова           |

2. Прочитавши матеріал з коротких теоретичних відомостей дайте відповіді на наступні питання:
    1. Охарактеризуйте поняття «гіпервізор». Які бувають їх типи?
    > Готував студент Путін М.Г.
    
    A **hypervisor** is a computer program or processor hardware that provides simultaneous and parallel execution of several virtual machines, each of which runs its own operating system, on one physical computer
    
    - Offline hypervisor 
      - A standalone hypervisor is booted with a bootloader or firmware, and runs configured operating systems in separate virtual machines. 
      - Examples: VMware ESX, PR/SM.
    
    - Based on the underlying OS
      - This is a component that runs in the same ring as the kernel of the underlying OS. The guest code can run directly on the physical processor, but access to the I/O devices of the computer from the guest OS is through a second component, a normal process of the main OS - the user-level monitor.
      - Examples: Windows Virtual PC, VMware Workstation, QEMU, Parallels, VirtualBox, OVirt.
    
    - Hybrid 
      - A hybrid hypervisor consists of two parts: a thin hypervisor that controls the processor and memory, and a special service OS in a lower-level ring that runs under the hypervisor. Through the service OS, guest OSes access the physical hardware.
      - Examples: Microsoft Virtual Server, Sun Logical Domains, Xen, Citrix XenServer, Microsoft Hyper-V.

    
    2. Перерахуйте основні компоненти та можливості гіпервізорів відповідно до свого варіанту (порядковий номер по журналу), табл.1.
    >Готував студент Кушанов Р.Г.
    
    VirtualBox is a powerful hypervisor that has many advantages over other hypervisors. The main ones are openness, cross-platform compatibility and a large number of customizations.
    
    The main features of VirtualBox:
    - selection of a system image for installation
    - flexible configuration of the method and location of storing virtual machine files
    - the ability to run multiple machines simultaneously
    - customize the display of virtual monitors

    
### Хід роботи
1. Подивіться ознайомчі відео та демонстраційні матеріали з наступних напрямків:
    1. [GNU/Linux. Базові відомості.](https://www.youtube.com/watch?v=k4AKMLS2Ac8)
    2. [Встановлення CentOS у VirtualBox.](https://www.youtube.com/watch?v=W3XTYYoHe9A)
    3. [Встановлення CentOS в текстовому режимі.](https://www.youtube.com/watch?v=gOR-1o3K18Q)
    4. [Встановлення оточення робочого столу Gnome в CentOS.](https://www.youtube.com/watch?v=gcEiIH3KF4Y)
    5. [Встановлення оточення робочого столу KDE в CentOS.](https://www.youtube.com/watch?v=_ruIWLExaOY)
    6. [The Shell (Linux)](https://drive.google.com/open?id=0B0PV0_SM0LoDSVNPWUVRdUxaN2s)
    7. [Огляд графічних оболонок Linux](https://www.youtube.com/watch?v=lEGplwLXZ78)
    
2. Після перегляду відео дайте відповіді на наступні питання.
    1. Перерахуйте етапи для розгортання операційної системи на базі віртуальної машини VirtualBox.
    >Готував студент Кушанов Р.Г.
    
    Stages of deploying an operating system on VirtualBox:
    - Download the image of the desired system
    - In the hypervisor, click the "Create" button
    - Select "Expert mode" at the bottom
    - In the "OS name and type" section, specify the image, system type, version and storage location on the host system
    - In the "Automatic installation" section, optionally specify the data of the future OS user
    - In the "Hardware" section, set the desired system resource limits
    - In the "Hard disk" section, specify the maximum size and location of the OS disk file
    - Click "Finish" and wait for the installation
    
    2. Чи є якісь апаратні обмеження при встановленні 32- та 64-бітних ОС?
    >Готував студент Путін М.Г.
    
    You can install both 32-bit and 64-bit OS on a 32-bit processor
    There are restrictions on a 64-bit processor, because you can only install a 64-bit OS on it, the processor is simply not capable of supporting lower bit depths
    
    3. Які основні етапи при встановленні CentOS в текстовому режимі?
    >Готував студент Штома Д.О.
    
    The main steps in installing CentOS in text mode include:
    - Selecting the user interface language.
    - Selecting the keyboard language.
    - Loading network profiles.
    - Installing the system.
    - Confirmation of settings and disk partitions.
    - Enter the user, his password and other access details.
    - Installing additional packages if desired. 
    
    The options and sequence of actions may differ depending on the version being installed.
    
   4. Яким чином можна доустановити графічні оболонки Gnome та KDE на CentOS, якщо вона вже встановлена в текстовому режимі (вкажіть необхідні команди та пакети)?
    >Готував студент Штома Д.О.
    
    To install the Gnome and KDE desktop environments on CentOS, run the following commands and packages:

    - To install Gnome:
    sudo yum groupinstall "GNOME Desktop"
    sudo yum groupinstall "X Window System"

    - To install KDE:
    sudo yum groupinstall "KDE Plasma Workspaces"
    sudo yum groupinstall "X Window System"
     
    5. Дайте коротку характеристику графічних інтерфейсів, що використовуються в різних дистрибутивах Linux відповідно до свого варіанту (порядковий номер по     журналу 30 "Оскільки такого варіанту немає я обрав 5"), табл.2.
    >Готував студент Штома Д.О.
    
    GNOME combines a simple and user-friendly interface with various customization options. It contains a large number of programs and can be easily customized to the user's needs. JWM (Joe's Window Manager) is a simple and easy to customize graphical interface that allows users to create a convenient panel of programs for their personalization.
   
>Висновок:
>>Готував студент Путін М.Г.
>>
In the course of completing the tasks of the laboratory work, we have studied the environment of virtual machines and operating systems of various types and families - their graphical shell, login and logout. Practical skills in working with Linux commands and setting up a virtual machine were gained.

Відповіді на контрольні питання:

  1. Type 1 hypervisor (Standalone hypervisor) type 2 (Based on the underlying OS) differ in that the type 1 hypervisor runs directly on the hardware and is independent of the underlying OS, while the type 2 hypervisor can run directly on the physical processor, but access to the computer's I/O devices from the guest OS is through a second component, the usual processor of the underlying OS - the user-level monitor. A type 1 hypervisor has a higher performance than a type 2 hypervisor. 

 2. GNU General Public License (GNU General Public License or GNU General Public License) is one of the most popular free software licenses. The concept of "GNU GPL" is to provide licenses for the distribution of programs, plug-ins or class libraries for free and open source.
 3. The essence of open-source software is that the source code is freely available for anyone to access, use, modify, and distribute, without restrictions or fees.
 4. A distribution kit is a package that contains all the files necessary to install and run a software program on a particular operating system or platform.

 5.  The main tasks of the system administrator (superuser) in Linux include:
installation of the OS;
managing the OS boot process;
setting the operating modes of the OS;
editing configuration files;
mounting and unmounting file systems;
adding and removing OS users;
update the software;
configuring the OS kernel;
ensuring reliable operation of the OS;
configuring a computer network.

6. Android is a mobile operating system based on the Linux kernel. It uses the Linux kernel as its foundation, but also includes its own unique user interface and software stack.

7. Embedded Linux is a version of the Linux operating system designed for use in embedded systems, such as smartphones, routers, and other small devices. Its main features include a small footprint, real-time capabilities, and support for a wide range of hardware architectures. The scope of Embedded Linux includes industrial automation, automotive systems, medical devices, and more.
 
  8. The process of changing the Linux boot type from graphical to text or vice versa depends on the specific Linux distribution and version are using but there are general steps that work on some systems:

- Boot your Linux system and wait for the bootloader screen to appear.
- Select the boot option you want to modify and press the "e" key to edit it.
- Locate the line that starts with "linux" or "linuxefi" and append the word "text" (for text mode) or "graphical" (for graphical mode) at the end of the line.
- Press "Ctrl + x" to boot using the modified boot option.

Key differences between CLI and GUI
  - CLI allows users to manually enter a command to perform a desired task, while in GUI, users are provided with visuals to interat with the operating system, such as buttons, icons, images, etc.
  - GUI tasks are easy to perform and good for beginners. The CLI, on the other hand, requires experience with commands and syntax.
  - GUI systems require a mouse and keyboard, while CLI just requires a keyboard to work.
  - Higher accuracy can be achieved in CLI compared to GUI.
  - GUI has the advantage of flexibility where CLI systems are inflexible.
  - GUI consumes more system space while CLI requires less system resources and space.
  - The appearance of the CLI cannot be changed. On the contrary, the appearance of the GUI is adjustable.
  - CLI is faster than GUI.


