---
title: "Переход с a9lh на boot9strap" #
lang: ru
permalink: a9lh-to-b9s.html
sidebar:
  nav: "a9lh-to-b9s"
---

Эта страница предназначена для пользователей arm9loaderhax, чтобы обновить их устройства до boot9strap.
{: .notice--warning}

Все будущие релизы Luma3DS будут только в формате `.firm`, который будет совместим только с boot9strap и sighax. Это означает, что для того, чтобы продолжать получать последние обновления Luma3DS, вы должны использовать эту страницу для обновления установки.
{: .notice--info}

Если в Luma3DS вы используете PIN-код, то при работе SafeB9SInstaller вы получите ошибку "OTP Crypto Fail". Для решения этой проблемы временно откажитесь от использования PIN-кода (вы сможете включить его обратно после обновления).
{: .notice--warning}

Для использования [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme)-ссылок в этом руководстве необходим torrent-клиент, например [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--success}

{% capture notice-1 %}
Сообщается о волне банов, выданных Nintendo пользователям CFW. Чтобы защитить себя, выполните следующие шаги перед началом этого руководства:

1. Откройте Системные настройки (System settings), затем "Интернет-настройки" (Internet Settings), затем "SpotPass", затем "Отправка информации о системе" (Sending of System Information)
1. Отключите опцию "Отправка информации о системе" (Sending of System Information)
1. Закройте Системные настройки (System settings)
1. Откройте Список друзей (Friend's List) (значок в виде лица на верхней строчке меню HOME, на нижнем экране)

    ![]({{ base_path }}/images/screenshots/friend-list.jpg)
	{: .text-center}
    {: .notice--info}

  + Если появляется ошибка и вас не пускают в меню, значит Список друзей уже отключен
1. Перейдите в настройки Списка друзей, затем "Настройки сообщений друга" (Friend Notification Settings), затем "Показать друзьям, во что вы играете" (Show friends what you're playing)
1. Отключите опцию "Показать друзьям, во что вы играете"
1. Закройте Список друзей
{% endcapture %}

<div class="notice--danger">{{ notice-1 | markdownify }}</div>

#### <a name="what_need" />Что понадобится

Обратите внимание, что требуемый ниже файл с именем `secret_sector.bin` это тот же, что присутствовал в различных версиях архива `data_input.zip`. Если у вас уже есть этот файл где-то на диске, вы можете использовать его, вместо загрузки файла ниже.
{: .notice--info}

Обратите внимание, что на New 3DS `secret_sector.bin` необходим для отката эксплойта arm9loaderhax, поэтому он не требуется для установки на не взломанную консоль. Если у вас не New 3DS, вам не нужен `secret_sector.bin`.
{: .notice--info}

* <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - **Только для пользователей New 3DS:** [`secret_sector.bin`](magnet:?xt=urn:btih:15a3c97acf17d67af98ae8657cc66820cc58f655&dn=secret_sector.bin&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl% 3A2710%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce)
* Свежая версия [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(`.7z-архив`)*
* Свежая версия [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* Свежая версия [boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *(стандартный boot9strap; не `devkit-файл`, не `ntr-файл` и не `devkit-ntr-файл`)*
* Свежая версия [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
* Свежая версия [Luma3DS Updater](https://github.com/KunoichiZ/lumaupdate/releases/latest)

#### <a name="instructions" />Инструкция

##### <a name="part1" />Часть I - Подготовительные работы

Для всех шагов в этой части перезаписывайте любые существующие файлы на SD-карте.
{: .notice--info}

1. Перейдите в Системные настройки (System Settings), Управление данными (Data Managment), Nintendo 3DS, Программы (Software) и удалите Luma3DS Updater
1. Выключите консоль
1. Вставьте SD-карту в компьютер
1. Скопируйте _содержимое_ архива `starter.zip` в корень SD-карты
1. Скопируйте файл `boot.firm` из `.7z-архива` Luma3DS в корень SD-карты
1. Создайте папку `cias` в корне SD-карты
1. Скопируйте `lumaupdater.cia` в папку `/cias/` на SD-карте
1. Создайте папку `boot9strap` в корне SD-карты
1. Скопируйте `GodMode9.firm` из `.zip-архива` GodMode9 в папку `/luma/payloads/` на SD-карте
 + Удалите все существующие `.bin` приложения в папке `/luma/payloads/` на SD-карте, так как они не будут совместимы с boot9strap-совместимыми версиями Luma3DS
1. Скопируйте `SafeB9SInstaller.bin` из `.zip-архива` SafeB9SInstaller в папку `/luma/payloads/` на SD-карте
1. Переименуйте`SafeB9SInstaller.bin` в папке `/luma/payloads/` на SD-карте в `start_SafeB9SInstaller.bin`
1. Скопируйте `boot9strap.firm` и `boot9strap.firm.sha` из `.zip-архива`boot9strap в папку `/boot9strap/` в корне SD-карты
1. **Только для пользователей New 3DS:** Скопируйте `secret_sector.bin` в папку `/boot9strap/` на SD-карте

    ![]({{ base_path }}/images/screenshots/updating-to-b9s-file-layout.png)
	{: .text-center}
    {: .notice--info}

1. Вставьте SD-карту обратно в консоль

##### <a name="part2" />Часть II - Установка boot9strap

1. Включите консоль кнопкой питания, держа нажатой кнопку (START), чтобы запустить меню Luma3DS chainloader
  + Некоторые версии Luma3DS будут напрямую запускать любое приложение, начинающееся со `start_`. Если вместо меню chainloader запускается SafeB9SInstaller, просто следуйте инструкции.
1. Запустите SafeB9SInstaller, нажав кнопку (A) на нём
  + При возникновении ошибки попробуйте использовать другую SD-карту, или отформатировать имеющуюся (предварительно сделав резервную копию всего её содержимого)
1. Дождитесь окончания всех проверок безопасности
  + Если вы получаете сообщение об ошибке "OTP Crypto Fail", скачайте <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [`aeskeydb.bin`](magnet:?xt=urn:btih:621f8af00638cb2b00d5bd0c6816543fa00b5fb1&dn=aeskeydb.bin&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce), поместите этот файл в папку `/boot9strap/` на SD-карте и попробуйте снова
1. При появлении запроса, введите указанную комбинацию кнопок для установки boot9strap
1. После завершения процесса, нажмите (A) для перезагрузки.
  + Если ваше устройство выключается при загрузке, убедитесь что вы скопировали `boot.firm` из `.7z-архива` Luma3DS в корень SD-карты

##### <a name="part3" />Часть III - Настройка Luma3DS

Этот раздел требуется только в том случае, если после перезагрузки появилось меню настроек Luma3DS.
{: .notice--info}

1. В меню настроек Luma3DS используйте кнопки (A) и D-Pad чтобы включить следующее:    
  + **"Enable game patching"**
  + **"Show NAND or user string in System Settings"**
1. Если у вас **New 3DS**, вы *также* можете включить следующие опции:
  + **"New 3DS CPU" выбрать значение "Clock+L2(x)"**
    + Это увеличит частоту кадров в множестве игр, но может отразиться на стабильности других
    + Если какие-либо игры работают некорректно, отключите эту опцию
	
    ![]({{ base_path }}/images/screenshots/luma-settings.png)
	{: .text-center}
    {: .notice--info}

1. Нажмите (START), чтобы сохранить настройки и перезагрузиться

##### <a name="part4" />Часть IV - CTRNAND Luma3DS

Обратите внимание, что в некоторых версиях Luma3DS, меню Luma3DS chainloader отображается только в том случае, если в папке payloader более одного приложения. Если установлено только одно приложение, удерживание (START) при включении консоли запустит GodMode9 напрямую. Если вместо chainloader запускается окно конфигурации Luma3DS, просто нажмите (START), чтобы сохранить настройки, и следуйте инструкции дальше.
{: .notice--info}

Если перед переходом на boot9strap у вас есть EmuNAND, данные из которого вы хотели бы сохранить, самое время воспользоваться инструкцией по [переносу EmuNAND](move-emunand) в SysNAND, а уже после выполнять данную часть.
{: .notice--info}

1. Перезагрузитесь, удерживая кнопку (START), чтобы запустить меню Luma3DS chainloader
1. Запустите GodMode9, нажав кнопку (A)
1. Перейдите в `[0:] SDCARD` -> `luma` -> `payloads`
1. Нажмите (X), выделив файл `start_SafeB9SInstaller.bin` чтобы удалить его
1. Нажмите (A) для подтверждения
1. Нажмите (B), чтобы вернуться к `[0:] SDCARD`
1. Нажмите (Y), выделив файл `boot.firm` чтобы скопировать его
1. Нажмите (B) для возврата в главное меню
1. Перейдите в `[1:] SYSNAND CTRNAND`
1. Нажмите (Y), чтобы вставить копию `boot.firm`
1. Выберите "Copy path(s)"
1. Нажмите (A), чтобы разрешить запись в SysNAND (lvl1) и введите указанную комбинацию кнопок
1. Нажмите (X), выделив файл `arm9loaderhax.bin`, чтобы удалить его
  + Если у вас нет этого файла, просто продолжайте следовать инструкциям
1. Нажмите (A) для подтверждения
1. Нажмите (B) для возврата в главное меню
1. Перейдите в `[0:] SDCARD`
1. Нажмите (Y) на папке `luma`, чтобы скопировать её
  + Если в папке `luma` остались файлы и/или папки (например, файлы LayeredFS) *помимо тех*, что были задействованы в прошлых версиях этого руководства (`config.bin` и `payloads`), вам следует скопировать только `config.bin` и `payloads`, выделив их с помощью (L) и нажав (Y) для копирования
1. Нажмите (B) для возврата в главное меню
1. Перейдите в `[1:] SYSNAND CTRNAND` -> `rw`
1. Нажмите (X) на существующей папке `luma`, чтобы удалить её
  + Если у вас нет этой папки, просто продолжайте следовать инструкциям
1. Нажмите (A) для подтверждения
1. Нажмите (Y), чтобы вставить копию папки `luma` из вашей SD-карты
  + Если ранее вы скопировали только `config.bin` и `payloads`, вам будет нужно создать папку `luma` вручную (удерживая (R), нажмите (Y), введите имя `luma`, затем нажмите (A) для подтверждения), затем перейти в папку `luma` и нажать (Y), чтобы вставить `config.bin` и `payloads`
  1. Нажмите (START) для перезагрузки

##### <a name="part5" />Часть V - Установка Luma3DS Updater

1. Запустите FBI
1. Перейдите в `SD` -> `cias`
1. Выберите `lumaupdater.cia`
1. Выберите "Install CIA", затем нажмите (A) для подтверждения
1. Нажмите (HOME) для выхода из FBI

___

Теперь вы можете удалить все файлы, связанные с arm9loaderhax, с SD-карты, такие как `arm9loaderhax.bin` в корне SD-карты и файл `aeskeydb.bin` в папке `files9` на SD-карте.
{: .notice--info}

Обратите внимание, что `.bak-файлы` в папке `/boot9strap/` на SD-карте необходимы только в случае неудачной установки boot9strap. После успешной установки вы можете удалить всю папку `boot9strap`.
{: .notice--info}

Эта версия Luma3DS Updater позволяет работать с boot9strap, путем загрузки и распаковки последнего Luma3DS `boot.firm`.
{: .notice--info}

{% capture notice-6 %} 
Для запуска конфигуратора Luma3DS включите консоль с зажатой кнопкой (SELECT). 
<br><br>
Теперь вы можете удерживать (START) при загрузке для запуска меню Luma3DS chainloader (обратите внимание, что меню Luma3DS chainloader отображается только если существует более одного приложения).
<br><br>
Теперь, с помощью зажатой комбинации клавиш (START) + (SELECT) + (X) при включении консоли, вы сможете сохранить копии ARM11 bootrom (`boot11.bin`), ARM9 bootrom (`boot9.bin`) и уникального [OTP](otp) вашей консоли (`OTP.bin`) в папку `/boot9strap/` на SD-карте (обратите внимание, что этот процесс не предусматривает отображения какого-либо оповещения).
{% endcapture %}

<div class="notice--info">{{ notice-6 | markdownify }}</div>

<div id="vk_comments"></div>
<script type="text/javascript">
VK.Widgets.Comments("vk_comments", {limit: 10, attach: "*"});
</script>