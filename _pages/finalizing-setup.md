---
title: "Завершение установки" #
lang: ru
permalink:  finalizing-setup.html
sidebar:
  nav: "finalizing-setup"
---

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
+  **freeshop** *(open source клон eShop, облегчающий поиск игр)*
+  **Homebrew Launcher Loader** *(запускает Homebrew Launcher в качестве обычного приложения благодаря магии Rosalina)*

{% endcapture %}

<div class="notice--info">{{ notice-2 | markdownify }}</div>

#### <a name="what_need" />Что понадобится

* Свежая версия [Themely](https://github.com/ErmanSayin/Themely/releases/latest) *(`.cia` файл)*
* Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
* Свежая версия [hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases/latest) *(`.zip`-архив)*
* Свежая версия [GodMode9](https://github.com/d0k3/GodMode9/releases/latest) *(`.zip`-архив)*
* Свежая версия [FBI](https://github.com/Steveice10/FBI/releases/latest) *(`.cia-файл`и `.3dsx-файл`)*
* Свежая версия [Homebrew Launcher](https://github.com/fincs/new-hbmenu/releases/latest)
* Свежая версия [Luma3DS Update](https://github.com/KunoichiZ/lumaupdate/releases/latest) *(`.cia` файл)*
* Свежая версия [DSP1](https://github.com/zoogie/DSP1/releases/latest) *(`.cia` файл)*
* Свежая версия [freeshop](https://notabug.org/arc13/freeShop/releases) *(`.cia` файл)*
* **Только для Old 3DS и 2DS:** Old 3DS 11.2.0-35 [otherapp payload](https://smealum.github.io/3ds/#otherapp) для вашего региона

#### <a name="instructions" />Инструкция

##### <a name="part1" />Часть I - Подготовительные работы

1. Отключите приставку
1. Вставьте SD-карту в компьютер
1. Скопируйте `boot.3dsx` в корень SD-карты *(перезаписывайте существующие файлы)*
1. Скопируйте `FBI.3dsx` в папку `/3ds/` на SD-карте
1. Создайте папку `cias` в корне SD-карты
1. Создайте папку `hblauncherloader` в корне SD-карты, если таковой нет
1. Скопируйте `hblauncher_loader.cia` из `.zip` архива hblauncher_loader в папку `/cias/` в корне SD-карты
1. Скопируйте `lumaupdater.cia` в папку `/cias/` в корне SD-карты
1. Скопируйте `Themely.cia` в папку `/cias/` в корне SD-карты
1. Скопируйте `freeshop.cia` в папку `/cias/` в корне SD-карты
1. Скопируйте `DSP1.cia` в папку `/cias/` в корне SD-карты
1. Скопируйте `FBI.cia` в папку `/cias/` в корне SD-карты

    ![]({{ base_path }}/images/screenshots/cias-file-layout.png)
	{: .text-center}
    {: .notice--info}

1. Создайте папку `payloads` в папке `luma` на SD-карте
1. Скопируйте `GodMode9.firm` из `.zip-архива` GodMode9 в папку `/luma/payloads/` на SD-карте

    ![]({{ base_path }}/images/screenshots/finalizing-setup-file-layout.png)
	{: .text-center}
    {: .notice--info}

1. Если ваше устройство использует прошивку версии от 3.0.0 до 4.5.0, консоль не запустится до тех пор, пока вы вручную не скачаете нужные файлы прошивки:
  + Скачайте [этот файл](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/00000056) и переименуйте его в `firmware.bin`
  + Скачайте [этот файл](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/cetk)
  + Скопируйте `firmware.bin` и `cetk` в папку `/luma/` на SD-карте
  + Удалите оба этих файла позже, после обновления устройства
1. Вставьте SD-карту обратно в консоль
1. Включите приставку

##### <a name="part2" />Часть II - Обновление системы

Если вы, следуя предыдущей версии этого руководства, выполнили CTRTransfer на прошивку 2.1.0 на *New 3DS*, [восстановите бэкап NAND](godmode9-usage#nand_restore), прежде чем приступить к этой части.
{: .notice--danger}

Если, следуя прошлой версии руководства, вы делали CTRTransfered прошивки 2.1.0 в *New 3DS*, [восстановите NAND](godmode9-usage#nand_restore) из резервной копии и только потом выполняйте эту часть.
{: .notice--danger}

Если прежде чем начать выполнять действия из этого руководства у вас уже был установлен EmuNAND и вы хотите перенести содержимое EmuNAND в SysNAND с кастомной прошивкой - сейчас самый подходящий момент. Выполните действия из раздела [перенос EmuNAND](move-emunand), перед выполнением этой части.
{: .notice--info}

1. Обновите прошивку консоли, зайдя в Системные настройки (System Settings), затем "Прочие настройки" (Other Settings), затем листайте вправо до конца и выберите пункт "Обновление" (System Update)
  + Обновление консоли с установленным B9S + Luma (установленых у вас) безопасно
  + При появлении ошибки, поставьте в настройках подключения, в настройках DNS "Получать DNS автоматически" в положение "Да"
  + Если вы все еще получаете ошибку и версия вашего NAND ниже 9.2.0, [выполните 9.2.0 CTRTransfer](9.2.0-ctrtransfer) и попробуйте обновиться еще раз

##### <a name="part3" />Часть III - Интеграция Homebrew Launcher

1. Запустите приложение Загружаемая игра (Download Play)
1. Нажмите (L) + (ВНИЗ) + (SELECT) одновременно чтобы открыть меню Rosalina
1. Выберите "Process patches menu..."
1. Выберите "Patch SM for the service checks"
1. Нажмите (B), чтобы продолжить
1. Выберите "Patch FS for the archive checks"
1. Нажмите (B), чтобы продолжить
1. Нажмите (B) для возврата в главное меню Rosalina
1. Выберите "Miscellaneous options"
1. Выберите "Switch the hb. title to the current app."
1. Нажмите (B), чтобы продолжить
1. Нажмите (B) для возврата в главное меню Rosalina
1. Нажмите (B) для выхода из главного меню Rosalina
1. Нажмите (HOME), затем закройте приложение Загружаемая игра (Download Play)
1. Запустите приложение Загружаемая игра (Download Play)
1. Консоль должна загрузиться в Homebrew Launcher

##### Часть IV - Установка CIA

1. Выберите FBI в списке homebrew
1. Перейдите в `SD` -> `cias`
1. Выберите "\<current directory>"
1. Выберите "Install and delete all CIAs" и нажмите (A) для подтверждения
1. Нажмите (HOME), затем закройте приложение Загружаемая игра (Download Play)

##### <a name="part5" />Часть V - DSP Dump

1. Запустите приложение DSP1
1. После завершения работы программы, нажмите (B), чтобы автоматически удалить программу из меню HOME

##### <a name="part6" />Часть VI - CTRNAND Luma3DS

Обратите внимание, что в некоторых версиях Luma3DS, меню Luma3DS chainloader отображается только в том случае, если в папке payloader более одного приложения. Если установлено только одно приложение, удерживание (START) при включении консоли запустит GodMode9 напрямую.
{: .notice--info}

1. Перейдите в `[0:] SDCARD`
1. Нажмите (Y) на файле `boot.firm`, чтобы скопировать его
1. Нажмите (B) для возврата в главное меню
1. Перейдите в `[1:] SYSNAND CTRNAND`
1. Нажмите (Y), чтобы вставить копию `boot.firm`
1. Выберите "Copy path(s)"
1. Нажмите (A), чтобы разрешить запись в SysNAND (lvl1) и введите указанную комбинацию кнопок
1. Нажмите (B) для возврата в главное меню
1. Перейдите в `[0:] SDCARD`
1. Нажмите (Y) на папке `luma`, чтобы скопировать её
1. Нажмите (B) для возврата в главное меню
1. Перейдите в `[1:] SYSNAND CTRNAND` -> `rw`
1. Нажмите (Y), чтобы вставить копию папки `luma` из вашей SD-карты
1. Выберите "Copy path(s)"

##### <a name="nand_backup" />Часть VII - NAND Backup

1. Дважды нажмите (B) для возврата в главное меню
1. Нажмите кнопку (HOME) для вызова меню
1. Выберите "More..."
1. Выберите "Backup NAND"
1. Нажмите (A), чтобы продолжить
1. Удерживая (R) нажмите (B) для того, чтобы извлечь SD-карту
1. Вставьте SD-карту в компьютер
1. Скопируйте `nand.bin` и `nand.bin.sha` из папки `/gm9out/` на SD-карте в безопасное место на вашем компьютере
  + Сделайте несколько резервных копий в нескольких местах (например в облачном хранилище)
  + Эти бэкапы позволят восстановить консоль, если впоследствии что-то пойдёт не так
1. После копирования удалите `nand.bin` и `nand.bin.sha`  из папки `/gm9out/` на SD-карте
1. Вставьте SD-карту обратно в консоль
1. Нажмите (START), чтобы сохранить настройки и перезагрузиться

##### <a name="freeshop" />Часть VIII - Настройка freeshop

Приложение работает только при включенном интернете!
{: .notice--info}

1. Запустите консоль
1. Запустите приложение freeshop из меню Home
1. Дождитесь пока программа обновится
1. Перейдите в настройки программы. Для этого на нижнем экране нажмите вторую справа иконку в верхнем правом углу (в форме шестеренки)
1. Перейдите во вкладку "Обновление"
1. Поставьте галочку напротив первого пункта - "Авто-обновление ключей приложения через URL"
1. Нажмите на иконку с изображение QR-кода (находится прямо под галочкой, которую вы только что отметили)
1. Отсканируйте QR 

    ![]({{ base_path }}/images/QR/freeshop.png)
	{: .text-center}
    {: .notice--info}

1. Нажмите кнопку "Обновить кэш"
1. Перезагрузите freeshop

Если у вас freeshop ругается на неверные или отсутствующие ключи, скачайте предложенный [`zip-архив`](images/freeShop.zip) и распакуйте его содержимое с заменой в папку `/3ds/data` на вашей SD-карте (должно получится так: `/3ds/data/freeshop/файлы`), после чего перезагрузите freeshop.
{: .notice--warning}

Установка приложений из freeshop происходит с помощью кнопки (X)
{: .notice--info}

___

В случае проблем с работой DSi / DS (например, картриджи DS или DSiWare перестали работать), обратитесь к разделу [Проблемы и их решения](troubleshooting#twl_broken)
{: .notice--warning}

{% capture notice-10 %}
Теперь вы можете использовать Luma3DS Updater для обновления кастомной прошивки. Запустите его и нажмите (А).     
Это не тоже самое что Обновление системы (System Update). Это приложение обновляет только файлы Luma3DS.
Это обновит только те файлы Luma3DS, которые находятся на SD-карте. Если вы включите консоль без SD-карты, она загрузится используя Luma3DS из CTRNAND.    
{% endcapture %}

<div class="notice--info">{{ notice-10 | markdownify }}</div>

{% capture notice-6 %}   
Теперь по умолчанию будет запускаться Luma3DS CFW SysNAND.    
Для запуска конфигуратора Luma3DS включите консоль с зажатой кнопкой (SELECT).    
Теперь вы можете удерживать (START) при загрузке для запуска Luma3DS chainloader меню (обратите внимание, что Luma3DS chainloader меню отображается только если существует более одного приложения).
Удерживайте (START) + (SELECT) + (X) при загрузке для сохранения копий ARM11 bootrom (`boot11.bin`), ARM9 bootrom (`boot9.bin`) и уникального OTP вашей консоли (`OTP.bin`) в папку `/boot9strap/` на SD-карте (весь процесс произойдет в фоне без какого-либо сообщения, или прогресс-бара).
Теперь нажатие (L) + (ВНИЗ) + (SELECT) в запущенной системе открывает меню Rosalina, встроенное в Luma3DS. Полный список особенностей Rosalina, можно прочитать в [README Luma3DS](https://github.com/AuroraWright/Luma3DS/blob/master/README.md) (англ.)
{% endcapture %}

<div class="notice--info">{{ notice-6 | markdownify }}</div>

Для использования [NTR CFW](https://github.com/44670/BootNTR/), установите [BootNTR Selector](https://gbatemp.net/threads/432911/).
{: .notice--info}

{% capture notice-7 %}
Удалите любые лишние файлы и папки из корня вашей SD-карты, которых *нет* на следующем изображении:
<br><br>
![]({{ base_path }}/images/screenshots/final-file-layout.png)
{: .text-center}
{% endcapture %}

<div class="notice--info">{{ notice-7 | markdownify }}</div>

Чтобы узнать, как сменить регион своей консоли, обратитесь к разделу [Смена региона](region-changing).
{: .notice--success}

Для получения информации по использованию различных функций GodMode9 обратитесь к разделу [Использование GodMode9](godmode9-usage).
{: .notice--success}

Для справки об использовании различных функций Luma3DS обратитесь к её [вики](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage) (англ.).
{: .notice--success}

<a name="links" />
Различные инструкции, не имеющие прямого отношения ко взлому, однако помогающие лучше изучить возможности 3DS на кастомной прошивке и эффективнее ей пользоваться находятся [здесь](addons).
{: .notice--success}

<div id="vk_comments"></div>
<script type="text/javascript">
VK.Widgets.Comments("vk_comments", {limit: 10, attach: "*"});
</script>