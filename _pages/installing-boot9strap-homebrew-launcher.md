---
title: "Установка boot9strap (Homebrew Launcher)" #
lang: ru
permalink: installing-boot9strap-homebrew-launcher.html
sidebar:
  nav: "installing-boot9strap-homebrew-launcher"

---

Если вы взламывали ваше устройство ранее и у вас установлена кастомная прошивка на основе EmuNAND, помните, что данное руководство работает только с SysNAND и вы должны выполнять вся шаги находясь в SysNAND. Помните, что RedNAND и EmuNAND - немного разные реализации [одного и того же](http://3dbrew.org/wiki/NAND_Redirection) (англ.).
{: .notice--info}

Для использования [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme)-ссылок в этом руководстве необходим torrent-клиент, например [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--success}

#### <a name="what_need" />Что понадобится

* Свежая версия [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* Свежая версия [boot9strap](https://github.com/SciresM/boot9strap/releases/latest)
* Свежая версия [safehax](https://github.com/TiniVi/safehax/releases/latest)
* Свежая версия [udsploit](https://github.com/smealum/udsploit/releases/latest)

#### <a name="instructions" />Инструкция

##### <a name="part1" />Часть I - Подготовительные работы

1. Не выходя из Homebrew Launcher, извлеките SD-карту и вставьте её в компьютер
1. Создайте папку `boot9strap` в корне SD-карты
1. Скопируйте `boot9strap.firm` и `boot9strap.firm.sha` из `.zip-архива`boot9strap в папку `/boot9strap/` в корне SD-карты
1. Скопируйте `safehax.3dsx` в папку `/3ds/` на SD-карте
1. Скопируйте `udsploit.3dsx` в папку `/3ds/` на SD-карте
1. Скопируйте `SafeB9SInstaller.bin` из `.zip-архива` SafeB9SInstaller в корень SD-карты и переименуйте `SafeB9SInstaller.bin` в `safehaxpayload.bin`

    ![]({{ base_path }}/images/screenshots/boot9strap-hb-file-layout.png)
	{: .text-center}
    {: .notice--info}

1. Вставьте SD-карту обратно в консоль

##### <a name="part2" />Часть II - Запуск SafeB9SInstaller

1. Выберите udsploit в списке homebrew
  + Вам может потребоваться пролистать список вниз, чтобы увидеть нужный пункт
1. После завершения нажмите (START) для выхода из udsploit
  + Может потребоваться несколько попыток
  + При зависании отключите питание консоли, зажав кнопку питания, и попробуйте снова
1. Выберите safehax в списке homebrew
  + Вам может потребоваться пролистать список вниз, чтобы увидеть нужный пункт
  + Если появляется ошибка "PM INIT FAILED", попробуйте использовать [r19 версию safehax](https://github.com/TiniVi/safehax/releases/tag/r19)
  + При зависании отключите питание консоли, зажав кнопку питания, и попробуйте снова
1. Если эксплойт сработал, запустится SafeB9SInstaller

##### <a name="part3" />Часть III - Установка boot9strap

1. Дождитесь окончания всех проверок безопасности
1. При появлении запроса, введите указанную комбинацию кнопок для установки boot9strap
1. После завершения процесса, нажмите (A) для перезагрузки
1. Ваша консоль загрузится в boot9strap, затем автоматически выключится, поскольку запускаемого файла еще нет

___

Следующий шаг: [Завершение установки](finalizing-setup)
{: .notice--success}