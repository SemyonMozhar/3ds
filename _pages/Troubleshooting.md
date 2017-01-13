---
title: "Проблемы и их решения"
permalink: /troubleshooting.html
sidebar:
  nav: "troubleshooting"
---

Если Ваша приставка не загружается, то просмотрите варианты, перечисленные ниже, и воспользуйтесь советом, который там дан. После этого можете дальше следовать основной инструкции.
(Гайд весьма обширен, рекомендуем пользовать поиск браузера - Ctrl+F).
{: .notice--primary}

**Если решения Вашей проблемы здесь не оказалось, то соберите в одну кучу все log файлы, что найдете в корне карты памяти девайса и киньте их на [Gist](https://gist.github.com/), а затем пишите мне. И не забудьте как можно детальнее описать свою проблему (*русскоязычным лучше конечно обращаться не к Plailect, а к нам - [3ds_cfw](http://vk.com/3ds_cfw) - прим. пер.*)**
{: .notice--info}

## <a name="twl_broken" />Я закончил гайд, но DSi / DS игры не работают.

#### Что нужно: 

* TWL_FIRM `.cia`, соответствующие вашему устройству
    + [`New_3DS TWL_FIRM - v9936.cia`](magnet:?xt=urn:btih:eab8558c97b18b1f329a2bfcc3c899b84c082a27&dn=New%5F3DS%20TWL%5FFIRM%20-%20v9936.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
    + [`Old_3DS TWL_FIRM - v8817.cia`](magnet:?xt=urn:btih:17511eadb6e6f3ff22d04f90644e37bd2d96ca43&dn=Old%5F3DS%20TWL%5FFIRM%20-%20v8817.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* [`TWL Version Data - v0.cia`](magnet:?xt=urn:btih:4a106681407fede5de95cc8bda635432481f6b5d&dn=TWL%20Version%20Data%20-%20v0.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* [`DS Internet - v2048.cia`](magnet:?xt=urn:btih:2b9df8496922f2546dfb0b01220068ce53c19d3d&dn=DS%20Internet%20-%20v2048.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* [`DS Download Play - v1024.cia`](magnet:?xt=urn:btih:b581d3c5d98f5e621fddfc1ce5704bb45bf05a8c&dn=DS%20Download%20Play%20-%20v1024.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* [`Nintendo DS Cart Whitelist - v11264.cia`](magnet:?xt=urn:btih:7b90d506ad032a581a00035616eaa17a68c48eff&dn=Nintendo%20DS%20Cart%20Whitelist%20-%20v11264.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
 
#### Что делать:

##### Часть I - Подготовка

1. Создайте папку `cias` в корне карты памяти.
1. Скопируйте `TWL Version Data - v0.cia` в папку `/cias/` вашей карты памяти.
2. Скопируйте `DS Download Play - v1024.cia` в папку `/cias/` вашей карты памяти.
3. Скопируйте `DS Internet - v2048.cia` в папку `/cias/` вашей карты памяти.
4. Скопируйте `Nintendo DS Cart Whitelist - v11264.cia` в папку `/cias/` вашей карты памяти.
5. Скопируйте `New_3DS TWL_FIRM - v9936.cia`  или `Old_3DS TWL_FIRM - v8817.cia` в папку `/cias/` вашей карты памяти.

##### Часть II - Установка

1. Запустите FBI.
3. Выберите "SD".
4. Выберите "cias".
5. Наведите курсор на <current directory>, нажмите (А).
9. Выберите Install all CIAs.
8. Нажмите кнопку (home) для перехода на домашний экран. 

## <a name="rm_nnid" />Удаление NNID без форматирования устройства

#### Что нужно:

* Свежая версия [GodMode9](https://github.com/d0k3/GodMode9/releases/)

#### Что делать:

1. Скопируйте `GodMode9.bin` из архива GodMode9 в папку `/luma/payloads/` на вашей карте памяти и переименуйте `GodMode9.bin` в `up_GodMode9.bin`.
12. Перезагрузите приставку, удерживая (ВВЕРХ), чтобы запустить GodMode9.
14. Перейдите в `SYSNAND CTRNAND` -> `data` -> (32-х-значный ID) -> `sysdata` -> `00010038`
15. Нажмите (X), удерживая (R) на файле `00000000`, чтобы переименовать его. 
16. Нажмите (ВВЕРХ), чтобы переименовать файл в `10000000`.
17. Нажмите (A), чтобы сохранить изменения.
18. Нажмите (A), чтобы разблокировать SysNAND для записи, а затем введите указанную клавишную комбинацию для подтверждения.
18. Вернитесь в главное меню.
16. Нажмите (START) для перезагрузки.

## <a name="gw_fbi" />Не выходит сделать инжект в Health and Safety после даунгрейда с помощью Gateway. 
Проблема часто встречается у тех, кто даунгрейдил при помощи Gateway. Суть в том, что метод даунгрейда гейта очень несовершенен. В ходе этой процедуры все системные приложения дублируются. Хоть они и не мешают работе, Decrypt9 спотыкается и не может понять в какой из H&S ему делать инжект, а в какой нет. 

#### Что нужно:

* Свежая версия [GodMode9](https://github.com/d0k3/GodMode9/releases/)

#### Что делать: 

1. Скопировать `GodMode9.bin` из GodMode9 zip в папку `/luma/payloads` на карте памяти и переименовать его из `GodMode9.bin` в `up_GodMode9.bin`.
2. Вставить КП обратно в 3DS. 
5. Открыть GodMode9 из arm9loaderhax. Для этого нужно зажать кнопку (ВВЕРХ), а затем, не отпуская кнопку, включить консоль.      
**(Будьте ОЧЕНЬ внимательны и осторожны! Эта программа в кривых руках может брикнуть приставку; не спасет даже a9lh)**
2. Перейдите в `SYSNAND CTRNAND` -> `title` -> `00040010`.
7. Перейдите в папку, соответствующую вашему регион и типу приставки:
  + **Old 3DS EUR**: `00022300` -> `content`;
  + **Old 3DS JPN**: `00020300` -> `content`;
  + **Old 3DS USA**: `00021300` -> `content`;
  + **New 3DS EUR**: `20022300` -> `content`;
  + **New 3DS JPN**: `20020300` -> `content`;
  + **New 3DS USA**: `20021300` -> `content`;
8. Видите, здесь два типа *.app и *.tmd файлов? Первые написаны в капсе (`.TMD` и `.APP`), а вторые - нет (`.tmd` и `.app`).
11. Удерживая (R), нажмите (Y), чтобы создать новую папку.
10. Нажмите (А), чтобы подтвердить название новой папки - `newdir` (нам без разницы как она будет называться). 
6. Нажмите (А), чтобы разблокировать SysNAND для записи и введите указанную комбинацию кнопок.
9. На каждом файле, разрешение которого написано в капсе (`.TMD` и `.APP`), нажмите (L), чтобы отметить его.
10. Нажмите (Y), чтобы скопировать эти файлы.
11. Перейдите в `newdir`.
12. Нажмите (Y), чтобы переместить выбранные ранее файлы.
13. Выберите "Move path(s)".
14. Теперь файлы с капсом переместились в папку `newdir`.
15. Нажмите (START) для перезагрузки. 
16. Вернитесь к [установке A9LH](installing-arm9loaderhax) и попробуйте инжект FBI еще раз. 
17. Если снова не получилось, то верните капснутые файлы назад в папку `content` и повторите операцию перемещения файлов в папку `newdir`, уже с файлами без капса (`.tmd` и `.app`), а затем вернитесь к [установке A9LH](installing-arm9loaderhax) и попробуйте инжект FBI еще раз. 

## <a name="ts_browser" />Почему не работает эксплойт, использующий браузер?
Эксплойты, базирующиеся на браузере (browserhax или 2xrsa, например) очень нестабильные и частенько крашатся, но иногда всего этого можно избежать, следуя рекомендациям, описанным ниже:

1. Откройте браузер, затем настройки браузера (settings):
    1. Пролистайте в самый низ и выберите "Удалить сохр. данные" (Initialize Savedata/Clear All Save Data).
    2. Попробуй запустить эксплойт еще раз.

## <a name="ts_safe_a9lh" />Приставка грузится в SafeA9LHInstaller
Вы просто скопировали не верный `arm9loaderhax.bin` на карту памяти.

1. Используйте верный `arm9loaderhax.bin`:
    1. Скопируйте `arm9loaderhax.bin` из архива Luma3DS в корень своей карты памяти;
    2. Выключите приставку, зажмите (SELECT) и включите.

## <a name="ts_safe_a9lh_screen" />SafeA9LHInstaller показывает корявый экран
Такое часто бывает непонятно почему. Кнопки все равно работают, поэтому нажимайте (SELECT) до тех пор, пока консоль не выключится (если приставка не выключается, секунд через 10 просто отключите долгим нажатием кнопки включения).

## <a name="ts_dsiware" />После DSiWare-даунгрейда, взломанная игра не работает.

3. Выключите **исходную 3DS**, зажмите (START) и включите. Загрузится Hourglass9.
4. Перейдите в SysNAND Backup/Restore и восстановите SysNAND из `NANDmin.bin` (который создавался до переноса системы).
1. Если игры нет совсем, следует соединить NNID, с которого была куплена игра, с **целевой 3DS** и перекачать игру на нее.
  + Может понадобится удалить игру через "Управление данными" (Data Management) в системных настройках (System Settings);
  + Если на **целевой 3DS** не самая последняя версия ПО (без нее в eShop не зайти), используйте ctr-httpwn. 
2. На **исходной 3DS** выполните шаги с инжектом сейва, или `.app`, в зависимости от метода, который вы используете.
3. На **исходной 3DS** перейдите в Системные настройки, Управление данными, DSiWare (System Settings, "Data Management", "DSiWare"), а затем скопируйте свою DSiWare игру на карту памяти.
4. Поставьте КП от **исходной 3DS** в **целевую 3DS**, или просто переименуйте папку `Nintendo 3DS`на КП в **целевой 3DS** и скопируйте на нее папку `Nintendo 3DS` из КП от **исходной 3DS**. 
5. На **целевой 3DS** перейдите в Системные настройки, Управление данными, DSiWare (System Settings, "Data Management", "DSiWare") и скопируйте свою DSi игру обратно в систему. 
6. Верните карты на свои места (если переименовывали папку, переименуйте обратно) и продолжайте DSiWare-даунгрейд. 

## <a name="ts_d9_backup" />Decrypt9 или Hourglass9 не восстанавливают / не видят мой NAND-бекап.

1. Убедитесь, что в **корне** КП нет папки "Decrypt9".
3. Попробуйте сделать проверку файловой системы карточки с помощью [H2testw (Windows)](h2testw-(windows)), [F3 (Linux)](f3-(linux)), или [F3X (Mac)](f3x-(mac)).
4. Сделайте бекап карты памяти и переформатируйте ее, затем верните все файлы на место.
5. Попробуйте другую карту памяти.

## <a name="ts_sys_down" />Черный экран при загрузке SysNAND 

1. Попробуйте загрузиться без карты памяти, а затем верните ее в консоль
    1. Отключите приставку, зажав кнопку выключения.
    2. Достаньте КП.
    3. Включите 3DS. 
    4. Когда появится Домашний экран, вставьте назад КП. 
    5. Если сработало, то следует отчистить данные Домашнего экрана. Для этого удалите в папке `/Nintendo 3DS/(32-значный ID)/(32-значный ID)/extdata/00000000/`, папку, соответствующую вашей системе и региону: 
        + EUR регион: Удалите `00000098`;
        + JPN регион: Удалите `00000082`;
        + USA регион: Удалите `0000008f`;
        + KOR регион: Удалите `000000A9`;
1. Попробуйте загрузиться без картриджа (совсем).
2. Если есть хардмод - восстановите бекап наверняка рабочего NAND в SysNAND.
3. Загрузитесь в режим восстановления и обновите систему.
    *Почти наверняка не сработает на 3DS с прошивкой 2.1.0*    
    **НЕЛЬЗЯ делать на New 3DS с прошивкой 2.1.0 - гарантированный брик**
    1. Отключите приставку, зажав кнопку выключения
    2. Удерживайте  (L)+(R)+(A)+(ВВЕРХ)
    3. Включите 3DS
    4. Зайдя в режим восстановления, обновите свою 3DS.
4. Может быть брик. Для поддержки обращайтесь на [#3dshacks on Rizon IRC](https://www.reddit.com/r/3dshacks/wiki/irc) или в [3DS Hacking on Discord](https://discord.gg/MWxPgEp) (*для русскоязычных - группа [3DS_cfw](http://vk.com/3ds_cfw) - прим. пер.*).

## <a name="ts_sys_a9lh" />Черный экран при загрузке SysNAND после установки a9lh

1. Убедитесь, что у вас установлен рабочий загрузчик
    1. Проверьте, есть ли в корне КП файл `arm9loaderhax.bin`. Если нет, скопируйте его из архива с Luma3DS.
2. Попробуйте сбросить настройки Luma 
    1. Удалите файл `/luma/config.bin` с карты памяти приставки;
    2. Заново настройте Luma после запуска. 
3. Проверьте, грузится ли Hourglass9
    1. Выключите приставку, зажмите (START) и включите.
4. Попробуйте отчистить данные Домашнего экрана
    1. Удалите в папке `/Nintendo 3DS/(32-значный ID)/(32-значный ID)/extdata/00000000/`, папку, соответствующую вашей системе и региону: 
        + EUR регион: Удалите `00000098`
        + JPN регион: Удалите `00000082`
        + USA регион: Удалите `0000008f`
        + KOR регион: Удалите `000000A9`
1. Попробуйте загрузиться без картриджа (совсем).
8. Если вы даунгрейдились через Gateway, то убедитесь, что у вас установлена самая последняя версия Luma3DS (не ниже, чем 6.2.3).
9. Если версия вашего NAND между 3.0.0 и 4.5.0, проделайте следующие действия:
    + Убедитесь, что используете самую свежую версию [Luma 3DS](https://github.com/AuroraWright/Luma3DS/releases)
    + Скачайте [этот файл](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/00000056) и переименуйте в `firmware.bin`.
    + Скачайте [этот файл](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/cetk).
    + Скопируйте `firmware.bin` и `cetk` в папку `/luma/` на карте памяти. 
    + После обновления системы удалите эти файлы. 
9. Попробуйте выполнить [9.2.0 ctrtransfer](9.2.0-ctrtransfer).
10. Попросите помощи на [#3dshacks on Rizon IRC](https://www.reddit.com/r/3dshacks/wiki/irc) или в [3DS Hacking on Discord](https://discord.gg/MWxPgEp) (*для русскоязычных - группа [3DS_cfw](http://vk.com/3ds_cfw) - прим. пер.*).

## <a name="ts_sys_blue" />Голубой экран при загрузке (bootrom error).

1. У вас брик.
2. Восстановиться может помочь [хардмод](https://gbatemp.net/threads/414498/) или ремонт / замена устройства.
