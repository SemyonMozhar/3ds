---
title: "Установка arm9loaderhax"
permalink: /installing-arm9loaderhax.html
sidebar:
  nav: "installing-arm9loaderhax"
---

Последний шаг данного руководства - установка arm9loaderhax и настройка Luma3DS на мгновенную загрузку сразу после включения консоли. Для этого мы воспользуемся SafeA9LHInstaller от [AuroraWright](https://github.com/AuroraWright/).
{: .notice}

Мы будем устанавливать [arm9loaderhax от AuroraWright](https://github.com/AuroraWright/arm9loaderhax).
{: .notice--info}

Также мы настроим возможность запускать другие приложения (payloads) через arm9loaderhax, что даст нам возможность восстановить SysNAND из бэкапа в ситуациях, которые обычно привели бы к брику.
{: .notice--info}

Для использования [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme)-ссылок в этом руководстве необходим torrent-клиент, например [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--info}
**Никогда не используйте OTP от другой консоли, это ГАРАНТИРОВАННО приведёт к брику**
{: .notice--danger}

**НИКОГДА не обновляйте New 3DS с прошивкой 2.1.0 (поскольку, это порт старой прошивки от Old3DS), это чревато БРИКОМ! Сначала ОБЯЗАТЕЛЬНО восстановите NAND из резервной копии или произведите обратный ctrtransfer на стандартную прошивку New 3DS!**
{: .notice--danger}

**Эту часть инструкции можно выполнять ТОЛЬКО находясь на 2.1.0. Если вы попали на эту страницу случайно, или по прямой ссылке и у вас не установлена 2.1.0, вернитесь в [начало](/) гайда и следуйте инструкции!**
{: .notice--danger}

{% capture notice %}
**Вы ГАРАНТИРОВАННО получите НЕВОССТАНАВЛИВАЕМЫЙ брик, если вы введете New 3DS с прошивкой 2.1.0 в режим сна! После того, как прошивка из бекапа будет восстановлена, закрывать крышку приставки снова будет безопасно**
**Это происходит только при закрытии крышки, _пока устройство включено_; это не касается выключения консоли.**
**Устройство переходит в спящий режим только когда крышка закрыта. Таймера, или чего-то похожего, в системе нет.**
**Оказавшись на 2.1.0 без промедления сделайте все необходимые шаги, чтобы избежать этого!**
{% endcapture %}

#### <a name="steps" />Описание шагов

{% capture notice-2 %}

В этом разделе мы, наконец, сделаем то, к чему вели все предыдущие шаги: установим arm9loaderhax.
<br><br>
Можно уверенно заявить, что arm9loaderhax - наилучший из имеющихся типов эксплойтов. Все потому, что он устанавливается непосредственно в раздел NAND firm и запускается ДО запуска операционной системы приставки. Кроме прочего, a9lh работает с **любой** прошивкой и, благодаря тому, что запускается до ОС, в большинстве ситуаций, удалить его случайно не выйдет. А еще этот эксплойт позволяет запускать различного рода загрузчики, которые помогут восстановить консоль даже из тех состояний, которые в обычном случае привели бы вас в сервисный центр. 
<br><br>
Файл `arm9loaderhax.bin` - это то, что arm9loaderhax запускает после загрузки из NAND, и этот файл может быть любым arm9-приложением. Он может быть заменён когда угодно, однако Luma3DS позволяет запускать другие arm9 приложения, используя свой загрузчик.
<br><br>
Мы используем Luma3DS от [AuroraWright](https://github.com/AuroraWright/), чтобы запускать пропатченный SysNAND напрямую, поэтому необходимость в EmuNAND в каком-либо виде полностью пропадает, что значительно упрощает использование взломанной 3DS и экономит место на SD-карте.
<br><br>
После установки arm9loaderhax и настройки Luma3DS мы восстановим бэкап прошивки, сделанный ранее.
<br><br>
В процессе мы установим следующие программы:    

+  **FBI** *(установщик приложений и игр в формате CIA)*
+  **Themely** *(для установки кастомных тем)*
+  **Luma3DS Updater** *(удобное обновление CFW)*
+  **GodMode9** *(многофункциональная утилита для работы с NAND и картриджами)*
+  **freeshop** *(open source клон eShop, облегчающий поиск игр)*

{% endcapture %}

<div class="notice--info">{{ notice-2 | markdownify }}</div>

#### <a name="what_need" />Что понадобится

* <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [`aeskeydb.bin`](magnet:?xt=urn:btih:18b3a17f78e2376e05feaa150749d9fd689b25dc&dn=aeskeydb.bin&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)

* <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [`data_input_v3.zip`](magnet:?xt=urn:btih:a1195c9f7ab650fa7c7bf020b51fc19ea8d9440c&dn=data%5Finput%5Fv3.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* Свежая версия [SafeA9LHInstaller](https://github.com/Plailect/SafeA9LHInstaller/releases/latest) *(`.7z`-архив)*
* Свежая версия [arm9loaderhax](https://github.com/AuroraWright/arm9loaderhax/releases/latest) *(`.7z`-архив)*
* Свежая версия [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(`.7z`-архив)*
* Свежая версия [Themely](https://github.com/ErmanSayin/Themely/releases/latest) *(`.cia`-файл)*
* Свежая версия [hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases/latest)
* Свежая версия [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* Свежая версия [Luma3DS Updater](https://github.com/Hamcha/lumaupdate/releases/latest)
* Свежая версия [FBI](https://github.com/Steveice10/FBI/releases/latest)
* Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
* Свежая версия [freeshop](https://notabug.org/arc13/freeShop/releases)
* **Только для Old 3DS и 2DS:** Old 3DS 11.2.0-35 [otherapp payload](https://smealum.github.io/3ds/#otherapp) для вашего региона

Если у вас не выходит скачать freeshop или другие файлы, воспользуйтесь VPN. 
{: .notice--warning}

#### <a name="instructions" />Инструкция

##### <a name="part1" />Часть I - Подготовительные работы

**Убедитесь в том, что ваша SD-карта исправна! Использование неисправной карты может привести к БРИКУ! Если вы не уверены, что SD-карта исправна, рекомендуется проверить eё на ошибки с помощью [H2testw (Windows)](h2testw-windows), [F3 (Linux)](f3-linux), или [F3X (Mac)](f3x-mac)!**
{: .notice--warning}

1. Вставьте SD-карту в компьютер
1. Скопируйте `<серийный_номер_приставки>_nand.bin` и `<серийный_номер_приставки>_nand.bin.sha` (если таковые существуют) из папки `/CTRTransfer/` на вашей SD-карте в безопасное место на вашем компьютере
  + Сделайте несколько резервных копий в нескольких местах (например в облачном хранилище)
  + Эти бэкапы позволят восстановить консоль, если впоследствии что-то пойдёт не так
1. Создайте папку `cias` в корне SD-карты
1. Создайте папку `hblauncherloader` в корне SD-карты, если таковой нет
1. Удалите папку `3ds` из корня SD-карты, если таковая существует
1. Скопируйте _содержимое_ папки `starter` из архива `starter.zip` в корень вашей SD-карты
  + Этот архив содержит новую папку `3ds`, которая заменит удаленную
1. Скопируйте _содержимое_ `.7z-архива` SafeA9LHInstaller в корень SD-карты
1. **Скопируйте папку `a9lh` из `.zip-архива` `data_input` в корень SD-карты**
1. Скопируйте _содержимое_ архива arm9loaderhax (`release.7z`) в папку `a9lh` в корне SD-карты
1. Скопируйте `hblauncher_loader.cia` из архива hblauncher_loader в папку `/cias/` в корне SD-карты
1. Скопируйте `lumaupdater.cia` из архива Luma3DS Updater в папку `/cias/` в корне SD-карты
1. Скопируйте `FBI.cia` из архива FBI в папку `/cias/` в корне SD-карты
1. Скопируйте `Themely.cia` в папку `/cias/` в корне SD-карты
1. Скопируйте `freeShop-latest.cia` в папку `/cias/` в корне SD-карты

    <div class="notice--info"><a href="{{ base_path }}/images/screenshots/cias-file-layout.png"><div class="screenshot_image"><img src="{{ base_path }}/images/screenshots/cias-file-layout-crop.png"></div></a></div>

1. **Скопируйте `arm9loaderhax.bin` из `.7z-архива` Luma3DS в корень SD-карты, соглашаясь на перезапись файлов**
1. Создайте папку `luma` в корне SD-карты
1. Создайте папку `payloads` в папке `luma` на SD-карте
1. Скопируйте `GodMode9.bin` из `.zip-архива` GodMode9 в папку `/luma/payloads/` на SD-карте
1. Скопируйте `aeskeydb.bin` в папку `/files9/` в корне SD-карты
1. Скопируйте `DspDump.3dsx` в папку `/3ds/` в корне SD-карты
1. **Только для Old 3DS и 2DS:** Скопируйте Old 3DS 11.2.0-35 otherapp payload для вашего региона в папку `/hblauncherloader/` на SD-карте
1. **Только для Old 3DS и 2DS:** Переименуйте файл Old 3DS 11.2.0-35 otherapp payload на SD-карте в один из указанных ниже, подходящий вашему региону:
  + **EUR:** `OLD-11-4-0-37-EUR.bin`
  + **JPN:** `OLD-11-4-0-37-JPN.bin`
  + **KOR:** `OLD-11-4-0-37-KOR.bin`
  + **USA:** `OLD-11-4-0-37-USA.bin`

    <div class="notice--info"><a href="{{ base_path }}/images/screenshots/install-a9lh-file-layout.png"><div class="screenshot_image"><img src="{{ base_path }}/images/screenshots/install-a9lh-file-layout-crop.png"></div></a>
	<br><br>
    <a href="{{ base_path }}/images/screenshots/install-a9lh_folder-file-layout.png"><div class="screenshot_image"><img src="{{ base_path }}/images/screenshots/install-a9lh_folder-file-layout-crop.png"></div></a></div>
  
##### <a name="part2" />Часть II - Установка arm9loaderhax

**Эту часть инструкции можно выполнять ТОЛЬКО находясь на 2.1.0. Если вы попали на эту страницу случайно, или по прямой ссылке и у вас не установлена 2.1.0, вернитесь в [начало](/) гайда и следуйте инструкции!**
{: .notice--danger}

**НИКОГДА не обновляйте New 3DS с прошивкой 2.1.0 (поскольку, это порт старой прошивки от Old3DS), это чревато БРИКОМ! Сначала ОБЯЗАТЕЛЬНО восстановите NAND из резервной копии или произведите обратный ctrtransfer на стандартную прошивку New 3DS!**
{: .notice--danger}

{% capture notice %}
**Вы ГАРАНТИРОВАННО получите НЕВОССТАНАВЛИВАЕМЫЙ брик, если вы введете New 3DS с прошивкой 2.1.0 в режим сна! После того, как прошивка из бекапа будет восстановлена, закрывать крышку приставки снова будет безопасно**
**Это происходит только при закрытии крышки, _пока устройство включено_; это не касается выключения консоли.**
**Устройство переходит в спящий режим только когда крышка закрыта. Таймера, или чего-то похожего, в системе нет.**
**Оказавшись на 2.1.0 без промедления сделайте все необходимые шаги, чтобы избежать этого!**
{% endcapture %}

Помните, что приставка не включится, если в нее вставлена SD-карта. Выньте карту, а только затем включайте!
{: .notice--warning}

1. Убедитесь, что приставка включена, а затем вставьте в нее SD-карту 
1. **Консоль уже должна быть на прошивке 2.1.0**
2. Откройте `https://goo.gl/xUMUJB` в браузере 3DS (нужно вводить адрес не в поиск, а именно перейти по нему, воспользовавшись кнопкой URL)
  + Если появляется ошибка "This service is not available in your region", поменяйте регион в Системных настройках (System Settings) на соответствующий тому, который был установлен при 2.1.0 CTRTransfer
  + Если вы забыли отключить Родительский контроль до начала процесса CTRTransfer или не можете получить доступ к настройкам сети, консоль подключится автоматически к беспроводной сети с именем `attwifi` без пароля
  + Если браузер зависает, обратитесь к разделу [Проблемы и их решения](troubleshooting#ts_browser), либо проверьте, что на карте все необходимые файлы находятся на нужных местах и карта памяти находится в приставке
  + Если на экране видны искажения, обратитесь к разделу [Проблемы и их решения](troubleshooting#ts_safe_a9lh_screen)
  + Если вы забыли включить Wi-Fi на 2DS или New 3DS, это можно сделать, вытащив батарею и отключив зарядное устройство на несколько секунд, а затем снова включить консоль
  
    <div class="notice--info"><a href="{{ base_path }}/images/screenshots/browser.png"><div class="screenshot_image"><img src="{{ base_path }}/images/screenshots/browser-crop.png"></div></a>
	<br><br>
	<a href="{{ base_path }}/images/screenshots/browser-url.png"><div class="screenshot_image"><img src="{{ base_path }}/images/screenshots/browser-url-crop.png"></div></a>
	<br><br>
	<a href="{{ base_path }}/images/screenshots/safea9lhinstaller-full.png"><div class="screenshot_image"><img src="{{ base_path }}/images/screenshots/safea9lhinstaller-full-crop.png"></div></a></div>
  
1. Нажмите (SELECT) для установки
1. Установщик поставит arm9loaderhax на вашу консоль (буквально за секунду)
1. Выключите консоль, нажав любую кнопку
1. Вставьте SD-карту в компьютер
1. Скопируйте уникальный для вашей консоли файл `otp.bin` из папки `/a9lh/` на SD-карте в надежное место на вашем компьютере и сделайте несколько резервных копий в нескольких местах (например в облачном хранилище)
1. Вставьте SD-карту обратно в консоль
  
##### <a name="part3" />Часть III - Настройка Luma3DS

1. Включите вашу консоль, зажав кнопку (SELECT), чтобы попасть в меню настроек Luma3DS
  + Важно зажать кнопку до того, как включать приставку
  + Если после включения экран остаётся чёрным, то перейдите к разделу [проблемы и их решения](troubleshooting#ts_sys_a9lh)   
  + Если после загрузки запускается SafeA9LHInstaller, то перейдите к разделу [проблемы и их решения](troubleshooting#ts_safe_a9lh)
1. Нажимая (A) выберите следующие пункты:    
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R"**
  + **"Show NAND or user string in System Settings"**
  + **"Enable game patching"**
1. Если у вас **New 3DS**, вы *также* можете включить следующие опции:
  + **"New 3DS CPU" выбрать значение "Clock+L2(x)"**
    + Это увеличит частоту кадров в множестве игр, но может отразиться на стабильности других
    + Если какие-либо игры работают некорректно, отключите эту опцию
	
    <div class="notice--info"><a href="{{ base_path }}/images/screenshots/luma-settings.png"><div class="screenshot_image"><img src="{{ base_path }}/images/screenshots/luma-settings-crop.png"></div></a></div>
	
1. Нажмите (START), чтобы сохранить настройки и перезагрузиться
  + Если после включения экран остаётся чёрным, просто переходите к следующей части   
  + Если появляется ошибка "Failed to mount CTRNAND", просто переходите к следующей части     
  + Если появится ошибка "Failed to apply 1 Firm patch(es)", понизьте версию luma до 6.6 (https://github.com/AuroraWright/Luma3DS/releases/tag/v6.6)
  
##### <a name="part4" />Часть IV - Восстановление системы

Если прежде чем начать выполнять действия из этого руководства у вас уже был установлен EmuNAND и вы хотите перенести содержимое EmuNAND в SysNAND с кастомной прошивкой - сейчас самый подходящий момент. Выполните действия из раздела [перенос EmuNAND](move-emunand), вместо выполнения этой части.
{: .notice--info}

1. Включите вашу консоль, зажав кнопку (START) и выберите GodMode9.bin
1. Перейдите в `[0:] SDCARD` -> `ctrtransfer`
1. Нажмите (A) чтобы выбрать файл `<серийный_номер_приставки>_nand.bin`, затем выберите "NAND image options...", затем "Restore SysNAND (safe)"
1. Нажмите (A), чтобы разрешить запись в SysNAND и введите указанную комбинацию кнопок
  + Это действие не перезапишет установленный arm9loaderhax
1. Введите указанную комбинацию кнопок чтобы разрешить запись в SysNAND (lvl1)
  + Этот процесс займет некоторое время
1. Когда процесс завершится, нажмите (A) для продолжения
1. Нажмите (START) для перезагрузки
  + Если после запуска экран чёрный, выполняйте инструкции из раздела [9.2.0 CTRTransfer](9.2.0-ctrtransfer)
  + Теперь вы снова можете безопасно переводить New 3DS в режим сна
1. Если ваш бэкап был сделан на прошивках от 3.0.0 до 4.5.0, консоль не запустится до тех пор, пока вы вручную не скачаете нужные файлы прошивки:
  + Скачайте [этот файл](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/00000056) и переименуйте его в `firmware.bin`
  + Скачайте [этот файл](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/cetk)
  + Скопируйте `firmware.bin` и `cetk` в папку `/luma/` на SD-карте
  + После обновления прошивки удалите оба этих файла
1. Обновите прошивку консоли, зайдя в Системные настройки (System Settings), затем "Прочие настройки" (Other Settings), затем листайте вправо до конца и выберите пункт "Обновление" (System Update)
  + Обновление консоли с установленным A9LH + Luma (установлено у вас) безопасно
  + Теперь вы снова можете безопасно переводить New 3DS в режим сна
  + При появлении ошибки, поставьте в настройках подключения, в настройках DNS "Получать DNS автоматически" в положение "Да"
  + Если вы все еще получаете ошибку и версия вашего NAND ниже 9.2.0, [выполните 9.2.0 CTRTransfer](9.2.0-ctrtransfer)
  
##### <a name="part5" />Часть V - Интеграция FBI

1. Перезагрузите консоль, зажав кнопку (START) и выберите GodMode9.bin
1. Перейдите в `[0:] SDCARD` -> `cias`
1. Нажмите (A) чтобы выбрать файл `FBI.cia`, затем выберите "CIA image options...", затем "Mount image to drive"
1. Нажмите (A) чтобы выбрать файл `.app`, затем выберите "NCCH image options", затем "Inject to H&S"
1. Нажмите (A), чтобы разрешить запись в SysNAND (lvl1) и введите указанную комбинацию кнопок
1. Нажмите (A), чтобы продолжить
1. Нажмите (START) для перезагрузки
1. Если при запуске "Информация о здоровье и безопасности" (Health & Safety) запускается не FBI и вы в прошлом понижали прошивку с помощью Gateway, перейдите в раздел [проблемы и их решения](troubleshooting#gw_fbi)

##### <a name="part6" />Часть VI - Установка CIA

1. Запустите "Информация о здоровье и безопасности" (Health and Safety) (теперь это FBI)
1. Перейдите в `SD` -> `cias`
1. Выберите "\<current directory>"
1. Выберите "Install all CIAs" и нажмите (A) для подтверждения
1. Нажмите (HOME) для выхода из FBI

##### <a name="part7" />Часть VII - DSP Dump

1. Запустите Homebrew Launcher из меню HOME
 + Если Homebrew Launcher не запускается, убедитесь что у вас включен Wi-Fi, стоит свежая версия hblloader и luma3DS
 + Если вместо Homebrew Launcher запускается Загружаемая игра (Download play), отключите приставку, удерживая кнопку включения, и заново запустите Homebrew Launcher.
1. Выберите "DSP Dump"
1. После завершения нажмите (START) для выхода из DSP Dump
1. Нажмите (START), чтобы открыть меню выхода из Homebrew Launcher

##### <a name="part8" />Часть VIII - Восстановление приложения Информация о здоровье и безопасности (Health and Safety)

Выполнение этой части опционально. В случае форматирования приставки с восстановленным H&S, [FBI придется интегрировать повторно](fbi)!
{: .notice--info}

1. Перезагрузите консоль, зажав кнопку (START) и выберите GodMode9.bin
1. Нажмите кнопку (HOME) для вызова меню
1. Выберите "More..."
1. Выберите "Restore H&S"
1. Нажмите (A), чтобы разрешить запись в SysNAND (lvl1) и введите указанную комбинацию кнопок

##### <a name="lumactrnand" />Часть IX - CTRNAND Luma3DS

Выполнение этой части позволит запускать приставку без SD-карты. 
{: .notice--info}

1. Находясь в Godmode9, перейдите в `[0:] SDCARD`
1. Нажмите (Y), выделив файл `arm9loaderhax.bin` чтобы скопировать его
1. Нажмите (B) для возврата в главное меню
1. Перейдите в `[1:] SYSNAND CTRNAND`
1. Нажмите (Y) чтобы вставить файл `arm9loaderhax.bin`
1. Выберите "Copy path(s)"
1. Нажмите (A) для подтверждения копирования
1. Введите указанную комбинацию клавиш для того, чтобы разрешить запись в системный раздел
1. Нажмите (B) для возврата в главное меню
1. Удерживая (R) нажмите (B), чтобы извлечь SD-карту
1. Извлеките SD-карту из консоли
1. Нажмите (START) для перезагрузки с извлеченной SD-картой
  + Необходимо хотя бы раз загрузиться без SD-карты, чтобы настроить Luma3DS, установленную в раздел CTRNAND
1. Нажимая (A) выберите следующие пункты:    
  + **"Show NAND or user string in System Settings"**
  + **"Enable game patching"**
1. Если у вас **New 3DS**, вы *также* можете включить следующие опции:
  + **"New 3DS CPU" выбрать значение "Clock+L2(x)"**
    + Это увеличит частоту кадров в множестве игр, но может отразиться на стабильности других
    + Если какие-либо игры работают некорректно, отключите эту опцию
1. Вставьте SD-карту обратно в консоль
1. Нажмите (START), чтобы сохранить настройки и перезагрузиться

##### <a name="freeshop" />Часть X - Настройка freeshop

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

    <div class="notice--info"><a href="{{ base_path }}/images/QR/freeshop.png"><div class="screenshot_image"><img src="{{ base_path }}/images/QR/freeshop-crop.png"></div></a></div>

1. Нажмите кнопку "Обновить кэш"
1. Перезагрузите freeshop

Если у вас freeshop ругается на неверные или отсутствующие ключи, скачайте предложенный [`zip-архив`](images/freeshop.zip) и распакуйте его содержимое с заменой в папку `/3ds/data` на вашей SD-карте (должно получится так: `/3ds/data/freeshop/файлы`), после чего перезагрузите freeshop.
{: .notice--warning}

Установка приложений из freeshop происходит с помощью кнопки (X)
{: .notice--info}

___

В случае проблем с работой DSi / DS (например, картриджи DS или DSiWare перестали работать), обратитесь к разделу [Проблемы и их решения](troubleshooting#twl_broken)
{: .notice--warning}

{% capture notice-10 %}
Теперь вы можете использовать Luma3DS Updater для обновления кастомной прошивки. Запустите его и нажмите (А). Это не тоже самое что Обновление системы (System Update). Приложение обновляет только файлы Luma3DS.
Обновятся только те файлы Luma3DS, которые находятся на SD-карте. Если вы включите консоль без SD-карты, она загрузится используя Luma3DS из CTRNAND.    
{% endcapture %}

<div class="notice--info">{{ notice-10 | markdownify }}</div>

{% capture notice-6 %}   
Теперь по умолчанию будет запускаться Luma3DS CFW SysNAND.    
Для запуска конфигуратора Luma3DS включите консоль с зажатой кнопкой (SELECT).
Для запуска меню Luma3DS chainloader включите консоль с зажатой кнопкой (START).
{% endcapture %}

<div class="notice--info">{{ notice-6 | markdownify }}</div>

В дальнейшем вы можете обновить arm9loaderhax, обратившись к разделу [обновление A9LH](updating-a9lh).
{: .notice--info}

Чтобы использовать [NTR CFW](https://github.com/44670/BootNTR/), установите [BootNTR Selector](https://gbatemp.net/threads/release-bootntr-selector.432911/).
{: .notice--info}

Сохраните свой бекап (`<серийный_номер_приставки>_nand.bin`). Используя GodMode9, с помощью этого файла, можно восстановить консоль в случае брика.
{: .notice--info}

Вы можете удалить бэкапы NAND из папки `/files9/` или `/CTRtransfer/` (если они там есть), при условии наличия резервной копии в безопасном месте.
{: .notice--info}

<div class="notice--info">Удалите все файлы связанные со взломом, кроме представленных на скриншоте:<br><br><a href="{{ base_path }}/images/screenshots/final-file-layout.png"><div class="screenshot_image"><img src="{{ base_path }}/images/screenshots/final-file-layout-crop.png"></div></a></div>

<div class="notice--info">{{ notice-7 | markdownify }}</div>

Чтобы узнать, как сменить регион своей консоли, обратитесь к разделу [Смена региона](region-changing).
{: .notice--success}

Чтобы узнать, как поддерживать A9LH в актуальном состоянии, обратитесь к разделу [Обновление A9LH](updating-a9lh).
{: .notice--success}

<a name="links" />
Различные инструкции, не имеющие прямого отношения ко взлому, однако помогающие лучше изучить возможности 3DS на кастомной прошивке и эффективнее ей пользоваться находятся [здесь](addons).
{: .notice--success}