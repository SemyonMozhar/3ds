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

**Никогда не используйте OTP от другой консоли, это ГАРАНТИРОВАННО приведёт к брику**
{: .notice--danger}

**НИКОГДА не обновляйте New 3DS с прошивкой 2.1.0 (это старая прошивка Old 3DS), это чревато БРИКОМ! Сначала ОБЯЗАТЕЛЬНО восстановите NAND из резервной копии или произведите обратный ctrtransfer на стандартную прошивку New 3DS!**
{: .notice--danger}

{% capture notice %}
**Вы ГАРАНТИРОВАННО получите НЕВОССТАНАВЛИВАЕМЫЙ брик, если вы введете New 3DS с прошивкой 2.1.0 в режим сна! После того, как прошивка из бекапа будет восстановлена, закрывать крышку приставки снова будет безопасно**
**Это происходит только при закрытии крышки, _пока устройство включено_; это не касается выключения консоли.**
**Устройство переходит в спящий режим только когда крышка закрыта. Таймера, или чего-то похожего, в системе нет.**
**Оказавшись на 2.1.0 без промедления сделайте все необходимые шаги, чтобы избежать этого!**
{% endcapture %}


#### <a name="steps" />Описание шагов

В этом разделе мы, наконец, сделаем то, к чему вели все предыдущие шаги: установим arm9loaderhax.

Можно уверенно заявить, что arm9loaderhax - наилучший из возможных типов эксплойтов. Все потому, что он устанавливается непосредственно в раздел NAND firm и запускается ДО запуска операционной системы приставки. Кроме прочего, a9lh работает с **любой** прошивкой и, благодаря тому, что запускается до ОС, в большинстве ситуаций, удалить его случайно не выйдет. А еще этот эксплойт позволяет запускать различного рода загрузчики, которые помогут восстановить консоль даже из тех состояний, которые в обычном случае привели бы вас в сервисный центр. 

Файл `arm9loaderhax.bin` - это то, что arm9loaderhax запускает после загрузки из NAND, и этот файл может быть любым arm9-приложением. Этот файл может быть заменён когда угодно, однако Luma3DS позволяет запускать другие arm9 приложения, используя свой загрузчик.

