---
title: "Смена региона"
permalink: /region-changing.html
author_profile: true
---
{% include toc title="Разделы" %}

Этот дополнительный раздел рассказывает о смене региона на вашей приставке с CFW, установленной в SysNAND. Это делается путем установки образа 9.2.0 CTRTransfer того региона, на который вы хотите перейти.
{: .notice--primary}

**Смена региона абсолютно не обязательна с тех пор, как в Luma3DS поддерживает запуск игр других регионов и индивидуальную [эмуляцию региона для отдельных игр](https://vk.com/3ds_cfw?w=wall-125012133_2091%2Fall).**
{: .notice--info}

Для использования [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme)-ссылок в этом руководстве необходим torrent-клиент, например [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--success}

Обратите внимание, что если у вас имеются другие файлы помимо `GodMode9.firm` в папке `/luma/payloads/` на SD-карте, удержание кнопки (START) при загрузке будет запускать "chainloader menu", где вам нужно будет использовать D-Pad и кнопку (A) для выбора "GodMode9" при выполнении этих инструкций.
{: .notice--info}

Этот процесс отсоединит NNID от приставки, поскольку он больше не будет совместим с вашей консолью. NNID привязан к конкретному устройству и к его региону, поэтому перенос NNID между приставками с разными регионами невозможен без применения [крайне сложных операций](https://gist.githubusercontent.com/yifanlu/e80db121d38aceb8cca0e03cefd5853b/raw/3c4dd89869156ca0f945a2791e699acfdb32b510/gistfile1.txt).
{: .notice--warning}

Практика показывает, что eShop почти наверняка перестанет работать, вне зависимости от типа вашей консоли. Все же, наибольший шанс есть у Old3DS и у New3DS, которая ни разу не была привязана к eShop.
{: .notice--warning}

Смена региона при помощи CTRTransfer (что используется в этом методе) по какой-то причине ломает reboot-патч. Причина этого неизвестна, но из-за этого владельцы Old 3DS теряют возможность играть в игры, требующие режим расширенной оперативной памяти (например, Monster Hunter, Super Smash Bros, и Pokémon Sun / Moon) до тех пор, пока не выполнят форматирование устройства (подробности в конце этой страницы).
{: .notice--warning}

Никогда не форматируйте New 2DS на прошивках версии <11.4.0, иначе вы не сможете завершить первоначальную настройку!
{: .notice--danger}

**Для продолжения, у вас уже ДОЛЖНА быть установлена Luma3DS и boot9strap или arm9loaderhax**
{: .notice--danger}

## Что понадобится
<a name="what_need" /> 

* Свежая версия [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* Свежая версия [FBI](https://github.com/Steveice10/FBI/releases/latest) (`.3dsx-файл`)
* [`ctrtransfer_ticket_copy.gm9`]({{ base_path }}/gm9_scripts/ctrtransfer_ticket_copy.gm9)
* Образ 9.2.0 ctrtransfer для вашего устройства и региона, на который вы хотите перейти
	+ <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [New 3DS или New 2DS - 9.2.0 - EUR - CTRTransfer](magnet:?xt=urn:btih:fed7bfeec0e52b42a77467cfb6ffd3e9dd2d5a70&dn=9.2.0-20E%5FCTRTransfer%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
	+ <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [New 3DS или New 2DS - 9.2.0 - JPN - CTRTransfer](magnet:?xt=urn:btih:b22d67fd02b3b0e30ac991e451db0f2d32e7beca&dn=9.2.0-20J%5FCTRTransfer%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
	+ <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [New 3DS или New 2DS - 9.2.0 - USA - CTRTransfer](magnet:?xt=urn:btih:985d47442dc470d1b9f908256bed041c63885f60&dn=9.2.0-20U%5FCTRTransfer%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
	~
	+ <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [Old 3DS или Old 2DS - 9.2.0 - EUR - CTRTransfer](magnet:?xt=urn:btih:8d6142313971b08f92257e7fb1c1d5689e34ed78&dn=9.2.0-20E%5FCTRTransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
	+ <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [Old 3DS или Old 2DS - 9.2.0 - JPN - CTRTransfer](magnet:?xt=urn:btih:24ad2b85e67013ef1f91178dca7ad2e40663b9b2&dn=9.2.0-20J%5FCTRTransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
	+ <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [Old 3DS или Old 2DS - 9.2.0 - USA - CTRTransfer](magnet:?xt=urn:btih:1dc79a2a0babb45497961888f369423a93135e2b&dn=9.2.0-20U%5FCTRTransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
 
## Инструкция
<a name="instructions" />

#### Часть I - Подготовительные работы
<a name="part1" />

1. Выключите консоль
1. Вставьте SD-карту в компьютер
1. Создайте папку `cias` в корне SD-карты
1. Скопируйте `GodMode9.firm` (или `GodMode9.bin` для пользователей arm9loaderhax) из `.zip-архива`GodMode9 в папку `/luma/payloads/` на SD-карте
1. Скопируйте папку `gm9` из `.zip-архива` `GodMode9` в корень SD-карты
1. Скопируйте `ctrtransfer_ticket_copy.gm9` в папку `/gm9/scripts/` на SD-карте
1. Скопируйте файл `.bin` из `.zip-архива` с образом 9.2.0 CTRTransfer в папку `/gm9out/` на SD-карте
1. Скопируйте `FBI.3dsx` в папку `/3ds/` в корне SD-карты
1. Вставьте SD-карту обратно в консоль

#### Часть II - CTRTransfer
<a name="part2" />

Обратите внимание, что если у вас имеются другие файлы помимо `GodMode9.firm` в папке `/luma/payloads/` на SD-карте, удержание кнопки (START) при загрузке будет запускать "chainloader menu", где вам нужно будет использовать D-Pad и кнопку (A) для выбора "GodMode9" при выполнении этих инструкций.
{: .notice--info}

1. Запустите GodMode9, удерживая (START) во время включения приставки
1. Если вам предложат создать бэкап важных файлов, нажмите кнопку (A) сделать это, затем нажмите (A) чтобы продолжить после завершения
1. Перейдите в `[0:] SDCARD` -> `gm9`
1. Нажмите (A) чтобы выбрать файл `.bin` CTRTransfer
1. Выберите "CTRNAND options..."
1. Выберите "Transfer image to CTRNAND"
1. Если появится запрос, выберите "Transfer to SysNAND"
  + Этот запрос отображается только если у вас есть EmuNAND
1. Нажмите (A), чтобы разрешить запись в SysNAND (lvl1) и введите указанную комбинацию кнопок
  + Этот процесс займет некоторое время
1. По завершению процесса, нажмите (A)
1. Нажмите (B), если появится запрос, чтобы не восстанавливать запрет на запись в раздел
1. Нажмите (Home), чтобы попасть в меню действий
1. Выберите "More..."
1. Выберите "Scripts..."
1. Выберите "ctrtransfer_ticket_copy"
1. Когда появится запрос, нажмите (A) для подтверждения
1. Нажмите (A), чтобы разрешить запись в SysNAND (lvl1) и введите указанную комбинацию кнопок
1. Нажмите (A) чтобы продолжить
1. Нажмите (A) чтобы вновь заблокировать права на запись
1. Нажмите (START) для перезагрузки
1. Обновите прошивку консоли, зайдя в Системные настройки (System Settings), затем "Прочие настройки" (Other Settings), затем листайте вправо до конца и выберите пункт "Обновление" (System Update)
  + Обновление консоли с установленным b9s + Luma (установлено у вас) безопасно
  + При появлении ошибки, поставьте в настройках подключения, в настройках DNS "Получать DNS автоматически" в положение "Да"

#### Часть III - Запуск FBI
<a name="part3" />

1. Запустите приложение Загружаемая игра
1. Нажмите (L) + (Вниз) + (SELECT) одновременно чтобы открыть меню Rosalina
1. Выберите "Miscellaneous options"
1. Выберите "Switch the hb. title to the current app."
1. Нажмите (B), чтобы продолжить
1. Нажмите (B) для возврата в главное меню Rosalina
1. Нажмите (B) для выхода из главного меню Rosalina
1. Нажмите (HOME), затем закройте приложение Загружаемая игра
1. Запустите приложение Загружаемая игра
1. Консоль должна загрузиться в Homebrew Launcher

#### Часть IV - Переустановка тикетов
<a name="part4" />

Если скрипт, запускавшийся выше, не нашел пользовательских тикетов на консоли, и предложил вам пропустить эту часть - так и поступите
{: .notice--info}

1. Выберите FBI в списке homebrew
1. Перейдите в `SD` -> `cias`
1. Нажмите (B), чтобы вернуться в папку "SD"
1. Выберите "gm9"
1. Выберите "out"
1. Выберите "ctrtransfer_tickets"
1. Выполните шаги ниже либо для папки `eshop` либо для папки `unknown`, или для обоих
  + Перейдите в папку
  + Выберите "\<current directory>"
  + Выберите "Install and delete all tickets"
  + Ожидайте. Может показаться, что приставка зависла, просто дайте ей время.
  + Нажмите (A) для подтверждения
  + Нажмите (B) для отмены установки тикетов из CDN.
1. Нажмите (HOME) для выхода из FBI

#### Часть V - Региональные настройки
<a name="part5" />

1. Откройте Системные настройки (System settings)
1. Перейдите в "Прочие настройки" (Other Settings), затем "Профиль" (Profile), затем "Настройки региона" (Region Settings)
1. Выберите страну из вашего нового региона
1. При появлении запроса о штате указывать его не нужно
1. Обновите SysNAND нового региона до последней версии

#### Часть VI - Удаление образа CTRTransfer
<a name="part6" />

Обратите внимание, что если у вас имеются другие файлы помимо `GodMode9.firm` в папке `/luma/payloads/` на SD-карте, удержание кнопки (START) при загрузке будет запускать "chainloader menu", где вам нужно будет использовать D-Pad и кнопку (A) для выбора "GodMode9" при выполнении этих инструкций.
{: .notice--info}

1. Запустите GodMode9, удерживая (START) во время включения приставки
1. Перейдите в `[0:] SDCARD` -> `gm9`
1. Нажмите (X), выделив файл `.bin` CTRTransfer чтобы удалить его
1. Нажмите (A) для подтверждения
1. Нажмите (START) для перезагрузки

___

Для Old 3DS и 2DS может потребоваться форматирование (используя TinyFormat или Системные настройки), иначе игры требующие режима расширенной памяти могут не заработать (Monster Hunter, Super Smash Bros, Pokemon Sun/Moon, и т. п.).
{: .notice--info}

