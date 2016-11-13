---
title: "NTR и Cubic Ninja"
permalink: /ntr-and-cubic-ninja.html
---

**NTR Cubic Ninja работает ТОЛЬКО для JPN New 3DS!**
{: .notice--warning}

#### What you need

* [JPN Cubic Ninja](https://www.amazon.com/dp/B004QL7M0A)
* The Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
* Свежая версия [Decrypt9WIP9](https://github.com/d0k3/Decrypt9WIP/releases/latest)
* [`3ds-private-update-server.zip`](torrents/3ds-private-update-server.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:8623e580752f22940d96630ef723ce30a707b22e"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* [WAMPSERVER (PHP 5.5) 2.5](http://www.wampserver.com/en/#download-wrapper)
* [`node.exe`](http://nodejs.org/dist/latest/win-x86/node.exe)
* [`update.php`](torrents/update.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:cd7e59ea9744115913b561dbde15f8d68e713507"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* Версия v3.2 [NTR CFW](https://github.com/44670/BootNTR/releases/tag/3.2)
* Свежая версия [NTR Debugger](torrents/NTR%20Debugger.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:66274cee542bef7745792714673bf2be4d606496"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* Прошивка 9.2.0: 
 +    [New 3DS 9.2.0 - JPN](torrents/9.2.0-20J(Full)_n3DS.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:c8630ed31b53637b9023bd4dc1ce38362bb8ecd9"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>     

#### Что делать:

##### Часть I - Подготовка

1. Установите WAMP в папку по умолчанию.
2. Скопируйте содержимое `3ds-private-update-server.zip` в папку `C:\wamp\www\` (соглашайтесь на замену).
3. Скопируйте `update.php` в `C:\wamp\www\` (соглашайтесь на замену).
4. Скопируйте папку `updates` из архива с прошивкой в папку `C:\wamp\www\`.
5. Переместите `node.exe` в папку `C:\wamp\www\updates`.
6. Переместите `C:\wamp\www\CdnCiaUnpack.js` в папку `C:\wamp\www\updates`.
7. В папке `C:\wamp\www\updates` перетяните мышкой файл `CdnCiaUnpack.js` на `node.exe`, чтобы создать `GetSystemUpdate.partial.xml`.
8. Переместите `node.exe` и `CdnCiaUnpack.js` обратно в папку `C:\wamp\www\`.
9. Скопируйте `GetSystemUpdate.partial.xml` в папку `C:\wamp\www\` (таким образом по копии этого файла будут находится в папках `C:\wamp\www\updates` и `C:\wamp\www\`).
9. Нажмите на иконке WAMP в трее Windows, и выберите пункт "Put Online".
10. Нажмите Win+R и в появившейся строке наберите "CMD".
11. Введите команду "ipconfig" в командной строке, чтобы получить IPv4-адрес вашего компьютера. Он понадобится вам в дальнейшем. 
11. Скопируйте `ntr.bin` в корень карты памяти.
12. Создайте папку `files9` в корне КП, если таковой нет.
1. Скопируйте _содержимое_ архива `starter.zip` в корень карты памяти и вставьте ее обратно в 3DS.
2. Скопируйте папку `Decrypt9WIP` из архива Decrypt9WIP в папку `/3ds/` на карте памяти.

##### Часть II - Обновление

1. Загрузите 3DS в режим восстановления, удерживая (L)+(R)+(A)+(ВВЕРХ) во время включения приставки.
2. Отклоните предложение обновиться и перезагрузите приставку.
3. Запустите Cubic Ninja (если у вас уже был установлен NinjHax, удерживайте (L)+(R)+(X)+(Y) чтобы сбросить его).
4. Выберите "Create", затем "QR Code", затем "Scan QR Code".
5. Отсканируйте QR-код, содержащийся в архиве NTR CFW и соответствующий вашему региону. 
6. На домашнем экране нажмите одновременно (X)+(Y), чтобы попасть в меню NTR. 
7. Включите дебаггер (Enable the debugger) и закройте меню. 
8. Используйте web-интерфейс своего роутера, чтобы узнать IP-адрес вашей консоли (если не знаете, как это сделать - -гуглите; все роутеры разные). 
9. Запустите NTR Debugger на компьютере. 
10. Введите указанные команды (замените 192.168.X.XXX IP-адресом вашей 3DS, а 192.168.Y.YYY IP-адресом вашего компьютера).    
    + `connect("192.168.X.XXX", 8000)`
    + `write(0x15E424, tuple(map(ord, "http://192.168.Y.YYY/update.php\0")), pid=0x25)`
    + `write(0x15E0EC, tuple(map(ord, "http://192.168.Y.YYY/update.php\0")), pid=0x25)`
    + `write(0x15E463, tuple(map(ord, "http://192.168.Y.YYY/update.php\0")), pid=0x25)`
11. Обновите вашу 3DS, перейдя в Системные настройки (System Settings), "Прочие настройки" (Other Settings), "Обновление" (System Update).

___

Продолжайте [установку arm9loaderhax](Installing-arm9loaderhax).
