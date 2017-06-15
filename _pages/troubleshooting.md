---
title: "Проблемы и их решения"
permalink: /troubleshooting.html
sidebar:
  nav: "troubleshooting"
---

Если ваша консоль не загружается, найдите раздел, соответствующий вашей проблеме, и следуйте его инструкциям. После решения возникшей проблемы, вернитесь к основному руководству
(Этот раздел весьма обширный, воспользуйтесь Ctrl+F для поиска своей проблемы)
{: .notice--primary}

**Если решения вашей проблемы здесь не оказалось, то загрузите содержимое всех .log файлов из корня SD-карты на [Gist](https://gist.github.com/), а затем обращайтесь за помощью, детально описав проблему и испробованные способы решения.**
{: .notice--info}

Для использования [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme)-ссылок в этом руководстве необходим torrent-клиент, например [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--success}

## <a name="twl_broken" />DSi / DS игры не работают после завершения руководства

#### Что понадобится:

* TWL_FIRM `.cia`, соответствующие вашему устройству
    + <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [`New_3DS TWL_FIRM - v9936.cia`](magnet:?xt=urn:btih:eab8558c97b18b1f329a2bfcc3c899b84c082a27&dn=New%5F3DS%20TWL%5FFIRM%20-%20v9936.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
    + <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [`Old_3DS TWL_FIRM - v8817.cia`](magnet:?xt=urn:btih:17511eadb6e6f3ff22d04f90644e37bd2d96ca43&dn=Old%5F3DS%20TWL%5FFIRM%20-%20v8817.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [`TWL Version Data - v0.cia`](magnet:?xt=urn:btih:4a106681407fede5de95cc8bda635432481f6b5d&dn=TWL%20Version%20Data%20-%20v0.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [`DS Internet - v2048.cia`](magnet:?xt=urn:btih:2b9df8496922f2546dfb0b01220068ce53c19d3d&dn=DS%20Internet%20-%20v2048.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [`DS Download Play - v1024.cia`](magnet:?xt=urn:btih:b581d3c5d98f5e621fddfc1ce5704bb45bf05a8c&dn=DS%20Download%20Play%20-%20v1024.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* <i class="fa fa-magnet" aria-hidden="true" title="Это magnet-ссылка. Воспользуйтесь торрент-клиентом, чтобы скачать этот файл."></i> - [`Nintendo DS Cart Whitelist - v11264.cia`](magnet:?xt=urn:btih:7b90d506ad032a581a00035616eaa17a68c48eff&dn=Nintendo%20DS%20Cart%20Whitelist%20-%20v11264.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
 
#### Инструкция

##### Часть I - Подготовительные работы

1. Создайте папку `cias` в корне SD-карты, если таковой нет
1. Скопируйте `TWL Version Data - v0.cia` в папку `/cias/` на SD-карте
1. Скопируйте `DS Download Play - v1024.cia` в папку `/cias/` на SD-карте
1. Скопируйте `DS Internet - v2048.cia` в папку `/cias/` на SD-карте
1. Скопируйте `Nintendo DS Cart Whitelist - v11264.cia` в папку `/cias/` на SD-карте
1. Скопируйте `New_3DS TWL_FIRM - v9936.cia`  или `Old_3DS TWL_FIRM - v8817.cia` в папку `/cias/` на SD-карте

##### Часть II - Установка

1. Запустите FBI
1. Перейдите в `SD` -> `cias`
1. Выберите "\<current directory>"
1. Выберите "Install and delete all CIAs"
1. Нажмите (HOME) для выхода из FBI

## <a name="rm_nnid" />Удаление NNID без форматирования устройства

#### Что понадобится:

* Свежая версия [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)

#### Инструкция

Обратите внимание, что в некоторых версиях Luma3DS, меню Luma3DS chainloader отображается только в том случае, если в папке payloader более одного приложения. Если установлено только одно приложение, удерживание (START) при включении консоли запустит GodMode9 напрямую. Если вместо chainloader запускается окно конфигурации Luma3DS, просто нажмите (START), чтобы сохранить настройки, и следуйте инструкции дальше.
{: .notice--info}

1. Скопируйте `GodMode9.firm` из `.zip-архива` GodMode9 в папку `/luma/payloads/` на SD-карте
1. Включите консоль кнопкой питания, держа нажатой кнопку (START), чтобы запустить меню Luma3DS chainloader
1. Запустите GodMode9, нажав кнопку (A)
1. Перейдите в `[1:] SYSNAND CTRNAND` -> `data` -> (32-значный ID) -> `sysdata` -> `00010038`
1. Зажмите (R), затем нажмите (X) на файле `00000000`, чтобы переименовать его
1. Нажмите (ВВЕРХ), чтобы переименовать файл в `10000000`
1. Нажмите (A), чтобы сохранить изменения
1. Нажмите (A), чтобы разрешить запись в SysNAND и введите указанную комбинацию кнопок
1. Вернитесь в главное меню
1. Нажмите (START) для перезагрузки

## <a name="gw_fbi" />Не работает интеграция в Health & Safety на устройстве с пониженной прошивкой при помощи Gateway

Это вызвано крайне некорректной процедурой понижения прошивки Gateway, которая дублирует каждое приложение в системе. Одно из них не используется, но это сбивает с толку систему интеграции в H&S, из-за чего она интегрирует FBI в неиспользуемый дубликат.

Обратите внимание, что в некоторых версиях Luma3DS, меню Luma3DS chainloader отображается только в том случае, если в папке payloader более одного приложения. Если установлено только одно приложение, удерживание (START) при включении консоли запустит GodMode9 напрямую. Если вместо chainloader запускается окно конфигурации Luma3DS, просто нажмите (START), чтобы сохранить настройки, и следуйте инструкции дальше.
{: .notice--info}

1. Включите консоль кнопкой питания, держа нажатой кнопку (START), чтобы запустить меню Luma3DS chainloader
1. Запустите GodMode9, нажав кнопку (A)   
1. Перейдите в `[1:] SYSNAND CTRNAND` -> `title` -> `00040010`
1. Перейдите в папку, соответствующую вашей приставке и региону:
  + **Old 3DS EUR**: `00022300` -> `content`
  + **Old 3DS JPN**: `00020300` -> `content`
  + **Old 3DS USA**: `00021300` -> `content`
  + **New 3DS EUR**: `20022300` -> `content`
  + **New 3DS JPN**: `20020300` -> `content`
  + **New 3DS USA**: `20021300` -> `content`
1. Заметьте, что есть два вида app и tmp файлов, одни имеют расширение, написанное прописными буквами (`.TMD` и `.APP`), а другие строчными (`.tmd` и `.app`)
1. Удерживая (R), нажмите (Y), чтобы создать новую папку
1. Нажмите (А), чтобы подтвердить название новой папки - `newdir` (название папки не играет роли)
1. Нажмите (A), чтобы разрешить запись в SysNAND (lvl1) и введите указанную комбинацию кнопок
1. Нажмите (L) на каждом файле, расширение которого написано прописными буквами (`.TMD` и `.APP`), чтобы отметить его
1. Нажмите (Y), чтобы скопировать эти файлы
1. Перейдите в папку `newdir`
1. Нажмите (Y), чтобы вставить скопированные ранее файлы
1. Выберите "Move path(s)"
1. Теперь файлы с расширением из прописных букв перемещены в папку `newdir`
1. Нажмите (START) для перезагрузки
1. Вернитесь к разделу [Завершение установки](finalizing-setup) и попробуйте интегрировать FBI еще раз
1. Если это не помогло, верните файлы с расширением `.TMD` и `.APP` обратно в папку `content`, а файлы с расширением `.tmd` и `.app` переместите в папку `newdir`, затем попытайтесь интегрировать FBI еще раз

## <a name="ts_browser" />Не работает эксплойт на основе браузера

Эксплойты, базирующиеся на браузере (например, browserhax или 2xrsa), нестабильны и часто не срабатывают, но в некоторых случаях это можно исправить, следуя рекомендациям ниже
{: .notice--info}


1. Откройте браузер, затем настройки браузера (Settings)
1. Прокрутите до конца вниз и выберите "Удалить сохр. данные" (Initialize Savedata/Clear All Save Data)
1. Попробуйте запустить эксплойт еще раз

## <a name="ts_sys_down" />Черный экран при загрузке SysNAND

1. Попробуйте загрузиться без SD-карты, а затем верните ее в консоль
    1. Выключите консоль
    1. Извлеките SD-карту из консоли
    1. Включите консоль
    1. Когда появится меню HOME, вставьте SD-карту обратно в консоль
    1. Если это сработало, вам следует очистить данные меню HOME, удалив соответствующую вашему региону папку, находящуюся в`/Nintendo 3DS/(32-значный ID)/(32-значный ID)/extdata/00000000/`
        + EUR регион: Удалите `00000098`
        + JPN регион: Удалите `00000082`
        + USA регион: Удалите `0000008f`
        + CHN регион: Удалите `000000A1`
        + KOR регион: Удалите `000000A9`
        + TWN регион: Удалите `000000B1`
1. Попробуйте включить устройство без каких-либо картриджей (включая флеш-картриджи)
1. Если у вас есть хардмод и резервная копия NAND, прошейте бэкап обратно в SysNAND
1. Попробуйте загрузиться в режим восстановления и обновить систему    
    *Скорее всего это не будет работать на Old 3DS с прошивкой 2.1.0*    
    **Вы получите БРИК на New 3DS c прошивкой 2.1.0**
    1. Выключите консоль
    1. Зажмите (L)+(R)+(A)+(ВВЕРХ)
    1. Включите консоль
    1. Если вы вошли в режим восстановления, обновите консоль *при условии, что у вас есть возможность запустить Homebrew Launcher на последней версии прошивки, и понизить версию прошивки*, и попробуйте понизить прошивку ещё раз.
1. Ваша консоль, скорее всего, превратилась в брик. Вы можете обратиться за поддержкой на канал [Nintendo Homebrew в Discord](https://discord.gg/MWxPgEp) (англ.), [группу 3DS_CFW вконтакте](http://vk.com/3ds_cfw) (рус.)

## <a name="ts_sys_b9s" />Черный экран при загрузке SysNAND после установки b9s

1. Убедитесь, что у вас установлен рабочий загрузчик
    1. Проверьте, есть ли в корне SD-карты файл `boot.firm`.
1. Попробуйте сбросить настройки Luma3DS
    1. Удалите файл `/luma/config.bin` с SD-карты
    1. Выберите нужные настройки при запуске
1. Попробуйте запустить GodMode9
    1. Для устройства с Luma3DS, зажмите (START) при включении
1. Попробуйте очистить данные меню HOME
    1. Чтобы очистить данные меню HOME перейдите в папку `/Nintendo 3DS/(32 Character ID)/(32 Character ID)/extdata/00000000/`на SD-карте и удалите папку, соответствующую вашему региону
        + EUR регион: Удалите `00000098`
        + JPN регион: Удалите `00000082`
        + USA регион: Удалите `0000008f`
        + CHN регион: Удалите `000000A1`
        + KOR регион: Удалите `000000A9`
        + TWN регион: Удалите `000000B1`
1. Попробуйте включить устройство без каких-либо картриджей (включая флеш-картриджи)
1. Если вы понижали прошивку через Gateway, то убедитесь, что у вас установлена самая последняя версия Luma3DS (не ниже 6.2.3)
1. Если версия вашего NAND между 3.0.0 и 4.5.0, проделайте следующие действия:
	+ Убедитесь, что используете самую свежую версию Luma 3DS (6.6, или выше)
	+ Скачайте [этот файл](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/00000056) и переименуйте его в `native.firm`
	+ Скачайте [этот файл](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/cetk)
	+ Скопируйте `native.firm` и `cetk` в папку `/luma/` на SD-карте
	+ Если у вас Luma3DS версии 7.1 или ниже, переименуйте `native.firm` в `firmware.bin`
	+ После обновления прошивки удалите оба этих файла
1. Попробуйте выполнить [9.2.0 CTRTransfer](9.2.0-ctrtransfer)
1. Вы можете обратиться за поддержкой на канал [Nintendo Homebrew в Discord](https://discord.gg/MWxPgEp) (англ.), или [группу 3DS_CFW вконтакте](http://vk.com/3ds_cfw) (рус.).

## <a name="lumaupdater" />После обновления Luma3DS через Luma3DS Updater и теперь приставка не включается. Загорается синий диод и тухнет.

Вы установили Luma3DS на не поддерживаемый boot. 
{: .notice--warning}

Сперва попробуем определить boot какой версии прошит в приставку.
{: .notice--info}

#### Способ I - CTRNAND

Если прошивка выполнялась по этому гайду , то в CTRNAND приставки должны были быть скопированы файлы прошивки. Следовательно, вынув КП из приставки и запустив 3DS, вы сможете запустить Luma и увидеть её версию, из чего легко сделать вывод о том, какой загрузчик стоит в системе.
{: .notice--info}

1. Отключите 3DS
1. Достаньте КП из приставки
1. Загрузите приставку с зажатой кнопкой (SELECT)
1. Обратите внимание на первую строчку, там написана версия Luma3DS

    ![]({{ base_path }}/images/screenshots/luma.png)
	{: .text-center}
    {: .notice--info}

  + Если Luma3DS меньше, или равна 7.0.5, то у вас a9lh - [перейдите на b9s 1.2](a9lh-to-b9s)
  + Если Luma3DS 7.1, то у вас b9s 1.0 и нужно [обновить его до версии 1.2](updating-b9s)

#### Способ II - Перебор

Этот метод для тех, кто по каким-то причинам не стал устанавливать Luma3DS в CTRNAND, либо для тех, кто обновился до b9s 1.0 в момент его выхода и обновил Luma3DS через Luma3DS Updater
{: .notice--info}

1. Выключаем консоль
1. Вставляем SD-карту из приставки в компьютер
1. Качаем [Luma3DS 7.0.5](https://github.com/AuroraWright/Luma3DS/releases/tag/v7.0.5)
1. Копируем `arm9loaderhax.bin` из архива `Luma3DSv7.0.5.7z` в корень карты памяти с заменой
1. Возвращаем карту памяти в консоль
1. Пробуем запустить приставку. 
1. Если сработало и приставка запустилась, то у вас a9lh - [перейдите на b9s 1.2](a9lh-to-b9s). 
  + Если не сработало, двигаемся дальше
1. Качаем [Luma3DS 7.1](https://github.com/AuroraWright/Luma3DS/releases/tag/v7.1) 
1. Копируем `boot.firm` из архива `Luma3DSv7.1.7z` в корень карты памяти с заменой 
1. Возвращаем карту памяти в консоль 
1. Пробуем запустить приставку. 
1. Если сработало и приставка запустилась, то у вас b9s 1.0 и нужно обновить его до версии 1.2 по инструкции (updating-b9s)
  + Если не сработало, двигаемся дальше
1. Качаем Luma3DS 8 (https://github.com/AuroraWright/Luma3DS/releases/tag/v8.0 
1. Копируем `boot.firm` из архива `Luma3DSv8.0.7z` в корень карты памяти с заменой 
1. Возвращаем карту памяти в консоль 
1. Пробуем запустить приставку. 
1. Если сработало и приставка запустилась, то у вас b9s 1.2 и самая последняя версия Luma3DS
  + Если ничего не помогло, попробуйте выполнить [9.2.0 CTRTransfer](9.2.0-ctrtransfer)


## <a name="ts_sys_blue" />Голубой экран при загрузке (bootrom error)

1. У вас брик
1. Для восстановления вам понадобится [хардмод](https://gbatemp.net/threads/414498/) (англ.) или ремонт / замена устройства

<div id="vk_comments"></div>
<script type="text/javascript">
VK.Widgets.Comments("vk_comments", {limit: 10, attach: "*"});
</script>