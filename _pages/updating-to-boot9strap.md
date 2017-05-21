---
title: "Обновление до boot9strap" #
lang: ru
permalink: updating-to-boot9strap.html
---

Эта страница предназначена для текущих пользователей arm9loaderhax для обновления их устройств до boot9strap.
{: .notice--info}

Все будущие релизы Luma3DS будут только в формате «.firm», который будет совместим только с boot9strap и sighax. Это означает, что для того чтобы продолжать получать последние обновления Luma3DS, вы должны использовать эту страницу для обновления установки.
{: .notice--info}

Если у вас установлен ПИН-код на Luma, вы должны временно его отключить, в противном случае вы получите ошибку "OTP Crypto Fail". После обновления вы можете включить пин-код назад.
{: .notice--warning}

{% capture notice-1 %}

Если у вас установлена программа "3dsafe", вы должны удалить ее чтобы продолжить, иначе вы получите ошибку "OTP Crypto Fail".
<br><br>
Чтобы сделать это, распакуйте [свежую версию arm9loaderhax](https://github.com/AuroraWright/arm9loaderhax/releases) (файлы payload) в папку с именем `a9lh` в корне SD-карты, запустите 3dsafe, введите пин-код и во время ввода держите нажатой последнюю кнопку. Продолжая удерживать нажатой эту кнопку, нажмите (X), чтобы запустить встроенный SafeA9LHInstaller, затем нажмите (Select), чтобы "обновиться" до стандартного arm9loaderhax.

{% endcapture %}

<div class="notice--warning">{{ notice-1 | markdownify }}</div>

Если вы в настоящее время используете или использовали ранее программу "3dsafe", вы можете получить сообщение об ошибке "OTP Crypto Fail" при попытке запуска SafeB9SInstaller. Воспользуйтесь решением, предложенным [здесь](https://github.com/Plailect/Guide/issues/1094)
{: .notice--warning}

Для использования [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme)-ссылок в этом руководстве необходим torrent-клиент, например [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--success}

#### <a name="what_need" />Что понадобится

Обратите внимание, что требуемый ниже файл с именем `secret_sector.bin` это тот же, что присутствовал в различных версиях файл `data_input.zip`. Если у вас уже есть этот файл на где-то диске, вы можете использовать его, вместо загрузки файла ниже.
{: .notice--info}

Обратите внимание, что `secret_sector.bin`необходим для отката arm9loaderhax эксплойта, поэтому он не требуется для установки на не взломанную консоль.
{: .notice--info}

* <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [`secret_sector.bin`](magnet:?xt=urn:btih:15a3c97acf17d67af98ae8657cc66820cc58f655&dn=secret_sector.bin&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce)
* Свежая версия [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(`.7z-архив`)*
* Свежая версия [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* Свежая версия [boot9strap](https://github.com/SciresM/boot9strap/releases/latest)
* Свежая версия [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* Свежая версия [Luma3DS Updater](https://github.com/KunoichiZ/lumaupdate/releases/latest)

#### <a name="instructions" />Инструкция

##### <a name="part1" />Часть I - Подготовительные работы

1. Выключите консоль
1. Вставьте SD-карту в компьютер
1. Скопируйте файл `boot.firm` из `.7z-архива` Luma3DS в корень SD-карты
1. Создайте папку `cias` в корне SD-карты
1. Скопируйте `lumaupdater-v2.0.cia` в папку `/cias/` на SD-карте
1. Создайте папку `boot9strap` в корне SD-карты
1. Скопируйте `GodMode9.firm` из `.zip-архива` GodMode9 в папку `/luma/payloads/` на SD-карте
1. + Удалите все существующие `.bin` приложения в папке `/luma/payloads/` на SD-карте, так как они не будут совместимы с boot9strap совместимы версиями Luma3DS
1. Скопируйте `SafeB9SInstaller.bin` из `.zip-архива` SafeB9SInstaller в папку `/luma/payloads/` на SD-карте
1. Переименуйте`SafeB9SInstaller.bin` в папке `/luma/payloads/` на SD-карте в `start_SafeB9SInstaller.bin`
1. Скопируйте `boot9strap.firm` и `boot9strap.firm.sha` из `.zip-архива`boot9strap в папку `/boot9strap/` в корне SD-карты
1. Скопируйте `secret_sector.bin` в папку `/boot9strap/` на SD-карте

    ![]({{ base_path }}/images/screenshots/updating-to-b9s-file-layout.png)
    {: .notice--info}

1. Вставьте SD-карту обратно в консоль

##### <a name="part2" />Часть II - Установка boot9strap

1. Включите консоль кнопкой питания, держа нажатой кнопку (Start), чтобы запустить меню Luma3DS chainloader
  + Некоторые версии Luma3DS будут напрямую запускать любое приложение начинающееся со `start_`
  + Если ваша версия делает это, просто продолжайте следовать инструкциям
1. Запустите SafeB9SInstaller, нажав кнопку (A) на нём
1. Подождите окончания всех проверок безопастности
1. При появлении запроса, введите указанную комбинацию кнопок для установки boot9strap
1. После завершения процесса, нажмите (A) для перезагрузки
  + Если ваше устройство выключается при загрузке, убедитесь что вы скопировали `boot.firm` из `.7z-архива` Luma3DS в корень SD-карты

##### <a name="part3" />Часть III - Настройка Luma3DS

Этот раздел требуется только в том случае, если после перезагрузки появилось меню настроек Luma3DS.
{: .notice--info}

1. В меню настроек Luma3DS используйте кнопки (A) и D-Pad чтобы включить следующее:    
  + **"Show NAND or user string in System Settings"**
1. Нажмите (Start), чтобы сохранить настройки и перезагрузиться

##### <a name="part4" />Часть IV - CTRNAND Luma3DS

1. Перезагрузитесь, удерживая кнопку (Start), чтобы запустить меню Luma3DS chainloader
1. Запустите GodMode9, нажав кнопку (A)
1. Перейдите в `[0:] SDCARD` -> `luma` -> `payloads`
1. Нажмите (X), выделив файл `start_SafeB9SInstaller.bin` чтобы удалить его
1. Нажмите (A) для подтверждения
1. Нажмите (B), чтобы вернуться к `[0:] SDCARD`
1. + Нажмите (Y), выделив файл `boot.firm` чтобы скопировать его
1. Нажмите (B) для возврата в главное меню
1. Перейдите в `[1:] SYSNAND CTRNAND`
1. Нажмите (Y), чтобы вставить копию `boot.firm`
1. Выберите "Copy path(s)"
1. Нажмите (A), чтобы разрешить запись в SysNAND (lvl1) и введите указанную комбинацию кнопок
1. Нажмите (X) на `arm9loaderhax.bin`, чтобы удалить его
  + Если у вас нет этого файла, просто продолжайте следовать инструкциям
1. Нажмите (A) для подтверждения
1. Нажмите (B) для возврата в главное меню
1. Удерживая (R) нажмите (B) для того, чтобы извлечь SD-карту
1. Извлеките SD-карту из консоли
1. Нажмите (START) для перезагрузки с извлеченной SD-картой
  + Необходимо хотя бы раз загрузиться без SD-карты, чтобы настроить Luma3DS, установленную в раздел CTRNAND
1. Нажимая (A) выберите следующие пункты:    
  + **"Show NAND or user string in System Settings"**
1. Вставьте SD-карту обратно в консоль
1. Нажмите (Start), чтобы сохранить настройки и перезагрузиться

### Часть V - Установка Luma3DS Updater

1. Запустите FBI
1. Перейдите в `SD` -> `cias`
1. Выберите `lumaupdater-v2.0.cia`
1. Выберите "Install CIA", затем нажмите (A) для подтверждения
1. Нажмите (HOME) для выхода из FBI

___

Теперь вы можете удалить все файлы, связанные с arm9loaderhax, с SD-карты, такие как `arm9loaderhax.bin` в корне SD-карты и файл `aeskeydb.bin` в папке `files9` на SD-карте.
{: .notice--info}

Обратите внимание, что `firm0firm1.bak` и `sector0x96.bak` в папке `/boot9strap/` на SD-карте необходимы только в случае неудачной установки boot9strap. После успешной установки вы можете удалить всю папку `boot9strap`.
{: .notice--info}

Эта версия Luma3DS Updater позволяет работать с boot9strap, путем загрузки и распаковки последнего Luma3DS `boot.firm`.
{: .notice--info}

{% capture notice-6 %} 
Для запуска конфигуратора Luma3DS включите консоль с зажатой кнопкой (Select). 
Теперь вы можете удерживать (START) при загрузке для запуска меню Luma3DS chainloader (обратите внимание, что меню Luma3DS chainloader отображается только если существует более одного приложения).
Теперь, с помощью зажатой комбинации клавиш (START) + (SELECT) + (X) при включении консоли, вы сможете сохранить копии ARM11 bootrom (`boot11.bin`), ARM9 bootrom (`boot9.bin`) и уникального OTP вашей консоли (`OTP.bin`) в папку `/boot9strap/` на SD-карте (обратите внимание, что этот процесс не предусматривает отображения какого-либо оповещения).
{% endcapture %}

<div class="notice--info">{{ notice-6 | markdownify }}</div>