Мы используем Luma3DS от [AuroraWright](https://github.com/AuroraWright/), чтобы запускать пропатченный SysNAND напрямую, поэтому необходимость в каком-либо виде EmuNAND полностью пропадает, что значительно упрощает использование взломанной 3DS и экономит место на SD-карте.

После установки arm9loaderhax и настройки Luma3DS мы восстановим бэкап прошивки, сделанный ранее.

В процессе мы установим и настроим следующие программы:    

+  **FBI** *(установщик приложений и игр в формате CIA)*
+  **Luma3DS Updater** *(Удобное обновление CFW)*
+  **Hourglass9** *(многофункциональная утилита для работы с NAND и картриджами)*
+  **freeshop** *(open source клон eShop, облегчающий поиск игр)*

#### <a name="what_need" />Что понадобится

* <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [`aeskeydb.bin`](magnet:?xt=urn:btih:18b3a17f78e2376e05feaa150749d9fd689b25dc&dn=aeskeydb.bin&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [`fbi-2.4.2-injectable.zip`](magnet:?xt=urn:btih:f978b4cf5eda72823240b9c649f3fd2940a9f525&dn=fbi-2.4.2-injectable.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [`data_input_v3.zip`](magnet:?xt=urn:btih:a1195c9f7ab650fa7c7bf020b51fc19ea8d9440c&dn=data%5Finput%5Fv3.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* Свежая версия [SafeA9LHInstaller](https://github.com/Plailect/SafeA9LHInstaller/releases/latest) *(`.7z`-архив)*
* Свежая версия [arm9loaderhax](https://github.com/AuroraWright/arm9loaderhax/releases/latest) *(`.7z`-архив)*
* Свежая версия [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(`.7z`-архив)*
* Свежая версия [hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases/latest)
* Свежая версия [Hourglass9](https://github.com/d0k3/Hourglass9/releases/latest)
* Свежая версия [Luma3DS Updater](https://github.com/Hamcha/lumaupdate/releases/latest)
* Свежая версия [DspDump](https://github.com/Cruel/DspDump/releases/latest)
* Свежая версия [FBI](https://github.com/Steveice10/FBI/releases/latest)
* Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
* Свежая версия [freeshop](http://get.freeshop.pw/latest) (зеркало на [я.диске](https://yadi.sk/d/OVaX2Caz3Bebgd) и [меге](https://mega.nz/#!h58BVIbI!-iO7mCAeulNBGDqnuo5mjHuKO2N9yBB2EVzWlJ7BFyY)). 

Если у вас не выходит скачать freeshop или другие файлы, воспользуйтесь VPN. 
{: .notice--warning}

#### <a name="instructions" />Инструкция

##### <a name="part1" />Часть I - Подготовительные работы

{% capture notice-5 %}
**Убедитесь в том, что ваша SD-карта исправна!**

**Использование неисправной карты может привести к БРИКУ!**

**Если вы не уверены, что SD-карта исправна, рекомендуется проверить eё на ошибки с помощью [H2testw (Windows)](h2testw-windows), [F3 (Linux)](f3-linux), или [F3X (Mac)](f3x-mac)!**
{% endcapture %}

<div class="notice--danger">{{ notice-5 | markdownify }}</div>

1. **Если на SD-карте есть папка `/files9/`, скопируйте ее в надежное место на вашем компьютере и сделайте несколько резевных копий в нескольких местах (например, облачное хранилище). Файлы в этой папке помогут избежать полной потери данных, в случае поломки консоли**
2. Создайте папку `cias` в корне SD-карты
3. Удалите папку `3ds` из корня SD-карты, если таковая существует
5. Скопируйте _содержимое_ папки `starter` из архива `starter.zip` в корень вашей SD-карты
  + Этот архив содержит новую папку `3ds`, которая заменит удаленную
6. Скопируйте _содержимое_ `.7z-архива` SafeA9LHInstaller в корень SD-карты
7. **Скопируйте папку `a9lh` из `.zip-архива` `data_input` в корень SD-карты**
8. Скопируйте _содержимое_ `.7z-архива` arm9loaderhax в папку `a9lh` в корне SD-карты
9. Скопируйте `hblauncher_loader.cia` из архива hblauncher_loader в папку `/cias/` в корне SD-карты
10. Скопируйте `lumaupdater.cia` из архива Luma3DS Updater в папку `/cias/` в корне SD-карты
11. Скопируйте `FBI.cia` из архива FBI в папку `/cias/` в корне SD-карты
11. Скопируйте `freeShop-latest.cia` в папку `/cias/` в корне SD-карты
12. **Скопируйте `arm9loaderhax.bin` из `.7z-архива` Luma3DS в корень SD-карты, соглашаясь на перезапись файлов**
13. Создайте папку `luma` в корне SD-карты
14. Создайте папку `payloads` в папке `luma` на SD-карты
15. Скопируйте `Hourglass9.bin` из `.zip-архива` Hourglass9 в папку `/luma/payloads/` в корне SD-карты и переименуйте `Hourglass9.bin` в `start_Hourglass9.bin`
17. Скопируйте `aeskeydb.bin` в папку `/files9/` в корне SD-карты
18. Скопируйте `DspDump.3dsx` в папку `/3ds/` в корне SD-карты
19. Скопируйте _содержимое_ архива `fbi-2.4.2-injectable.zip` в папку `/files9/` в корне SD-карты
20. Вставьте SD-карту обратно в 3DS

##### <a name="part2" />Часть II - Установка arm9loaderhax

**НИКОГДА не обновляйте New 3DS с прошивкой 2.1.0 (это старая прошивка Old 3DS), это чревато БРИКОМ! Сначала ОБЯЗАТЕЛЬНО восстановите NAND из резервной копии или произведите обратный ctrtransfer на стандартную прошивку New 3DS!**
{: .notice--danger}

{% capture notice %}
**Вы ГАРАНТИРОВАННО получите НЕВОССТАНАВЛИВАЕМЫЙ брик, если вы введете New 3DS с прошивкой 2.1.0 в режим сна! После того, как прошивка из бекапа будет восстановлена, закрывать крышку приставки снова будет безопасно**
**Это происходит только при закрытии крышки, _пока устройство включено_; это не касается выключения консоли.**
**Устройство переходит в спящий режим только когда крышка закрыта. Таймера, или чего-то похожего, в системе нет.**
**Оказавшись на 2.1.0 без промедления сделайте все необходимые шаги, чтобы избежать этого!**
{% endcapture %}

1. Необходимо находиться на прошивке 2.1.0.
2. Откройте `https://goo.gl/xUMUJB` в браузере 3DS (нужно вводить адрес не в поиск, а именно перейти по нему, воспользовавшись кнопкой URL)
   + Если появляется ошибка "This service is not available in your region", поменяйте регион в Системных настройках (System Settings) на соответствующий тому, который был установлен при 2.1.0 ctrtransfer
   + При возникновении другой ошибки, обратитесь к разделу [Проблемы и их решения](troubleshooting#ts_browser)
   + Если на экране видны искажения, обратитесь к разделу [Проблемы и их решения](troubleshooting#ts_safe_a9lh_screen)
   + Если вы забыли включить Wi-Fi на 2DS или New 3DS, это можно сделать, вытащив батарею и отключив зарядное устройство на несколько секунд, а затем снова включить консоль
3. Нажмите (SELECT) для установки.
4. Установщик поставит arm9loaderhax на вашу консоль (буквально за секунду)
5. Нажмите любую кнопку для выключения консоли
6. Достаньте карту памяти из приставки и вставьте ее в ПК.
7. Скопируйте уникальный для вашей консоли файл `otp.bin` из папки `/a9lh/` на SD-карте в надежное место на вашем компьютере и сделайте несколько резевных копий в нескольких местах (например, облачное хранилище), вставьте SD-карту обратно в 3DS
8. Верните SD-карту обратно в консоль
  
##### <a name="part3" />Часть III - Настройка Luma3DS

1. Включите вашу консоль, зажав кнопку (SELECT), чтобы попасть в меню настроек Luma3DS
  + Важно зажать кнопку до того, как включать приставку
  + Если после включения экран остаётся чёрным, то перейдите к разделу [проблемы и их решения](troubleshooting#ts_sys_a9lh)
  + Если после загрузки запускается SafeA9LHInstaller, то перейдите к разделу [проблемы и их решения](troubleshooting#ts_safe_a9lh)
2. Нажимая (A) выберите следующие пункты:    
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R"**
  + **"Show NAND or user string in System Settings"**
3. Если у вас **New 3DS**, вы *также* можете в пункте **"New 3DS CPU" выбрать значение "Clock+L2(x)"**
  + Это увеличит частоту кадров в множестве игр, но может отразиться на стабильности других
  + Если какие-либо игры работают некорректно, отключите эту опцию
  + **Если у вас 11.3 и вам нужен Homebrew Launcher, отключите эту опцию.**
4. Нажмите (START), чтобы сохранить настройки и перезагрузиться. 
  + Если после включения экран остаётся чёрным, выключите приставку и переходите к следующей части   
  + Если появляется ошибка "Failed to mount CTRNAND", просто переходите к следующей части     
  
##### <a name="part4" />Часть IV - Восстановление системы

Если прежде чем начать выполнять действия из этого руководства у вас уже был установлен EmuNAND и вы хотите перенести содержимое EmuNAND в SysNAND с кастомной прошивкой - сейчас самый подходящий момент. Выполните действия из раздела [перенос EmuNAND](move-emunand), вместо первых 4 шагов в этой части.
{: .notice--info}

Если бекапа нет, то следуйте рекомендациям из [раздела с 9.2.0 ctrtransfer](9.2.0-ctrtransfer). После выполнения инструкций  переходите сразу к [Часть VI - Заключительная настройка](installing-arm9loaderhax#part6).
{: .notice--info}

1. Включите вашу консоль, зажав кнопку (START), чтобы запустить Hourglass9
2. Перейдите в "SysNAND Backup/Restore"
3. Перейдите в "SysNAND Restore (keep a9lh)"
2. Введите комбинацию кнопок, указанную на экране, затем выберите образ `NANDmin.bin` и нажмите (A)
4. Нажмите (START) для перезагрузки
  + Если после запуска экран чёрный, выполняйте инструкции из раздела [9.2.0 ctrtransfer](9.2.0-ctrtransfer)
5. Если ваш бэкап был сделан на прошивках от 3.0.0 до 4.5.0, консоль не запустится до тех пор, пока вы вручную не скачаете нужные файлы прошивки:
  + Скачайте [этот файл](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/00000056) и переименуйте его в `firmware.bin`
  + Скачайте [этот файл](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/cetk)
  + Скопируйте `firmware.bin` и `cetk` в папку `/luma/` на SD-карте
  + После обновления прошивки на 3DS удалите оба этих файла
6. Обновите прошивку 3DS. Для этого зайдите в Системные настройки, затем "Прочие настройки" (Other Settings), листайте вправо до тех пор, пока не дойдете до предпоследнего пункта - Обновление ("System Update")
  + Обновление консоли с установленным A9LH + Luma (который стоит у вас) безопасно, прекратите переспрашивать
  + Запрет на обновление New 3DS с прошивкой 2.1.0 не действует после восстановления бэкапа.
  + При появлении ошибки, поставьте в настройках подключения, в настройках DNS "Получать DNS автоматически" в положение "Да"
  + Если вы все еще получаете ошибку и версия вашего NAND ниже 9.2.0, [выполните 9.2.0 ctrtransfer](9.2.0-ctrtransfer)

##### <a name="part5" />Часть V - Интеграция FBI

1. Включите вашу консоль, зажав кнопку (START), чтобы запустить Hourglass9
2. Перейдите в "SysNAND Backup/Restore", затем "Health&Safety Dump", чтобы сохранить оригинал приложения Информация о здоровье и безопасности (Health & Safety) в файл `hs.app` **(стрелками (ВВЕРХ) и (ВНИЗ) / (ВЛЕВО) и (ВПРАВО) можно менять название файла)**
3. Нажмите (B), затем выберите "Health&Safety Inject"
4. Введите комбинацию кнопок, указанную на экране
5. Выберите файл с интегрированным FBI формата `.app` соответствующий вашему региону
6. Нажмите (A) для подтверждения. 
7. Нажмите (START) для перезагрузки.
8. Если при запуске Health & Safety запускается не FBI и вы в прошлом понижали прошивку при помощи Gateway, милости просим в раздел [проблемы и их решения](troubleshooting#gw_fbi).

##### <a name="part6" />Часть VI - Заключительная настройка

1. Запустите "Информация о здоровье и безопасности" (Health and Safety) (теперь это FBI)
2. Выберите "SD"
3. Перейдите в папку "cias"
4. Выберите `<current directory>`
5. Выберите "Install all CIAs" и нажмите (A) для подтверждения
6. Установятся все приложения, находящиеся в этой папке. 
7. Нажмите (B), чтобы вернуться в папку "SD"
8. Выберите файл `arm9loaderhax.bin`, нажмите (A) и выберите “Copy”
9. Нажмите (B), чтобы вернуться в главное меню FBI
10. Выберите "CTR NAND"
11. Выберите "\<current directory>"
12. Выберите "Paste", затем нажмите (A) для подтверждения
13. Выйдите из FBI нажатием кнопки (HOME)
14. Запустите Homebrew Launcher из меню HOME
15. Выберите "DSP Dump"
16. После завершения нажмите (START) для выхода
17. Достаньте SD-карту из приставки
17. Нажмите (START), чтобы открыть меню выхода из Homebrew Launcher
18. Нажмите (A), чтобы перезагрузиться
  + Для того, чтобы настроить Luma3DS, установленную в раздел CTRNAND, необходимо хотя бы раз загрузить консоль с извлеченной SD-картой.
23. Нажимая (A) выберите следующие пункты:    
  + **"Show NAND or user string in System Settings"**
24. Если у вас **New 3DS**, вы *также* можете в пункте **"New 3DS CPU" выбрать значение "Clock+L2(x)"**
  + Это увеличит частоту кадров в множестве игр, но может отразиться на стабильности других
  + Если какие-либо игры работают некорректно, отключите эту опцию
  + **Если у вас 11.3 и вам нужен Homebrew Launcher, отключите эту опцию.**
25. Вставьте SD-карту в приставку и нажмите (START) для того, чтобы сохранить настройки и перезагрузить приставку!

___


В случае проблем с работой DSi / DS (например, картриджи DS или DSiWare перестали работать), обратитесь к разделу [Проблемы и их решения](troubleshooting#twl_broken)
{: .notice--warning}

{% capture notice-10 %}
Теперь вы можете использовать Luma3DS Updater для обновления кастомной прошивки. Запустите его и нажмите (А).
Это не тоже самое что Обновление системы (System Update). Это приложение обновляет только файлы Luma3DS.
Это обновит только те файлы Luma3DS, которые находятся на SD-карте. Если вы включите консоль без SD-карты, она загрузится используя Luma3DS из CTR NAND.
{% endcapture %}

<div class="notice--info">{{ notice-10 | markdownify }}</div>

{% capture notice-6 %}   
Теперь при старте ваша консоль по умолчанию загружает кастомную прошивку.
Для запуска конфигуратора Luma3DS включите консоль с зажатой кнопкой (SELECT).
Для запуска Hourglass9 включите консоль с зажатой кнопкой (START).
{% endcapture %}

<div class="notice--info">{{ notice-6 | markdownify }}</div>

В дальнейшем вы можете обновить arm9loaderhax, обратившись к разделу [обновление A9LH](updating-a9lh).
{: .notice--info}

Чтобы установить [NTR CFW](https://github.com/44670/BootNTR/), поместите `ntr.bin` из архива с подходящей версией с [этой страницы](https://github.com/44670/BootNTR/releases) в корень SD-карты. Затем установите [`BootNTR.cia`](https://github.com/astronautlevel2/BootNTR/releases/latest).
{: .notice--info}

Сохраните свой `NANDmin.bin`. Используя Hourglass9, этим файлом можно восстановить консоль в случае брика, если что-то пойдёт не так.
{: .notice--info}

Вы можете удалить бэкапы NAND из папки `/files9/`, при условии наличия резервной копии в безопасном месте.
{: .notice--info}

{% capture notice-7 %}
**Вы можете удалить все ненужные файлы и папки в корне SD-карты, кроме следующиих:**

    + 3ds
    + files9
    + hblauncherloader
    + luma
    + Nintendo 3DS
    + arm9loaderhax.bin
    + boot.3dsx
	
{% endcapture %}

<div class="notice--info">{{ notice-7 | markdownify }}</div>

Чтобы узнать, как сменить регион своей консоли, обратитесь к разделу [Смена региона](region-changing).
{: .notice--success}

Чтобы узнать, как поддерживать A9LH в актуальном состоянии, обратитесь к разделу [Обновление A9LH](updating-a9lh).
{: .notice--success}

<a name="part7" />
• [Ответы на вопросы, которые у вас почти наверняка возникли](https://vk.com/3ds_cfw?w=wall-125012133_1073%2Fall)
• Для справки об использовании различных функций Luma3DS обратитесь к её [вики](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage) (англ.).
• [Как делать резервные копии, редактировать и восстанавливать](https://gbatemp.net/threads/release-jks-savemanager-Homebrew-cia-save-manager.413143/) сохранения игр.    
• Как настроить внешний вид домашнего экрана кастомными [темами](themes) и [жетонами](badges) с помощью программ [СHMM2](http://rinnegatamante.it/site/3ds_hbs.php) и [GYTB](https://github.com/MrCheeze/GYTB).    
• [Как ставить игры?](http://vk.com/3ds_cfw?w=wall-125012133_147%2Fall)   
• [Как настроить freeshop](https://vk.com/3ds_cfw?w=wall-125012133_847%2Fall)   
• [Конвертировать 3DS-ромы в CIA](https://rashevskyv.github.io/3ds-to-cia)   
{: .notice--success}