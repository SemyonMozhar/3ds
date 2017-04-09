---
title: "Запуск Decrypt9 через MSET"
permalink: /decrypt9-mset.html
sidebar:
  nav: "decrypt9-mset"
---

Если вы взламывали ваше устройство ранее и у вас установлена кастомная прошивка на основе EmuNAND, помните, что данное руководство работает только с SysNAND и вы должны выполнять вся шаги находясь в SysNAND. Помните, что RedNAND и EmuNAND - немного разные реализации [одного и того же](http://3dbrew.org/wiki/NAND_Redirection).
{: .notice--info}

Если перед понижением прошивки до 2.1.0 на 2DS или New 3DS вы забыли включить Wi-Fi, вы можете включить его, вытащив батарею и отключив зарядное устройство на несколько секунд, затем снова включив консоль.
{: .notice--info}

Если вы использовали Управление microSD (microSD Management) для передачи данных на New 3DS, вы не сможете им воспользоваться на прошивке 2.1.0. Убедитесь, что у вас есть картридер для microSD-карт, прежде чем продолжить.
{: .notice--info}

Для использования [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme)-ссылок в этом руководстве необходим torrent-клиент, например [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--info}

**На данный момент подключение устройства к интернету НЕОБХОДИМО, чтобы продолжить после 2.1.0 CTRTransfer.**
{: .notice--warning}

**Отключите родительский контроль (parental control) на устройстве перед тем, как перейти к 2.1.0 CTRTransfer. Если вы не знаете пароля, воспользуйтесь [генератором мастер-ключа](https://mkey.salthax.org/) (англ.). Если вы не можете отключить родительский контроль из-за того, что привязанный NNID зарегистрирован на ребенка младше 13 лет, вместо этого вам следует выставить все опции в состояние "не ограничивать" (do not restrict).**
{: .notice--warning}

**Выполнение CTRTransfer удалит все пользовательские ticket-файлы (которые дают доступ к играм) с вашего устройства до тех пор, пока не будет восстановлен бэкап.**
{: .notice--danger}

**НИКОГДА не форматируйте 2DS на прошивках ниже 6.0.0, иначе вы не сможете закончить первоначальную настройку и получите БРИК!**
{: .notice--danger}

**НИКОГДА не обновляйте New 3DS с прошивкой 2.1.0 (это старая прошивка Old 3DS), это чревато БРИКОМ! Сначала ОБЯЗАТЕЛЬНО восстановите NAND из резервной копии или произведите обратный CTRTransfer на стандартную прошивку New 3DS!**
{: .notice--danger}

{% capture notice %}
**Вы ГАРАНТИРОВАННО получите НЕВОССТАНАВЛИВАЕМЫЙ брик, если вы введете New 3DS с прошивкой 2.1.0 в режим сна!**    
**Это происходит только при закрытии крышки, _пока устройство включено_; это не касается выключения консоли.**    
**Устройство переходит в спящий режим только когда крышка закрыта. Таймера, или чего-то похожего, в системе нет.**    
**Оказавшись на 2.1.0 без промедления сделайте все необходимые шаги, чтобы избежать этого!**    
{% endcapture %}

<div class="notice--danger">{{ notice | markdownify }}</div>

#### <a name="steps" />Описание шагов

В этой части мы будем прошивать [CTRNAND](https://www.3dbrew.org/wiki/Flash_Filesystem#CTR_partition) (англ.) консоли до версии 2.1.0, чтобы воспользоваться уязвимостью получения уникального для устройства [OTP](otp). OTP необходим для установки arm9loaderhax и **не может быть использован** на других устройствах.

Это достигается благодаря [установке заранее подготовленного образа CTRTransfer](https://www.reddit.com/r/3dshacks/comments/4zhe4a/) (англ.), содержащего 2.1.0, и копированию в него уникальных для каждой консоли файлов (таких как `moveable.sed` и `SecureInfo_A`), а затем восстановлением базы данных тайтлов.

#### <a name="what_need" />Что понадобится

* Флешкартридж для DS, работающий на вашей версии прошивки
* Свежая версия [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/latest/)
* Образ 2.1.0 CTRTransfer для вашего устройства и региона     
*(Если вашего региона нет в списке, выберите любой)*:
  +    <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [New 3DS или Old 3DS или 2DS 2.1.0 - EUR - CTRTransfer](magnet:?xt=urn:btih:89acc9c1b488b8b38251de0ddf07975d6bd354a1&dn=2.1.0-4E%5FCTRTransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  +    <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [New 3DS или Old 3DS или 2DS 2.1.0 - JPN - CTRTransfer](magnet:?xt=urn:btih:3dbb9c9c85a33c6242f424dcbaebcacdd8a5912b&dn=2.1.0-4J%5FCTRTransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [New 3DS или Old 3DS или 2DS 2.1.0 - USA - CTRTransfer](magnet:?xt=urn:btih:1609ce9ee7b0ed9b6dea0b3e7cca4fc52dad6ff4&dn=2.1.0-4U%5FCTRTransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)

#### <a name="instructions" />Инструкция

##### <a name="part1" />Часть I - Подготовительные работы

1. Выключите консоль
1. Вставьте SD-карту в компьютер
1. Создайте папку `files9` в корне SD-карты, если таковой нет
1. Скопируйте 2.1.0 `.bin` и `.bin.sha` из `.zip-архива` CTRTransfer в папку `/files9/` на SD-карте
2. Скопируйте `Launcher.dat` и `Decrypt9WIP.dat` из `.zip-ахрива` Decrypt9WIP в корень SD-карты
1. Вставьте SD-карту обратно в консоль
4. Скопируйте `Decrypt9.nds` из `.zip-архива` Decrypt9 на флешкартридж DS
1. Включите консоль

##### <a name="part2" />Часть II - Запуск Decrypt9

1. Запустите флешкартридж DS
6. Запустите `Decrypt9.nds`, используя флешкартридж
7. Выберите опцию, соответствующую версии прошивки:
  + 4.X.X -> "4.x Decrypt9WIP"
  + 6.X.X -> "6.x Decrypt9WIP"
1. Перезагрузите консоль, зайдите в "Системные настройки" (System Settings), затем "Прочие настройки" (Other Settings), затем "Профиль" (Profile), затем "Профиль Nintendo DS" (Nintendo DS Profile)
1. Если эксплойт сработал, запустится Decrypt9

##### <a name="part3" />Часть III - CTRTransfer

**Наличие бэкапа NAND _вашей консоли_ ОБЯЗАТЕЛЬНО. Вам будет предложено создать его в одном из шагов инструкции, если у вас ещё нет бэкапа.**
{: .notice--danger}

**Если вы не уверены, есть ли у вас бэкап, создайте его, нажав на (A) по запросу, чтобы убедиться в наличии бэкапа в дальнейшем.**
{: .notice--danger}

**Если у вас недостаточно места для создания бэкапа, вы можете сделать бэкап на другую SD-карту, или очистить место на текущей, нажав (SELECT) в главном меню Decrypt9WIP, что позволит безопасно извлечь SD-карту с последующей заменой или очищением места**
{: .notice--danger}

1. Выберите "SysNAND Options", затем "CTRNAND Transfer", затем "Auto CTRNAND Transfer"
2. Введите комбинацию кнопок, указанную на экране, затем выберите образ для 2.1.0 ctrtransfer и нажмите (A)
3. Если у вас нет NAND бэкапа, **сделайте бэкап SysNAND в файл `NANDmin.bin` при появлении запроса "Optional NAND backup" нажатием кнопки (А)**
  + **Наличие бэкапа NAND _вашей консоли_ НЕОБХОДИМО.**
  + **Отсутствие резервной копии приведет к ПОТЕРЕ всех установленных игр и сохранений!**
4. Дождитесь завершения процесса. Это может занять некоторое время
5. По завершению переноса данных, нажмите (В)
6. Нажмите (SELECT), чтобы извлечь SD-карту
7. Удалите файлы образа 2.1.0 ctrtransfer `.bin` и `.bin.sha` из папки `/files9/` на SD-карте
8. Нажмите (START) для перезагрузки консоли, не вставляя SD-карту в устройство
  + Консоль с прошивкой 2.1.0 при загрузке будет зависать на чёрном экране, если SD-карта будет находиться в консоли до загрузки меню HOME
  + Каждый раз при перезагрузке на 2.1.0 необходимо извлекать SD-карту и вставлять обратно после загрузки меню HOME
  + Не вставляйте SD-карту обратно в консоль. На следующей странице вы будете копировать на неё файлы
  + Это будет исправлено после восстановления вашей резервной копии на следующей странице

___

*(Изменение цвета или искажения экрана - норма для некоторых устройств на 2.1.0; они исчезнут сразу после восстановления вашей резервной копии)*
{: .notice--info}

{% capture notice %}
**Вы ГАРАНТИРОВАННО получите НЕВОССТАНАВЛИВАЕМЫЙ брик, если вы введете New 3DS с прошивкой 2.1.0 в режим сна!**    
**Это происходит только при закрытии крышки, _пока устройство включено_; это не касается выключения консоли.**    
**Устройство переходит в спящий режим только когда крышка закрыта. Таймера, или чего-то похожего, в системе нет.**    
**Оказавшись на 2.1.0 без промедления сделайте все необходимые шаги, чтобы избежать этого!**    
{% endcapture %}

<div class="notice--danger">{{ notice | markdownify }}</div>

Следующий шаг: [Установка arm9loaderhax](installing-arm9loaderhax)
{: .notice--primary}