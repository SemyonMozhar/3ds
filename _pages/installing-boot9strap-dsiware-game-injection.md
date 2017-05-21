---
title: "Установка boot9strap (Инъекция в игры DSiWare)" #
lang: ru
permalink: installing-boot9strap-dsiware-game-injection.html
sidebar:
  nav: "installing-boot9strap-dsiware-game-injection"
---

Обратите внимание, что в некоторых версиях Luma3DS, Luma3DS chainloader меню отображается только в том случае, если существует более чем одно приложение. Если существует только одно приложение, удержание (START) при включении консоли запустит GodMode9 напрямую.
{: .notice--info}

Для использования [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme)-ссылок в этом руководстве необходим torrent-клиент, например [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--success}

Прежде чем продолжить, убедитесь, вы прочитали все уведомления и предупреждения в [Установка boot9strap (DSiWare)](installing-boot9strap-dsiware)
{: .notice--danger}

#### <a name="what_need" />Что понадобится

* Две приставки
  + **Исходная 3DS**: 3DS с кастомной прошивкой (boot9strap или arm9loaderhax) *с последней версией системного ПО*
  + **Целевая 3DS**: 3DS с не взломаной прошивкой *11.4.0*
* Купленная (или уже имеющаяся) DSiWare-игра из eShop на **исходной 3DS**
  + Пиратская копия игры **НЕ** будет работать
  + Список совместимых игр ищите на странице [Установка boot9strap (Список уязвимых игр DSiWare)](installing-boot9strap-dsiware-game-injection-list)
* Версия sudokuhax injection `.zip`для вашего региона
  + [`DSiWare_usa_sudokuhax_injection.zip`](magnet:?xt=urn:btih:7ed7fee15c900ed02b5e2cb3c8e7a0363f4d9354&dn=DSiWare_usa_sudokuhax_injection.zip&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce)
  + [`DSiWare_eur_exidiahax_injection.zip`](magnet:?xt=urn:btih:046bb8023bc40b9a95a8a339c85a9ef18cf60db6&dn=DSiWare_eur_exidiahax_injection.zip&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce)
  + [`DSiWare_jpn_4swordshax_injection.zip`](magnet:?xt=urn:btih:1bcc90c93da91c9876671f6218084207def90db9&dn=DSiWare_jpn_4swordshax_injection.zip&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce)
