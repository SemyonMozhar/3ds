---
title: "Установка boot9strap (MSET)" #
lang: ru
permalink: installing-boot9strap-mset.html
sidebar:
  nav: "installing-boot9strap-mset"

---

Если вы взламывали ваше устройство ранее и у вас установлена кастомная прошивка на основе EmuNAND, помните, что данное руководство работает только с SysNAND и вы должны выполнять вся шаги находясь в SysNAND. Помните, что RedNAND и EmuNAND - немного разные реализации [одного и того же](http://3dbrew.org/wiki/NAND_Redirection) (англ.).
{: .notice--info}

Для использования [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme)-ссылок в этом руководстве необходим torrent-клиент, например [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--success}

#### <a name="what_need" />Что понадобится

* Свежая версия [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* Свежая версия [boot9strap](https://github.com/SciresM/boot9strap/releases/latest)
* Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
* Любой флешкартридж для DS, работающий на вашей версии прошивки

#### <a name="instructions" />Инструкция

##### <a name="part1" />Часть I - Подготовительные работы

1. Выключите консоль
1. Вставьте SD-карту в компьютер
1. Скопируйте _содержимое_ папки `starter` из архива `starter.zip` в корень вашей SD-карты
1. Создайте папку `boot9strap` в корне SD-карты
1. Скопируйте `boot9strap.firm` и `boot9strap.firm.sha` из `.zip-архива`boot9strap в папку `/boot9strap/` в корне SD-карты
1. Скопируйте `SafeB9SInstaller.dat` из `.zip-ахрива` SafeB9SInstaller в корень SD-карты
1. Вставьте SD-карту обратно в консоль
1. Скопируйте `SafeB9SInstaller.dat` из `.zip-ахрива` SafeB9SInstaller в корень SD-карты
1. Включите консоль

##### <a name="part2" />Часть II - Запуск SafeB9SInstaller

1. Запустите флешкартридж DS
1. Запустите `SafeB9SInstaller.nds`, используя флешкартридж
1. Выберите опцию, соответствующую версии прошивки
  + 4.X.X -> "4.x SafeB9SInstaller"
  + 6.X.X -> "6.x SafeB9SInstaller"
1. Перезагрузите консоль, зайдите в "Системные настройки" (System Settings), затем "Прочие настройки" (Other Settings), затем "Профиль" (Profile), затем "Профиль Nintendo DS" (Nintendo DS Profile)
1. Если эксплойт сработал, запустится SafeB9SInstaller

##### <a name="part3" />Часть III - Установка boot9strap

1. Дождитесь окончания всех проверок безопасности
1. При появлении запроса, введите указанную комбинацию кнопок для установки boot9strap
1. После завершения процесса, нажмите (A) для перезагрузки
1. Ваша консоль загрузится в boot9strap, затем автоматически выключится, поскольку запускаемого файла еще нет
  + Приставка не загрузится до тех пор, пока вы не выполните инструкции на следующей странице; без паники, так и должно быть

___

Следующий шаг: [Завершение установки](finalizing-setup)
{: .notice--success}