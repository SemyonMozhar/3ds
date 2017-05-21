---
title: "Завершение установки" #
lang: ru
permalink:  finalizing-setup.html
---

Для использования [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme)-ссылок в этом руководстве необходим torrent-клиент, например [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--success}

#### <a name="steps" />Описание шагов

{% capture notice-2 %}

Файл `boot.firm` - это то, что boot9strap запускает после загрузки из NAND, и этот файл может быть любым arm9-приложением. Этот файл может быть заменён когда угодно, однако Luma3DS позволяет запускать другие arm9 приложения в FIRM формате, используя свой загрузчик.
<br><br>
Мы используем Luma3DS от [AuroraWright](https://github.com/AuroraWright/), чтобы запускать пропатченный SysNAND напрямую, поэтому необходимость в каком-либо виде EmuNAND полностью пропадает, что значительно упрощает использование взломанной 3DS и экономит место на SD-карте.
<br><br>
В процессе мы установим и настроим следующие программы:    

+  **FBI** *(установщик приложений и игр в формате CIA)*
+  **Themely** *(установка пользовательских тем)*
+  **Luma3DS Updater** *(Удобное обновление CFW)*
+  **GodMode9** *(многофункциональная утилита для работы с NAND и картриджами)*

{% endcapture %}

<div class="notice--info">{{ notice-2 | markdownify }}</div>

#### <a name="what_need" />Что понадобится

* Свежая версия [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(`.7z`-архив)*
* Свежая версия [Themely](https://github.com/ErmanSayin/Themely/releases/latest) *(`.cia` файл)*
* Свежая версия [hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases/latest)
* Свежая версия [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* Свежая версия [DSP1](https://github.com/zoogie/DSP1/releases/latest)
* Свежая версия [FBI](https://github.com/Steveice10/FBI/releases/latest)
* Свежая версия [Luma3DS Updater](https://github.com/KunoichiZ/lumaupdate/releases/latest)
* **Только для Old 3DS и 2DS:** Old 3DS 11.2.0-35 [otherapp payload](https://smealum.github.io/3ds/#otherapp) для вашего региона

#### <a name="instructions" />Инструкция

##### <a name="part1" />Часть I - Подготовительные работы

1. Вставьте SD-карту в компьютер
1. Создайте папку `cias` в корне SD-карты
1. Создайте папку `hblauncherloader` в корне SD-карты, если таковой нет
1. Скопируйте `hblauncher_loader.cia` из архива hblauncher_loader в папку `/cias/` в корне SD-карты
1. Скопируйте `lumaupdater-v2.0.cia` из `.zip-архива` Luma3DS Updater в папку `/cias/` в корне SD-карты
1. Скопируйте `FBI.cia` из архива FBI в папку `/cias/` в корне SD-карты
1. Скопируйте `DSP1.cia` в папку `/cias/` в корне SD-карты
1. Скопируйте `Themely.cia` в папку `/cias/` в корне SD-карты

    ![]({{ base_path }}/images/screenshots/cias-file-layout.png)
    {: .notice--info}

1. Скопируйте файл `boot.firm` из `.7z-архива` Luma3DS в корень SD-карты
1. Создайте папку `luma` в корне SD-карты
1. Создайте папку `payloads` в папке `luma` на SD-карте
1. Скопируйте `GodMode9.firm` из `.zip-архива` GodMode9 в папку `/luma/payloads/` на SD-карте
1. **Только для Old 3DS и 2DS:** Скопируйте Old 3DS 11.2.0-35 otherapp payload для вашего региона в папку `/hblauncherloader/` на SD-карте
1. **Только для Old 3DS и 2DS:** Переименуйте файл Old 3DS 11.2.0-35 otherapp payload на SD-карте в один из указанных ниже, подходящий вашему региону:
  + **EUR:** `OLD-11-4-0-37-EUR.bin`
  + **JPN:** `OLD-11-4-0-37-JPN.bin`
  + **KOR:** `OLD-11-4-0-37-KOR.bin`
  + **USA:** `OLD-11-4-0-37-USA.bin`

    ![]({{ base_path }}/images/screenshots/finalizing-setup-file-layout.png)
    {: .notice--info}

1. Если ваше устройство использует прошивку версии от 3.0.0 до 4.5.0, консоль не запустится до тех пор, пока вы вручную не скачаете нужные файлы прошивки:
  + Скачайте [этот файл](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/00000056) и переименуйте его в `firmware.bin`
  + Скачайте [этот файл](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/cetk)
  + Скопируйте `firmware.bin` и `cetk` в папку `/luma/` на SD-карте
  + Удалите оба этих файла позже, после обновления устройства
1. Вставьте SD-карту обратно в консоль

##### <a name="part2" />Часть II - Настройка Luma3DS

1. Включите консоль, чтобы попасть в меню настроек Luma3DS
  + Если после включения экран остаётся чёрным, то перейдите к разделу [проблемы и их решения](troubleshooting#ts_sys_b9s)
1. Нажимая (A) выберите следующие пункты:    
  + **"Show NAND or user string in System Settings"**
1. Нажмите (Start), чтобы сохранить настройки и перезагрузиться
  + Если после включения экран остаётся чёрным, просто переходите к следующей части   

##### <a name="part3" />Часть III - Обновление системы

Если прежде чем начать выполнять действия из этого руководства у вас уже был установлен EmuNAND и вы хотите перенести содержимое EmuNAND в SysNAND с кастомной прошивкой - сейчас самый подходящий момент. Выполните действия из раздела [перенос EmuNAND](move-emunand), вместо первых 9 шагов в этой части.
{: .notice--info}

1. Обновите прошивку консоли, зайдя в Системные настройки (System Settings), затем "Прочие настройки" (Other Settings), затем листайте вправо до конца и выберите пункт "Обновление" (System Update)
  + Обновление консоли с установленным B9S + Luma (установленых у вас) безопасно
  + При появлении ошибки, поставьте в настройках подключения, в настройках DNS "Получать DNS автоматически" в положение "Да"
  + Если вы все еще получаете ошибку и версия вашего NAND ниже 9.2.0, [выполните 9.2.0 CTRTransfer](9.2.0-ctrtransfer) и попробуйте обновиться еще раз

##### <a name="part4" />Часть IV - Интеграция FBI

1. Перезагрузитесь, удерживая кнопку (Start), чтобы запустить меню Luma3DS chainloader
1. Запустите GodMode9, нажав кнопку (A)
1. Перейдите в `[0:] SDCARD` -> `cias`
1. Нажмите (A) чтобы выбрать файл `FBI.cia`, затем выберите "CIA image options...", затем "Mount image to drive"
1. Нажмите (A) чтобы выбрать файл `.app`, затем выберите "NCCH image options", затем "Inject to H&S"
1. Нажмите (A), чтобы разрешить запись в SysNAND (lvl1) и введите указанную комбинацию кнопок
1. Нажмите (A), чтобы продолжить
1. Нажмите (START) для перезагрузки
1. Если при запуске Health & Safety запускается не FBI и вы в прошлом понижали прошивку с помощью Gateway, обратитесь к [этой части раздела Проблемы и их решения](troubleshooting#gw_fbi)

##### <a name="part5" />Часть V - Установка CIA

1. Запустите "Информация о здоровье и безопасности" (Health and Safety) (теперь это FBI)
1. Перейдите в `SD` -> `cias`
1. Выберите "\<current directory>"
1. Выберите "Install all CIAs" и нажмите (A) для подтверждения
1. Нажмите (HOME) для выхода из FBI

##### <a name="part6" />Часть VI - DSP Dump

1. Запустите DSP1
1. После завершения, нажмите (START) для выхода

##### <a name="part7" />Часть VII - Восстановление приложения Информация о здоровье и безопасности (Health and Safety)

1. Перезагрузитесь, удерживая кнопку (Start), чтобы запустить меню Luma3DS chainloader
1. Запустите GodMode9, нажав кнопку (A)
1. Нажмите кнопку (HOME) для вызова меню
1. Выберите "More..."
1. Выберите "Restore H&S"
1. Нажмите (A), чтобы разрешить запись в SysNAND (lvl1) и введите указанную комбинацию кнопок

##### <a name="part8" />Часть VIII - CTRNAND Luma3DS

1. Перезагрузитесь, удерживая кнопку (Start), чтобы запустить меню Luma3DS chainloader
1. Запустите GodMode9, нажав кнопку (A)
1. Перейдите в `[0:] SDCARD` -> `luma` -> `payloads`
1. Нажмите (X), выделив файл `SafeB9SInstaller.bin` чтобы удалить его
1. Нажмите (A) для подтверждения
1. Нажмите (B), чтобы вернуться к `[0:] SDCARD`
1. + Нажмите (Y), выделив файл `boot.firm` чтобы скопировать его
1. Нажмите (B) для возврата в главное меню
1. Перейдите в `[1:] SYSNAND CTRNAND`
1. Нажмите (Y), чтобы вставить копию `boot.firm`
1. Выберите "Copy path(s)"
1. Нажмите (A), чтобы разрешить запись в SysNAND (lvl1) и введите указанную комбинацию кнопок
1. Нажмите (B) для возврата в главное меню
1. Удерживая (R) нажмите (B) для того, чтобы извлечь SD-карту
1. Извлеките SD-карту из консоли
1. Нажмите (START) для перезагрузки с извлеченной SD-картой
  + Необходимо хотя бы раз загрузиться без SD-карты, чтобы настроить Luma3DS, установленную в раздел CTRNAND
1. Нажимая (A) выберите следующие пункты:    
  + **"Show NAND or user string in System Settings"**
1. Вставьте SD-карту обратно в консоль
1. Нажмите (Start), чтобы сохранить настройки и перезагрузиться

##### <a name="part9" />Часть IX - NAND Backup

1. Включите консоль кнопкой питания, держа нажатой кнопку (Start), чтобы запустить меню Luma3DS chainloader
1. Запустите GodMode9, нажав кнопку (A)
1. Нажмите кнопку (HOME) для вызова меню
1. Выберите "More..."
1. Выберите "Backup NAND"
1. Нажмите (A), чтобы продолжить
1. Удерживая (R) нажмите (B) для того, чтобы извлечь SD-карту
1. Вставьте SD-карту в компьютер
1. Скопируйте `nand.bin` из папки `/gm9out/` на SD-карте в безопасное место на вашем компьютере
  + Сделайте несколько резервных копий в нескольких местах (например в облачном хранилище)
  + Эти бэкапы позволят восстановить консоль, если впоследствии что-то пойдёт не так
1. После копирования удалите `nand.bin` из папки `/gm9out/` на SD-карте
1. Вставьте SD-карту обратно в консоль
1. Нажмите (Start), чтобы сохранить настройки и перезагрузиться

___

{% capture notice-10 %}
Теперь вы можете использовать Luma3DS Updater для обновления кастомной прошивки. Запустите его и нажмите (А).     
Это не тоже самое что Обновление системы (System Update). Это приложение обновляет только файлы Luma3DS.
Это обновит только те файлы Luma3DS, которые находятся на SD-карте. Если вы включите консоль без SD-карты, она загрузится используя Luma3DS из CTRNAND.    
{% endcapture %}

<div class="notice--info">{{ notice-10 | markdownify }}</div>

{% capture notice-6 %}   
Теперь по умолчанию будет запускаться Luma3DS CFW SysNAND.    
Для запуска конфигуратора Luma3DS включите консоль с зажатой кнопкой (Select).    
Теперь вы можете удерживать (START) при загрузке для запуска Luma3DS chainloader меню (обратите внимание, что Luma3DS chainloader меню отображается только если существует более одного приложения).
Теперь вы можете удерживать (START) + (SELECT) + (X) при загрузке для сохранения копий ARM11 bootrom (`boot11.bin`), ARM9 bootrom (`boot9.bin`) и уникального OTP вашей консоли (`OTP.bin`) в папку `/boot9strap/` на SD-карте (Обратите внимания, что это не имеет какого либо запроса или сообщения).
{% endcapture %}

<div class="notice--info">{{ notice-6 | markdownify }}</div>

Для использования [NTR CFW](https://github.com/44670/BootNTR/), установите [BootNTR Selector](https://gbatemp.net/threads/432911/).
{: .notice--info}

{% capture notice-7 %}
Удалите любые лишние файлы и папки из корня вашей SD-карты, которых *нет* на следующем изображении:
<br><br>
![]({{ base_path }}/images/screenshots/final-file-layout.png)
{% endcapture %}

<div class="notice--info">{{ notice-7 | markdownify }}</div>

Чтобы узнать, как сменить регион своей консоли, обратитесь к разделу [Смена региона](region-changing).
{: .notice--success}

Для получения информации по использованию различных функций GodMode9 обратитесь к [Использование GodMode9](godmode9-usage).
{: .notice--success}

Для справки об использовании различных функций Luma3DS обратитесь к её [вики](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage) (англ.).
{: .notice--success}

Для получения информации по установке пользовательских тем, значков и экранов-заставок, посетите [3dsthem.es](https://3dsthem.es/about.php).
{: .notice--success}