* Свежая версия [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* Свежая версия [b9sTool](https://github.com/Plailect/b9sTool/releases/latest)
* Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
* 11.4.0 `.firm` соответствующий **целевой 3DS**
  + [11.4.0 New 3DS](magnet:?xt=urn:btih:3b59dd43eec3edb133555f58d1180bfb196acbb4&dn=2.54-0_11.4_NEW.firm&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  + [11.4.0 Old 3DS](magnet:?xt=urn:btih:0dd89d42ad711f770da899af05ee162ede0d0070&dn=2.54-0_11.4_OLD.firm&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)

#### <a name="instructions" />Инструкция

##### <a name="part1" />Часть I - Подготовительные работы

Используйте [save manager](https://github.com/J-D-K/JKSM/releases/latest) для того, чтобы сделать резервные копии всех важных сохранений на *целевой 3DS* (приставка будет отформатирована!)
{: .notice--warning}

1. Выключите **исходную 3DS**
1. Вставьте SD-карту **исходной 3DS** в компьютер
1. Скопируйте `GodMode9.firm` (или `GodMode9.bin` для пользователей arm9loaderhax) из `.zip-архива`GodMode9 в папку `/luma/payloads/` на SD-карте **исходной 3DS**
1. Скопируйте `.app` из `.zip-архива` с DSiWare injection, соответствующего региону консоли в корень SD-карты **исходной 3DS**
1. Скопируйте папку `savedata` из `.zip-архива` DSiWare injection в корень SD-карты **исходной 3DS**
1. Вставьте SD-карту в **исходную 3DS**
1. Включите **исходную 3DS** кнопкой питания, держа нажатой кнопку (Start), чтобы запустить меню Luma3DS chainloader
1. Запустите GodMode9, нажав кнопку (A)
1. Нажмите кнопку (HOME) для вызова меню
1. Выберите "More..."
1. Выберите "Backup NAND"
1. Нажмите (A), чтобы продолжить
1. Удерживая (R) нажмите (B) для того, чтобы извлечь SD-карту
1. Вставьте SD-карту **целевой 3DS** в компьютер
1. **Сохраните каждый файл на обеих SD-картах 3DS в две разные папки на компьютере (следите, какая из них какая)**
1. Вставьте SD-карты обратно в соответствующие 3DS
1. Нажмите (START) на **исходной 3DS** для перезагрузки

##### <a name="part2" />Часть II - Инъекция игры и сохранения

1. Включите **исходную 3DS** кнопкой питания, держа нажатой кнопку (Start), чтобы запустить меню Luma3DS chainloader
1. Запустите GodMode9, нажав кнопку (A)
1. Перейдите в `SDCARD`
1. Нажмите (Y) на `.app`-файле из архива с файлами для инжекта DSiWare, который вы скопировали на КП ранее
1. Нажмите (B) для возврата в главное меню
1. Перейдите в `SYSNAND TWNLN` -> `title` -> `00030004` -> `(8-ми значный ID)`
  + 8-значный ID смотрите на странице [Установка boot9strap (Список уязвимых игр DSiWare)](installing-boot9strap-dsiware-game-injection-list)
1. Перейдите в папку `content`
1. Нажмите (A) на `.app-файле`, находящемся в папке
1. Выберите "Inject data @offset"
1. Нажмите (A), чтобы выбрать смещение `00000000`
1. Нажмите (A), чтобы разрешить запись в SysNAND и введите указанную комбинацию кнопок
1. Нажмите (B) для возврата в главное меню
1. Перейдите в `SYSNAND TWNLN` -> `title` -> `00030004` -> `(8-ми значный ID)`
  + 8-значный ID смотрите на странице [Установка boot9strap (Список уязвимых игр DSiWare)](installing-boot9strap-dsiware-game-injection-list)
1. Перейдите в `data`
1. Нажмите (A) на `public.sav`
1. Выберите "Mount as FAT image"
1. Это вернет вас обратно в главное меню
1. Перейдите в `SDCARD`
1. Нажмите (Y) на файле(ах) в папке `savedata`, чтобы скопировать их
  + Если в папке `savedata`  есть папка `savedata`, это не по ошибке. Вам следует скопируйте вложенную папку `savedata`, а не файлы в ней.
1. Нажмите (B) для возврата в главное меню
1. Перейдите в `FAT IMAGE`
1. C помощью кнопки (X) удалите все содержимое папки `FAT IMAGE`
1. Нажмите (Y), чтобы вставить **содержимое** папки `savedata`в `FAT IMAGE`
1. Выберите "Copy path(s)"
1. Нажмите (A), чтобы разрешить запись в SysNAND и введите указанную комбинацию кнопок
1. Нажмите (START) для перезагрузки
1. Запустите DSiWare-игру на **исходной 3DS**
1. Нажмите на экран, либо на какую-либо кнопку, чтобы запустить игру и проверить, работает ли сохранение
  + Если вы используете файлы EUR региона (**Legends of Exidia**), после нажатия (A), либо (START) на двух первых экранах, выберите первый слот и нажмите "continue"
  + Если игра вылетает с ошибкой, касающейся `boot.nds`, **значит эксплойт работает и все в порядке!**
  + Если игра жалуется на поврежденный или неверный файл сохранения (corrupted or inaccessible), убедитесь, что скопировали именно **содержимое** папки `savedata`, а не саму папку
  + Если игра работает нормально безо всяких ошибок, значит вам следует остановится и выяснить на каком этапе вы допустили оплошность
  + Если появляется черный экран, обратитесь к разделу с [проблемами и их решениями](troubleshooting#twl_broken)
  + Если игра пропала из **целевой 3DS**, либо появляется ошибка сообщающая о повреждении, либо недоступности файла сохранения, [обратитесь к части с проблемами и их решениями](troubleshooting#ts_dsiware)

##### <a name="part3" />Часть III - Перенос системы

1. Если на **целевой 3DS** есть Nintendo Network ID, отформатируйте приставку, используя Системные настройки:
  + Перейдите на последнюю вкладку меню "Прочие настройки" (Other Settings), выберите пункт "Форматировать" (Format System Memory), следуйте инструкциям на экране
1. Прочитайте внимательно:
  + Ваша 3DS с CFW = "Исходная система"
  + Ваша 3DS с официальной прошивкой = "Целевая система"
  + **Переместите DSiWare по запросу!**
  + **НЕ** удаляйте содержимое карты памяти на исходной системе, даже по запросу
  + Убедитесь, что обе приставки заряжены и батарея не сядет ни у одной из них во время передачи данных
  + Если вы переносите данные с 2DS/Old 3DS (исходная) на New 3DS (целевая) и получили запрос на выбор метода переноса:
    **НЕ** выбирайте "Low-Capacity microSD Card Transfer" (опция 2), при таком варианте перенесутся только тикеты, а DSiWare-игры и, что важно, их сохранения - нет.
    + Быстрый способ: Выберите "PC-Based Transfer" (опция 3) и по запросу на экране приставке, скопировать содержимое SD-карты из исходной консоли на SD-карту целевой приставки (если у вас на Old 3DS\2DSстоит micro SD с переходником, можно просто переставить карту).
    + Медленный способ: Выберите "Wireless Transfer" (опция 1) для полного переноса **всего** содержимого SD-карты в целевую приставку по WiFi.
1. Перейдите по [этой ссылке](http://www.nintendo.ru/-/Nintendo-2DS-Nintendo-3DS/-Nintendo-3DS-Nintendo-3DS-XL-/-Nintendo-3DS-Nintendo-3DS-XL/-Nintendo-3DS-Nintendo-3DS-XL-592201.html) ([та же информация, но на английском](http://en-americas-support.nintendo.com/app/answers/detail/a_id/227/)) и следуйте официальным инструкциям от nintendo, держа в голове то, что вы прочитали чуть выше

##### <a name="part4" />Часть IV - Восстановление исходной 3DS

1. На **исходной 3DS**, завершите первоначальную настройку
1. Выполните одно из следующих действий
    + Продолжайте выполнять оставшуюся часть инструкции для **целевой 3DS**, а затем подождите неделю и выполните перенос данных уже с **целевой 3DS** на **исходную** *(помните, что вы не можете перенести данные с New 3DS на Old 3DS)*
    + Позвоните в Nintendo и скажите им, что у вас больше нет доступа к устройству, к которому привязан ваш NNID (в нашем случае, это уже **целевая 3DS**) и вы бы хотели	привязать аккаунт новому устройству (в нашем случае, это **исходная 3DS**)
    + Можете просто [удалить NNID](https://3ds.guide/troubleshooting#rm_nnid) из **исходной 3DS**, чтобы оставить его на **целевой 3DS**
1. Перезагрузите **исходную 3DS**, удерживая нажатой кнопку (Start), чтобы запустить меню Luma3DS chainloader
1. Запустите GodMode9, нажав кнопку (A)
1. Перейдите в `[0:] SDCARD`
1. Нажмите (A) чтобы выбрать `.bin` файл вашего NAND, затем выберите "NAND image options...", затем "Restore SysNAND (safe)"
1. Нажмите (A), чтобы разрешить запись в SysNAND и введите указанную комбинацию кнопок
  + Это действие не перезапишет установленный boot9strap
1. Введите указанную комбинацию кнопок чтобы разрешить запись в SysNAND (lvl1)
  + Этот процесс займет некоторое время
1. По завершению процесса, нажмите (A)
1. Нажмите (START) для того, чтобы перезагрузить **исходную 3DS**

##### <a name="part5" />Часть V - Резервное копирование FIRM целевой 3DS

1. 1. Скопируйте `boot.nds` в корень SD-карты **целевой 3DS**
1. Создайте папку `boot9strap` в корне SD-карты **целевой 3DS**
1. Скопируйте `.firm` от 11.4, соответствующий **целевой 3DS** в папку `boot9strap`на SD-карте **целевой 3DS**
1. Скопируйте `boot9strap.firm` из `.zip-архива` boot9strap в папку `/boot9strap/` в корне SD-карты
1. Запустите b9sTool, запустив инфицированную DSiWare на **целевой 3DS**
  + Если игра не запускает b9sTool, [следуйте инструкциям из части с проблемами и их решениями](troubleshooting#ts_dsiware)
1. Выберите "Dump f0f1", чтобы сделать резервную копию FIRM **целевой 3DS**
1. Запомните место положения бекапа FIRM
1. Закройте b9sTool
  + При необходимости выключите приставку, удерживая кнопку питания
1. Вставьте SD-карту в компьютер и скопируйте `F0F1_N3DS.bin` или `F0F1_O3DS.bin`(в зависимости от типа вашего устройства) в безопасное место; сделайте их резервные копии в нескольких местах; эти файлы помогут вам восстановить приставку в случае брика, если что-то пойдет не так

##### <a name="part6" />Часть VI - Прошивка FIRM целевой 3DS

**НЕ используйте b9sTool на приставках с установленным arm9loaderhax. Это гарантированно приведет к БРИКУ!**
{: .notice--danger}

1. Откройте b9sTool, запустив DSiWare игру на **целевой 3DS**
1. Выберите "Install boot9strap" и подтвердите выбор
1. Закройте b9sTool, затем выключите консоль
  + При необходимости выключите консоль принудительно, удерживая кнопку питания
1. Ваша консоль загрузится в boot9strap, затем автоматически выключится, поскольку запускаемого файла еще нет

___

Следующий шаг: [Завершение установки](finalizing-setup)
{: .notice--success}