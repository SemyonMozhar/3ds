---
title: "Установка arm9loaderhax"
permalink: /installing-arm9loaderhax.html
sidebar:
  nav: "installing-arm9loaderhax"
---

Последний шаг данного гайда - установка arm9loaderhax и настройка Luma3DS на мгновенную загрузку сразу после включения консоли. Для этого мы воспользуемся SafeA9LHInstaller от [AuroraWright](https://github.com/AuroraWright/).
{: .notice}

Мы будем устанавливать [arm9loaderhax от AuroraWright](https://github.com/AuroraWright/arm9loaderhax).
{: .notice--info}

Также мы настроим возможность запускать другие приложения (payloads) через arm9loaderhax, что даст нам возможность восстановить SysNAND из бэкапа в ситуациях, которые обычно привели бы к брику.
{: .notice--info}

**Никогда не используйте OTP от другой консоли, это ГАРАНТИРОВАННО приведёт к брику**
{: .notice--danger}

#### <a name="steps" />Описание шагов

В этом разделе мы, наконец, сделаем то, к чему вели все предыдущие шаги: установим arm9loaderhax.

Можно уверенно заявить, что arm9loaderhax - наилучший из возможных типов эксплойтов. Все потому, что он устанавливается непосредственно в раздел NAND firm и запускается ДО запуска операционной системы приставки. Кроме прочего, a9lh работает с **любой** прошивкой и, благодаря тому, что запускается до ОС, в большинстве ситуаций, удалить его случайно не выйдет. А еще этот эксплойт позволяет запускать различного рода загрузчики, которые помогут восстановить консоль даже из тех состояний, которые в обычном случае привели бы вас в сервисный центр. 

Файл под названием `arm9loaderhax.bin` - исполняемый файл, написанный под arm9, который запускает arm9loaderhax до загрузки системы. К слову, luma3DS делает запуск загрузчиков гораздо удобнее. Ничего не нужно заменять или переименовывать. достаточно зажать кнопку при старте системы, присвоенную необходимому загрузчику. 

`arm9loaderhax.bin`, используемый в этом гайде - исполняемый файл самой Luma3DS от [AuroraWright](https://github.com/AuroraWright/), после того как он загружается в память приставки, он на лету патчит SysNAND. Таким образом мы загружаем систему сразу в кастомную прошивку без необходимости EmuNAND. 

После того, как мы установим arm9loaderhax и настроем Luma3DS, мы восстановим бекап прошивки, сделанный ранее. У нас будет консоль с arm9loaderhax и прошивкой, софтом и сейвами, с которыми приставка была ДО взлома. 

В процессе мы установим и настроем следующие программы: 

  +  **FBI** *(устанавливает игры и программы в формате CIA)*
  +  **Luma3DS Updater** *(программа для упрощения обновления нашей кастомной прошивки)*
  +  **Hourglass9** *(многоцелевая утилита, выполняющие различные функции, связанные с NAND и картриджами)*
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
* Свежая версия [freeshop](http://get.freeshop.pw/latest)
* The Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)

#### <a name="instructions" />Инструкция

##### <a name="part1" />Часть I - Подготовительные работы

{% capture notice-5 %}
**Убедитесь в том, что ваша карта памяти исправна!**

**Использование неисправной карты может привести к БРИКУ!**

**Если вы не уверены, что SD-карта исправна, рекомендуется проверить eё на ошибки с помощью [H2testw (Windows)](h2testw-(windows)), [F3 (Linux)](f3-(linux)), или [F3X (Mac)](f3x-(mac))!**
{% endcapture %}

<div class="notice--danger">{{ notice-5 | markdownify }}</div>

1. **Если на карте памяти есть папка `/files9/`, скопируйте ее в надежное место (лучше сделать не одну копию и на разных носителях, а так же в облаке); файлы, находящиеся в этой папке файлы могут вернуть приставку к жизни, в случае проблем.**
2. Создайте папку `cias` в корне SD-карты
4. Скопируйте _содержимое_ `.7z-архива` SafeA9LHInstaller в корень SD-карты
3. **Скопируйте папку `a9lh` из `.zip-архива` `data_input` в корень SD-карты**
4. Скопируйте _содержимое_ `.7z-архива` arm9loaderhax в папку `a9lh` в корне SD-карты
5. Скопируйте _содержимое_ архива SafeA9LHInstaller в корень карты памяти.
6. Скопируйте `hblauncher_loader.cia` из архива hblauncher_loader в папку `/cias/` в корне SD-карты
9. Скопируйте `hblauncher_loader.cia` из архива hblauncher_loader в папку `/cias/` в корне КП.
10. Скопируйте `lumaupdater.cia` из архива Luma3DS Updater в папку `/cias/` в корне КП.
11. Скопируйте `FBI.cia` из архива FBI в папку `/cias/` в корне КП.
11. Скопируйте `freeShop-latest.cia` в папку `/cias/` в корне КП.
12. Скопируйте `arm9loaderhax.bin` из архива Luma3DS, в корень карты памяти, согласившись на перезапись.
13. Создайте папку `luma` в корне карты памяти.
14. Создайте папку `payloads` в папке `luma` в корне карты памяти.
15. Скопируйте `Hourglass9.bin` из `.zip-архива` Hourglass9 в папку `/luma/payloads/` в корне SD-карты и переименуйте `Hourglass9.bin` в `start_Hourglass9.bin`
17. Скопируйте `aeskeydb.bin` в папку `/files9/` в корне SD-карты
18. Скопируйте `DspDump.3dsx` в папку `/3ds/` в корне SD-карты
19. Скопируйте _содержимое_ архива `fbi-2.4.2-injectable.zip` в папку `/files9/` в корне SD-карты

##### <a name="part2" />Часть II - Установка arm9loaderhax

1. Вставьте SD-карту обратно в 3DS
2. Установите arm9loaderhax на консоль, следуя инструкции:
  + Необходимо находиться на прошивке 2.1.0.
  + Откройте `http://goo.gl/xUMUJB` в браузере 3DS
    + Если появляется ошибка "This service is not available in your region", поменяйте регион в Системных настройках (System Settings) на соответствующий тому, который был установлен при 2.1.0 ctrtransfer
    + При возникновении другой ошибки, обратитесь к разделу [Проблемы и их решения](troubleshooting#ts_browser)
    + Если экран выглядит некорректно и видны графические артефакты, обратитесь к разделу [Проблемы и их решения](troubleshooting#ts_safe_a9lh_screen).
    + Если вы забыли включить Wi-Fi на 2DS или New 3DS, это можно сделать, вытащив батарею и отключив зарядное устройство на несколько секунд, а затем снова включить консоль
  + Нажмите (SELECT) для установки.
  + Установщик поставит arm9loaderhax на вашу консоль (буквально за секунду)
  + Нажмите любую кнопку для выключения консоли
  + Достаньте карту памяти из приставки и вставьте ее в ПК.
  + Скопируйте файл `otp.bin` из папки `/a9lh/` на SD-карте в надежное место (лучше сделать не одну копию и на разных носителях, а так же в облаке). Помните, что `otp.bin` уникален для каждой приставки
  + Верните SD-карту обратно в консоль
  
##### <a name="part3" />Часть III - Настройка Luma3DS

1. Зажмите (SELECT) и включите приставку, чтобы попасть в меню настройки Luma3DS.
  + Важно зажать кнопку до того, как включать приставку.
  + Если после включения экран остаётся чёрным, то перейдите к разделу [проблемы и их решения](troubleshooting#ts_sys_a9lh)
  + Если после загрузки запускается SafeA9LHInstaller, то следуйте рекомендациям из [раздела с помощью](troubleshooting#ts_sys_a9lh).   
2. С помощью кнопки (А) отметьте следующие пункты:     
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R"**
  + **"Show NAND or user string in System Settings"**
3. Если у вас **New 3DS**, так же отметьте следующие пункты: 
  + **"New 3DS CPU" to "Clock+L2(x)"**
    + Это увеличит частоту кадров в множестве игр, но может отразиться на стабильности других
    + Если какие-либо игры работают некорректно, отключите эту опцию
4. Нажмите (START), чтобы сохранить настройки и перезагрузиться. 
  + Если после включения экран остаётся чёрным, просто переходите к следующей части   
  + Если появляется ошибка "Failed to mount CTRNAND", просто переходите к следующей части     
  
##### <a name="part4" />Часть IV - Восстановление системы

Если прежде чем начать выполнять действия из этого руководства у вас уже был установлен EmuNAND и вы хотите перенести содержимое EmuNAND в SysNAND с кастомной прошивкой - сейчас самый подходящий момент. Выполните действия из раздела [перенос EmuNAND](move-emunand), вместо первых 4 шагов в этой части.{: .notice--info}

Если бекапа нет, то следуйте рекомендациям из [раздела с 9.2.0 ctrtransfer](9.2.0-ctrtransfer).
{: .notice--info}

1. Запустите Hourglass9 из под arm9loaderhax, удерживая кнопку (START) при запуске приставки. 
2. Перейдите в "SysNAND Backup/Restore"
3. Перейдите в "SysNAND Restore (keep a9lh)" и восстановите NAND из `NANDmin.bin`
4. Нажмите (START) для перезагрузки
  + Если после запуска экран чёрный, выполняйте инструкции из раздела [9.2.0 ctrtransfer](9.2.0-ctrtransfer)
5. Если ваш бекап был сделан на прошивках от 3.0.0 до 4.5.0, консоль не запустится до тех пор, пока вы вручную не скачаете нужные файлы прошивки:
  + Скачайте [этот файл](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/00000056) и переименуйте его в `firmware.bin`
  + Скачайте [этот файл](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/cetk)
  + Скопируйте `firmware.bin` и `cetk` в папку `/luma/` на SD-карте
  + После обновления прошивки на 3DS удалите оба этих файла
  
##### <a name="part5" />Часть V - Интеграция FBI

2. Обновите прошивку 3DS, вне зависимости от того делали ли вы это давно, или всего шаг назад. Для этого зайдите в Системные настройки, "Прочие настройки" (Other Settings), листайте вправо до тех пор, пока не дойдете до предпоследнего пункта - Обновление ("System Update").
  + Если у вас Luma + A9HL (а она стоит, если вы внимательно следовали гайду), то обновляться безопасно. 
  + При появлении ошибки, поставьте в настройках подключения, в настройках DNS "Получать DNS автоматически" в положение "Да"  + Если выскакивает ошибка и версия вашей прошивки ниже 9.2.0, [проделайте 9.2.0 ctrtransfer](9.2.0-ctrtransfer).
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

1. Запустите "Информация о здоровье и безопасности" (Health and Safety) (теперь это FBI)
2. Выберите "SD"
4. Выберите "cias".
5. Наведите курсор на `<current directory>`, нажмите (А) и выберите Install all CIAs.
6. Установятся все приложения, находящиеся в этой папке. 
9. Нажмите (B), чтобы вернуться в папку "SD".
8. Выберите файл `arm9loaderhax.bin`, нажмите (A) и выберите “Copy”
9. Нажмите (B), чтобы вернуться в главное меню FBI
10. Выберите "CTR NAND"
11. Выберите "\<current directory>"
12. Выберите "Paste", затем нажмите (A) для подтверждения
13. Выйдите из FBI нажатием кнопки (HOME)
14. Запустите Homebrew Launcher с домашнего экрана
15. Выберите "DSP Dump"
16. После завершения нажмите (START) для выхода
12. Перезагрузите приставку, с извлеченной SD-картой
  + Необходимо хотя бы раз загрузиться без карты памяти, чтобы настроить прошивку, расположенную в CTRNAND.
16. Нажимая (A) выберите следующие пункты: 
  + **"Show NAND or user string in System Settings"**
3. Если у вас **New 3DS**, так же отметьте следующие пункты: 
  + **"New 3DS CPU" to "Clock+L2(x)"**
    + Это увеличит частоту кадров в множестве игр, но может отразиться на стабильности других
    + Если какие-либо игры работают некорректно, отключите эту опцию
25. Вставьте SD-карту в приставку и нажмите (START) для того, чтобы сохранить настройки и перезагрузить приставку!
___

В случае проблем с запуском приложений DSi / DS (например, картриджи DS или DSiWare перестали работать), [обратитесь к разделу с проблемами и их решениями](troubleshooting#twl_broken).
{: .notice--warning}

{% capture notice-10 %}
Теперь вы можете использовать Luma3DS Updater для обновления кастомной прошивки. Запустите его и нажмите (А).
Это не тоже самое что Обновление системы (System Update). Это приложение обновляет только файлы Luma3DS.
Это обновит только те файлы Luma3DS, которые находятся на SD-карте. Если вы включите консоль без SD-карты, она загрузится используя Luma3DS из CTR NAND.
{% endcapture %}

<div class="notice--info">{{ notice-10 | markdownify }}</div>

{% capture notice-6 %}   
Теперь при старте ваша консоль по умолчанию загружает кастомную прошивку.Для запуска конфигуратора Luma3DS включите консоль с зажатой кнопкой (SELECT).
Для запуска Hourglass9 включите консоль с зажатой кнопкой (START).
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

Если вы хотите сменить регион вашего устройства, вам сюда - [Смена региона](region-changing).
{: .notice--success}

Для того, чтобы держать свой a9lh в актуальном состоянии, следуйте этой инструкции - [Обновление A9LH](updating-a9lh).
{: .notice--success}

<a name="part7" />
• Рекомендую ознакомиться с различными фишками, которые умеет Luma3DS [в этой статье](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage).   
• [Как делать резервные копии, редактировать и восстанавливать](https://gbatemp.net/threads/release-jks-savemanager-Homebrew-cia-save-manager.413143/) сохранения игр.    
• Как настроить внешний вид домашнего экрана кастомными [темами](themes) и [жетонами](badges) с помощью программ [СHMM2](http://rinnegatamante.it/site/3ds_hbs.php) и [GYTB](https://github.com/MrCheeze/GYTB).    
• [Как ставить игры?](http://vk.com/3ds_cfw?w=wall-125012133_147%2Fall)   
• [Как настроить freeshop](https://vk.com/3ds_cfw?w=wall-125012133_847%2Fall)   
{: .notice--success}