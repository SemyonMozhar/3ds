---
title: "Установка boot9strap (2xrsa)" #
lang: ru
permalink: installing-boot9strap-2xrsa.html
sidebar:
  nav: "installing-boot9strap-2xrsa"
---

Для использования [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme)-ссылок в этом руководстве необходим torrent-клиент, например [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--success}

#### <a name="what_need" />Что понадобится

* Свежая версия [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* Свежая версия [boot9strap](https://github.com/SciresM/boot9strap/releases/latest)
* Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)

#### <a name="instructions" />Инструкция

##### <a name="part1" />Часть I - Подготовительные работы

1. Выключите консоль
1. Вставьте SD-карту в компьютер
1. Скопируйте _содержимое_ папки `starter` из архива `starter.zip` в корень вашей SD-карты
1. Создайте папку `boot9strap` в корне SD-карты
1. Скопируйте `boot9strap.firm` и `boot9strap.firm.sha` из `.zip-архива` boot9strap в папку `/boot9strap/` в корне SD-карты
1. Скопируйте `arm9.bin` и `arm11.bin` из `.zip-архива` SafeB9SInstaller в корень SD-карты
1. Вставьте SD-карту обратно в консоль
1. Включите консоль

##### <a name="part2" />Часть II - Запуск SafeB9SInstaller

1. Запустите браузер на консоли и перейдите по одной из следующих ссылок
  + `http://2xrsa.3ds.guide`
  + Если вы забыли включить Wi-Fi на 2DS или New 3DS, это можно сделать, вытащив батарею и отключив зарядное устройство на несколько секунд, а затем снова включить консоль
  + Если появляется ошибка "This service is not available in your region", поменяйте регион в Системных настройках (System Settings) на соответствующий тому, который был установлен при 2.1.0 CTRTransfer
  + Если вы забыли отключить Родительский контроль до начала процесса CTRTransfer или не можете получить доступ к настройкам сети, консоль подключится автоматически к беспроводной сети с именем `attwifi` без пароля
  + При возникновении другой ошибки, обратитесь к разделу [Проблемы и их решения](troubleshooting#ts_browser)
1. Если эксплойт сработал, запустится SafeB9SInstaller

##### <a name="part3" />Часть III - Установка boot9strap

1. Дождитесь окончания всех проверок безопасности
1. При появлении запроса, введите указанную комбинацию кнопок для установки boot9strap
1. После завершения процесса, нажмите (A) для перезагрузки
1. Ваша консоль загрузится в boot9strap, затем автоматически выключится, потому что запускаемого файла еще нет
  + Приставка не загрузится до тех пор, пока вы не выполните инструкции на следующей странице; без паники, так и должно быть

___

Помните, что пользователи *New 3DS*, делавшие CTRTransfer прошивки 2.1.0 *должны* [восстановить резервную копию NAND](godmode9-usage#nand_restore) в промежутке между выполнением "Части II - Настройка Luma3DS" и "Часть III - Обновление системы" раздела [Завершение настройки](finalizing-setup).
{: .notice--danger}

Следующий шаг: [Завершение установки](finalizing-setup)
{: .notice--success}