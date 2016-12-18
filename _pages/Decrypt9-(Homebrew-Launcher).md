---
title: "Decrypt9 (Homebrew Launcher)"
permalink: /decrypt9-(Homebrew-launcher).html
sidebar:
  nav: "decrypt9-(Homebrew-launcher)"
---
<a name="start" />
Если ваша 3DS уже взломана и у нее есть рабочий и настроенный EmuNAND, помните, что этот гайд имеет дело исключительно с SysNAND, поэтому все действия применяются именно к этому разделу и только к нему. Не забывайте, что EmuNAND и RedNAND - всего лишь разные методы [NAND-перенаправления](http://3dbrew.org/wiki/NAND_Redirection) с едва различимыми различиями в способах работы. Чуть позже мы [перенесем EmuNAND](move-emunand) в SysNAND. 
{: .notice--info}

#### <a name="what_need" />Что нужно: 

* Свежая версия [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/)

#### <a name="instructions" />Что делать:

2. Создайте папку `files9` в корне карты памяти, если папки нет - создайте ее. 
3. Скопируйте папку `Decrypt9WIP` из архива с Decrypt9WIP в папку `/3ds/` на вашей карте памяти.
4. Вставьте карту памяти в приставку.
4. Запустите Homebrew launcher.
4. Запустите Decrypt9WIP **(Часто запускается не с первого раза)**
    + Если после множества попыток, Decrypt9WIP так и не запустился, скорее всего, у вас частично пониженная прошивка. Вернитесь на страницу с [даунгрейдом до 9.2.0](9.2.0-downgrade).
4. Выберите "SysNAND Options", а затем "SysNAND Backup/Restore".
5. Выберите "NAND Backup (min size)" и сделайте бекап в файл `NANDmin.bin`.
6. Вернитесь в главное меню. 

Переходите к [2.1.0 ctrtransfer](2.1.0-ctrtransfer).    
{: .notice--primary}
