---
title: "Обновление A9LH "
permalink: /updating-a9lh.html
---

### Крайняя версия: 3 ноября 2016

Собственно процесс установки arm9loaderhax подразумевает установку загрузчика, который на лету изменяет файлы, расположенные в системном разделе на NAND-чипе приставки, который припаян к самой материнской плате. Эти загрузчики обновляются редко и нужны только для запуска `arm9loaderhax.bin` с SD-карты, которая, в нашем случае, есть ни что иное как Luma3DS.
{: .notice}

Если вы не знаете какая конкретно версия arm9loaderhax установлена на вашей приставке, просто обновите текущую на самую новую. Хуже не будет.
{: .notice--info}

Если вы пользуетесь PIN-кодом на Luma, временно отключите его. Сможете снова включить после обновления. 
{: .notice--info}

Если вы используете загрузчик, не инициализирующий экран (например Bootanim9), следует переименовать его в `arm9loaderhax_si.bin` вместо `arm9loaderhax.bin`.
{: .notice--info}

Лишь после установки arm9loaderhax на o3ds можно использовать `data_input_v4`. Первоначальная установка a9lh на old3ds требует `data_input_v3` для совместимости со старой версией SafeA9LHInstaller, которую можно запустить через браузер. Версия в названии архива относится лишь к версии самого архива и не коррелирует с версий загрузчика. 
{: .notice--info}

Нижеследующая инструкция так же обновляет некоторые полезные загрузчики и базу ключей AES. 
{: .notice--success}

#### Что нужно:

* [`aeskeydb.bin`](torrents/aeskeydb.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:18b3a17f78e2376e05feaa150749d9fd689b25dc&dn=aeskeydb.bin&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* [`data_input_v4.zip`](torrents/data_input_v4.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:00f03ff69b5961307303d5e4778a2f65a528bf2d&dn=data%5Finput%5Fv4.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>* Свежая версия [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest)
* Свежая версия [arm9loaderhax](https://github.com/AuroraWright/arm9loaderhax/releases/latest)
* Свежая версия [SafeA9LHInstaller](https://github.com/AuroraWright/SafeA9LHInstaller/releases/latest)
* Свежая версия [Hourglass9](https://github.com/d0k3/Hourglass9/releases/latest)

#### Что делать: 

**Все нижеследующие действия обычно перезаписывают старые версии заменяемых файлов. Логично, что нужно соглашаться на замену.**

##### Часть I - Подготовка

1. Удалите `aeskeydb.bin` из корня карты памяти, если таковой файл есть.
13. Удалите папку `a9lh` из корня карты памяти.
2. Скопируйте скачанный `aeskeydb.bin` в папку `/files9/` в корне КП.
3. Скопируйте `Hourglass9.bin` из архива Hourglass9 в папку `/luma/payloads/`, а затем переименуйте `Hourglass9.bin` в `start_Hourglass9.bin`.
5. Скопируйте `arm9loaderhax.bin` из архива SafeA9LHInstaller  в папку `/luma/payloads`
9. Переименуйте `arm9loaderhax.bin` в `down_safea9lhinstaller.bin`.
7. Скопируйте папку`a9lh` из архива `data_input_v3.zip` в корень карты памяти.
8. Скопируйте содержимое архива arm9loaderhax (release.7z) в папку `a9lh` в корне КП.
8. Скопируйте  `arm9loaderhax.bin` из архива Luma3DS в корень карты памяти с заменой. 
9. Вставьте карту обратно в 3DS.

##### Часть II - Обновление загрузчика

10. Отключите питание, зажмите кнопку (ВНИЗ) и, не отпуская кнопку, включите приставку.
11. Нажмите (SELECT), чтобы обновить arm9loaderhax.
12. Отключите приставку и вновь вставьте КП в компьютер.
13. Удалите папку `a9lh` из корня карты памяти.
14. Удалите `down_safea9lhinstaller.bin` из папки `/luma/payloads`

##### Часть III - Настройка Luma3DS

15. Вставьте карту обратно в 3DS.
2. С помощью кнопки (А) отметьте следующие пункты:     
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R (A9LH)"**
  + **"Show NAND or user string in System Settings"**
3. Если у вас **New 3DS**, так же отметьте следующие пункты: 
  + **"New 3DS CPU" to "Clock+L2(x)"**
    + Это увеличит частоту кадров в некоторых играх.
    + Если какие-то игры работают некорректно, отключите эту опцию.
4. Нажмите (START), чтобы сохранить настройки и перезагрузиться. 

##### Часть IV - CTRNAND Luma3DS

16. Запустите FBI.
17. Выберите "SD".
4. Выберите arm9loaderhax.bin, нажмите (A) и выберите “Copy”.
9. Нажмите (B), чтобы вернуться в главное меню FBI.
10. Выберите "CTR NAND".
11. Выберите "\<current directory>".
12. Нажмите "Paste", затем нажмите (A) для подтверждения.
8. Выйдите из программы, нажатием кнопки (home).
9. Выключите 3DS и извлеките карту памяти. 
10. Включите устройство с зажатой кнопкой (SELECT).
  + Необходимо хотя бы раз загрузиться без карты памяти, чтобы настроить прошивку, расположенную в CTRNAND.
16. Нажимая (A) выберите следующие пункты: 
  + **"Show NAND or user string in System Settings"**
3. Если у вас **New 3DS**, так же отметьте следующие пункты: 
  + **"New 3DS CPU" to "Clock+L2(x)"**
    + Это увеличит частоту кадров в некоторых играх.
    + Если какие-то игры работают некорректно, отключите эту опцию.
14. Вставьте карту памяти в приставку и нажмите (START) для того, чтобы сохранить настройки и перезагрузить приставку. 
