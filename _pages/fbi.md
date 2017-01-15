---
title: "Инжект FBI"
permalink: /fbi.html
---

#### Что нужно: 
* Установленный и рабочий [a9lh](installing-arm9loaderhax)
* [`fbi-2.4.2-injectable.zip`](magnet:?xt=urn:btih:f978b4cf5eda72823240b9c649f3fd2940a9f525&dn=fbi-2.4.2-injectable.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* Свежая версия [Hourglass9](https://github.com/d0k3/Hourglass9/releases/latest)

##### Что делать:

##### <a name="part1" />Часть I - Подготовка

13. Создайте папку `luma` в корне карты памяти, если таковой нет.
14. Создайте папку `payloads` в папке `luma` в корне карты памяти.
15. Скопируйте `Hourglass9.bin` из архива Hourglass9 в папку `/luma/payloads/` в корне КП и переименуйте `Hourglass9.bin` в `start_Hourglass9.bin`.
18. Скопируйте _содержимое_ архива `fbi-2.4.2-injectable.zip` в папку `/files9/` в корне КП.

##### <a name="part2" />Часть II - Внедрение FBI

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
