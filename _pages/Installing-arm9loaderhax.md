---
title: "Установка arm9loaderhax"
permalink: /installing-arm9loaderhax.html
sidebar:
  nav: "installing-arm9loaderhax"
---

На последнем этапе гайда устанавливаем arm9loaderhax и настраиваем Luma3DS, после чего загрузка будет занимать значительно меньше времени. За эту возможность благодарим [AuroraWright](https://github.com/AuroraWright/) и его программу SafeA9LHInstaller.
{: .notice}

Для установки arm9loaderhax будем использовать [форк AuroraWright](https://github.com/AuroraWright/arm9loaderhax).
{: .notice--info}

Так же настроим запуск пейлоадеров из под arm9loaderhax, благодаря чему будем иметь возможность сделать анбрик консоли и восстановить SysNAND из бекапа практически в любой момент. 
{: .notice--info}

**НЕЛЬЗЯ использовать чужой OTP. Брик гарантирован!**
{: .notice--danger}

#### <a name="steps" />Что будем делать?

В этом разделе мы будем шаг за шагом продвигаться к цели - установке arm9loaderhax.

Можно уверенно заявить, что arm9loaderhax - наилучший из возможных типов эксплойтов. Все потому, что он устанавливается непосредственно в раздел NAND firm и запускается ДО запуска операционной системы приставки. Кроме прочего, a9lh работает с <0>любой</0> прошивкой и, благодаря тому, что запускается до ОС, в большинстве ситуаций, удалить его случайно не выйдет. А еще этот эксплойт позволяет запускать различного рода загрузчики, которые помогут восстановить консоль даже из тех состояний, которые в обычном случае привели бы вас в сервисный центр. 

Файл под названием `arm9loaderhax.bin` - исполняемый файл, написанный под arm9, который запускает arm9loaderhax до загрузки системы. К слову, luma3DS делает запуск загрузчиков гораздо удобнее. Ничего не нужно заменять или переименовывать. достаточно зажать кнопку при старте системы, присвоенную необходимому загрузчику. 

`arm9loaderhax.bin`, используемый в этом гайде - исполняемый файл самой Luma3DS от [AuroraWright](https://github.com/AuroraWright/), после того как он загружается в память приставки, он на лету патчит SysNAND. Таким образом мы загружаем систему сразу в кастомную прошивку без необходимости EmuNAND. 

После того, как мы установим arm9loaderhax и настроем Luma3DS, мы восстановим бекап прошивки, сделанный ранее. У нас будет консоль с arm9loaderhax и прошивкой, софтом и сейвами, с которыми приставка была ДО взлома. 

В процессе мы установим и настроем следующие программы: 

  +  **FBI** *(устанавливает игры и программы в формате CIA)*
  +  **Luma3DS Updater** *(программа для упрощения обновления нашей кастомной прошивки)*
  +  **Hourglass9** *(многоцелевая утилита, выполняющие различные функции, связанные с NAND и картриджами)*
  +  **freeshop** *(open source клон eShop, облегчающий поиск игр)*

#### <a name="what_need" />Что нужно: 

* [`aeskeydb.bin`](magnet:?xt=urn:btih:18b3a17f78e2376e05feaa150749d9fd689b25dc&dn=aeskeydb.bin&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* [`fbi-2.4.2-injectable.zip`](magnet:?xt=urn:btih:f978b4cf5eda72823240b9c649f3fd2940a9f525&dn=fbi-2.4.2-injectable.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* [`data_input_v3.zip`](magnet:?xt=urn:btih:a1195c9f7ab650fa7c7bf020b51fc19ea8d9440c&dn=data%5Finput%5Fv3.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* Свежий форк [SafeA9LHInstaller](https://github.com/Plailect/SafeA9LHInstaller/releases/latest) *(`.7z`-файл)*
* Свежая версия [arm9loaderhax](https://github.com/AuroraWright/arm9loaderhax/releases/latest) *(t`.7z`-файл)*
* Свежая версия с зеркала [Luma3DS](https://astronautlevel2.github.io/Luma3DS/builds/Luma-1eb18c17.zip) *(`.7z`-файл)*
* Свежая версия [hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases/latest)
* Свежая версия [Hourglass9](https://github.com/d0k3/Hourglass9/releases/latest)
* Свежая версия [Luma3DS Updater](https://github.com/Hamcha/lumaupdate/releases/latest)
* Свежая версия [DspDump](https://github.com/Cruel/DspDump/releases/latest)
* Свежая версия [FBI](https://github.com/Steveice10/FBI/releases/latest)
* Свежая версия [freeshop](http://get.freeshop.pw/latest)
* Свежая версия [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* The Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
* Если вы пользовались блокировкой conntest.nintendowifi.net [(Homebrew Launcher (используя браузер), часть IV)](Homebrew-launcher-(browser)) через файерволл, роутер, смартфон, прочее, то отключите добавленное вами правило, иначе вы не сможете ни обновить прошивку по окончании выполнения инструкции, ни скачать новый ropbin payload при необходимости, а следовательно, зайти в HBL. 


#### <a name="instructions" />Что делать:

##### <a name="part1" />Часть I - Подготовка

{% capture notice-5 %}
**Убедитесь в том, что ваша карта памяти исправна и правильно отформатирована!**

**Использование испорченной карты может привести к БРИКУ!**

**Если вы не уверены, что карта работает правильно, проверьте КП на ошибки, используя [H2testw (Windows)](h2testw-(windows)), [F3 (Linux)](f3-(linux)), or [F3X (Mac)](f3x-(mac))!**
{% endcapture %}

<div class="notice--danger">{{ notice-5 | markdownify }}</div>

1. **Если на карте памяти есть папка `/files9/`, скопируйте ее в надежное место (лучше сделать не одну копию и на разных носителях, а так же в облаке); файлы, находящиеся в этой папке файлы могут вернуть приставку к жизни, в случае проблем.**
2. Создайте папку `cias` в корне карты памяти.
4. **Удалите папку `a9lh` из корня КП, если таковая там есть.**
  + **Если вы по ошибке установите arm9loaderhax, используя `OTP.bin` от другой консоли, то будет БРИК!**
3. Удалите папку `3ds` из корня КП, если таковая там есть.
4. **Скопируйте _содержимое_ папки `starter`, расположенной в архиве `starter.zip`, в корень карты памяти.**
  + Все это нужно сделать, чтобы актуализировать программы, содержащиеся в папке 3ds.
5. Скопируйте _содержимое_ архива SafeA9LHInstaller в корень карты памяти.
6. **Скопируйте папку `a9lh` из архива `data_input` в корень карты памяти.**
7. **Скопируйте _содержимое_ архива arm9loaderhax (release.7z) в папку `a9lh` в корне КП.**
9. Скопируйте `hblauncher_loader.cia` из архива hblauncher_loader в папку `/cias/` в корне КП.
10. Скопируйте `lumaupdater.cia` из архива Luma3DS Updater в папку `/cias/` в корне КП.
11. Скопируйте `FBI.cia` из архива FBI в папку `/cias/` в корне КП.
11. Скопируйте `freeShop-x.x.x.cia` в папку `/cias/` в корне КП.
12. **Скопируйте `arm9loaderhax.bin` из папки `out` из архива Luma3DS, в корень карты памяти, согласившись на перезапись.**
13. Создайте папку `luma` в корне карты памяти.
14. Создайте папку `payloads` в папке `luma` в корне карты памяти.
15. Скопируйте `Hourglass9.bin` из архива Hourglass9 в папку `/luma/payloads/` в корне КП и переименуйте `Hourglass9.bin` в `start_Hourglass9.bin`.
16. Скопируйте `GodMode9.bin` из архива GodMode9 папку `/luma/payloads` в корне КП и переименуйте `GodMode9.bin` в `up_GodMode9.bin`.
16. Скопируйте `aeskeydb.bin` в папку `/files9/` в корне КП.
17. Скопируйте `DspDump.3dsx` в папку `/3ds/` в корне КП.
18. Скопируйте _содержимое_ архива `fbi-2.4.2-injectable.zip` в папку `/files9/` в корне КП.

##### <a name="part2" />Часть II - Установка arm9loaderhax

1. Верните карту памяти в 3DS
2. Для того, чтобы установить a9lh, следуйте нижеизложенной инструкции:
    + Необходимо находиться на прошивке 2.1.0.
    + Перейдите по ссылке на своей приставке `https://goo.gl/xUMUJB` (или `http://dukesrg.github.io/2xrsa.html?arm11.bin`).
      + Если выскакивает ошибка "This service is not available in your region", поменяйте регион в Системных настройках (System Settings) на соответствующий тому, который был установлен при 2.1.0 ctrtransfer.
      + При возникновении другой ошибки, обратитесь к разделу [Проблемы и их решения](troubleshooting#ts_browser).
      + Если экран выглядит некорректно и видны графические артефакты, обратитесь к разделу [Проблемы и их решения](troubleshooting#ts_safe_a9lh_screen).
	  + Если у вас отключен wifi, отключите 3DS от зарядного и достаньте батарею на несколько секунд. 
    + Нажмите (SELECT) для установки.
    + Сейчас установщик поставит arm9loaderhax на вашу консоль (буквально секунда).
    + Нажмите любую кнопку, чтобы выключить приставку. При необходимости, выключите консоль долгим нажатием на кнопку включения. 
    + Достаньте карту памяти из приставки и вставьте ее в ПК.
    + Скопируйте файл `OTP.bin` из папки `/a9lh/` на карте памяти в надежное место (лучше сделать не одну копию и на разных носителях, а так же в облаке) и верните карту обратно в консоль. Помните, что `OTP.bin` уникален для каждой приставки. 

##### <a name="part3" />Часть III - Настройка Luma3DS

1. Зажмите (SELECT) и включите приставку, чтобы попасть в меню настройки Luma3DS.
  + Важно зажать кнопку до того, как включать приставку.
  + Если после запуска экран черный, то следуйте рекомендациям из [раздела с помощью](troubleshooting#ts_sys_a9lh).   
  + Если после загрузки запускается SafeA9LHInstaller, то следуйте рекомендациям из [раздела с помощью](troubleshooting#ts_sys_a9lh).   
2. С помощью кнопки (А) отметьте следующие пункты:     
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R"**
  + **"Show NAND or user string in System Settings"**
3. Если у вас **New 3DS**, так же отметьте следующие пункты: 
  + **"New 3DS CPU" to "Clock+L2(x)"**
    + Это увеличит частоту кадров в некоторых играх.
    + Если какие-то игры работают некорректно, отключите эту опцию.
4. Нажмите (START), чтобы сохранить настройки и перезагрузиться. 
  + Если после запуска экран черный, продолжайте выполнение инструкций. 
  + Если выскакивает ошибка "Failed to mount CTRNAND", просто продолжайте дальше.

##### <a name="part4" />Часть IV - Восстановление системы

Если вы начинали гайд со взломанной приставкой с EmuNAND, то самое время заняться [переносом EmuNAND в SysNAND](move-emunand).
{: .notice--info}

Если вы делали бекап NAND в части [DSiWare Downgrade (Save Injection)](dsiware-downgrade-(save-injection)) or [Hardmod Downgrade](hardmod-downgrade), восстановите этот бекап вместо `NANDmin.bin`. Переместите тот бекап в папку `/files9/` и следуйте инструкции. Бекап будет называться `NAND_N3DS.bin`, `NAND_O3DS.bin`, или `backup_nand.bin`, в зависимости от шага на котором он был сделан.
{: .notice--info}

Если бекапа нет, то следуйте рекомендациям из [раздела с 9.2.0 ctrtransfer](9.2.0-ctrtransfer).
{: .notice--info}

1. Запустите Hourglass9 из под arm9loaderhax, удерживая кнопку (START) при запуске приставки. 
2. Перейдите в "SysNAND Backup/Restore".
3. Перейдите в "SysNAND Restore (keep a9lh)" и восстановите NAND из `NANDmin.bin`.
4. Нажмите (START) для перезагрузки
    + Если после запуска экран черный, выполняйте инструкции из раздела [9.2.0 ctrtransfer](9.2.0-ctrtransfer).
5. Если ваш бекап был сделан на прошивках от 3.0.0 до 4.5.0, консоль не запустится до тех пор, пока вы вручную не выкачаете нужные файлы прошивки:
  + Скачайте [этот файл](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/00000056) и переименуйте его в `firmware.bin`.
  + Скачайте [этот файл](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/cetk).
  + Скопируйте `firmware.bin` и `cetk` в папку `/luma/` на карте памяти.
  + После обновления прошивки на 3DS удалите оба этих файла.

##### <a name="part5" />Часть V - Внедрение FBI

2. Обновите прошивку 3DS, вне зависимости от того делали ли вы это давно, или всего шаг назад. Для этого зайдите в Системные настройки, "Прочие настройки" (Other Settings), листайте вправо до тех пор, пока не дойдете до предпоследнего пункта - Обновление ("System Update").
  + Если у вас Luma + A9HL, то обновляться безопасно. 
  + Предупреждение о том, что нельзя обновлять прошивку на New 3DS будучи на прошивке с версией 2.1.0, не действует после восстановления бекапа. 
  + Если выскочит ошибка, поставьте в настройках подключения, в настройках DNS "Получить DNS автоматически" в положение "Да".
  + Если выскакивает ошибка и версия вашей прошивки ниже 9.2.0, [проделайте 9.2.0 ctrtransfer](9.2.0-ctrtransfer).
  + Если вы пользовались блокировкой conntest.nintendowifi.net [(Homebrew Launcher (используя браузер), часть IV)](Homebrew-launcher-(browser)) через файерволл, роутер, смартфон, прочее, то отключите добавленное вами правило, иначе вы не сможете ни обновить прошивку по окончании выполнения инструкции, ни скачать новый ropbin payload при необходимости, а следовательно, зайти в HBL. 
2. Запустите Hourglass9 из под arm9loaderhax, включив приставку с зажатой кнопкой (START). 
2. Перейдите в "SysNAND Backup/Restore", выберите "Health&Safety Dump", чтобы сдампить на карту памяти оригинальный Health & Safety в файл `hs.app` **(стрелками (ВВЕРХ) / (ВНИЗ) и (ВЛЕВО) / (ВПРАВО) можно менять имя дампа)**.
3. Нажмите (B), затем выберите "Health&Safety Inject".
4. Введите комбинацию кнопок, указанных на экране. 
8. Выберите файл с внедренным FBI формата `.app` кнопками (ВВЕРХ) / (ВНИЗ), соответствующий вашему региону. 
4. Нажмите (A) для подтверждения. 
9. Нажмите (Start) для перезагрузки.
10. Если при запуске Health & Safety запускается не FBI и вы в прошлом даунгрейдились с помощью Gateway, милости просим в раздел [проблемы и их решения](troubleshooting#gw_fbi).

##### <a name="part6" />Часть VI - Заканчиваем настройку

2. Запустите Информация о здоровье и безопасности (Health & Safety) (это теперь FBI).
3. Выберите "SD".
4. Выберите "cias".
5. Наведите курсор на `<current directory>`, нажмите (А) и выберите Install all CIAs.
6. Установятся все приложения, находящиеся в этой папке. 
9. Нажмите (B), чтобы вернуться в папку "SD".
4. Перейдите к файлу `arm9loaderhax.bin`, нажмите (A) и выберите “Copy”.
9. Нажмите (B), чтобы вернуться в главное меню FBI.
10. Выберите "CTR NAND".
11. Выберите `<current directory>`.
12. Нажмите "Paste", затем нажмите (A) для подтверждения.
8. Нажмите кнопку (home) для перехода на домашний экран. 
9. Запустите Homebrew Launcher с домашнего экрана.
10. Выберите "DSP Dump".
11. Нажмите (START), после завершения, для выхода.
12. Перезагрузите приставку, удерживая (START) для входа в Hourglass9.
13. Перейдите в "SysNAND Backup/Restore", выберите "Health&Safety Inject".
14. Выберите `hs.app` (оригинальный файл, не содержащий FBI), нажмите (A) для подтверждения внедрения. 
15. Нажмите (SELECT) в главном меню Hourglass9, чтобы извлечь КП.
15. Нажмите (START) для перезагрузки с извлеченной картой памяти
  + Необходимо хотя бы раз загрузиться без карты памяти, чтобы настроить прошивку, расположенную в CTRNAND.
16. Нажимая (A) выберите следующие пункты: 
  + **"Show NAND or user string in System Settings"**
3. Если у вас **New 3DS**, так же отметьте следующие пункты: 
  + **"New 3DS CPU" to "Clock+L2(x)"**
    + Это увеличит частоту кадров в некоторых играх.
    + Если какие-то игры работают некорректно, отключите эту опцию.
14. Вставьте карту памяти в приставку и нажмите (START) для того, чтобы сохранить настройки и перезагрузить приставку. 
___

В случае проблем с запуском приложений DSi / DS (например, картриджи DS или DSiWare перестали работать), [обратитесь к разделу с проблемами и их решениями](troubleshooting#twl_broken).
{: .notice--warning}

{% capture notice-10 %}
Теперь вы можете использовать Luma3DS Updater для обновления кастомной прошивки. Запустите его и нажмите (А).
Это не обновление системы; это приложение скачивает обновленные файлы luma3DS, находящиеся на карте памяти.
Это значит, что версия luma3ds ctrnand не обновляется этим приложением. 
При запуске приставки без карты памяти, загрузится та версия Luma, что находится в CTRNAND.
{% endcapture %}

<div class="notice--info">{{ notice-10 | markdownify }}</div>

{% capture notice-6 %}   
Вы загружаетесь сразу в кастомную прошивку, находящуюся в SysNAND. 
Для запуска конфигуратора luma3DS, нужно зажать (SELECT) и, не отпуская кнопку, включить приставку.
Для запуска Hourglass9 - крутой программы для работы с NAND и картриджами - нужно зажать (START) и, не отпуская кнопку, включить приставку.
{% endcapture %}

<div class="notice--info">{{ notice-6 | markdownify }}</div>

Для обновления A9LH, следуйте инструкциям из раздела [обновление A9LH](updating-a9lh).
{: .notice--info}

Для использования [NTR CFW](https://github.com/44670/BootNTR/), положите `ntr.bin`, находящийся в архиве на [этой странице](https://github.com/44670/BootNTR/releases), в корень карты памяти. Затем установите [`BootNTR.cia`](https://github.com/astronautlevel2/BootNTR/releases/latest).
{: .notice--info}

После всех настроек и манипуляций рекомендую сделать бекап через Hourglass9 (SysNAND Backup/Restore, SysNAND Backup). Получившийся файл `NANDmin.bin` сохраните в надежном месте. В случае чего, он может спасти вам консоль. 
{: .notice--info}

Можно удалить бекап из папки `/files9/`, коль уж вы сохранили его в надежном месте. 
{: .notice--info}

{% capture notice-7 %}
**Можно удалить ненужные файлы и папки из карты памяти. Важно *оставить* файлы, указанные ниже:** 

    + 3ds
    + files9
    + hblauncherloader
    + luma
    + Nintendo 3DS
    + arm9loaderhax.bin
    + boot.3dsx
	
{% endcapture %}

<div class="notice--info">{{ notice-7 | markdownify }}</div>

Если вы хотите сменить регион вашего устройства, вам сюда - [Смена региона](region-changing).
{: .notice--success}

Для того, чтобы держать свой a9lh в актуальном состоянии, следуйте этой инструкции - [Обновление A9LH](updating-a9lh).
{: .notice--success}

<a name="part7" />
+ Рекомендую ознакомиться с различными фишками, которые умеет Luma3DS [в этой статье](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage).   
+ [Как делать резервные копии, редактировать и восстанавливать](https://gbatemp.net/threads/release-jks-savemanager-Homebrew-cia-save-manager.413143/) сохранения игр.    
+ Как настроить внешний вид домашнего экрана кастомными [темами](themes) и [жетонами](badges) с помощью программ [СHMM2](http://rinnegatamante.it/site/3ds_hbs.php) и [GYTB](https://github.com/MrCheeze/GYTB).    
+ [Как ставить игры?](http://vk.com/3ds_cfw?w=wall-125012133_147%2Fall)   
+ [Как настроить freeshop](https://vk.com/3ds_cfw?w=wall-125012133_847%2Fall)   
{: .notice--success}