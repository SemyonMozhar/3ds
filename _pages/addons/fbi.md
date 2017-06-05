---
title: "Интеграция FBI"
permalink: /fbi.html
sidebar:
  nav: "fbi"
---

#### <a name="what_need" />Что понадобится
* Установленный и рабочий [b9s](updating-b9s) последней версии (*если уже делали, то повторно делать не нужно*)
* Свежая версия [FBI](https://github.com/Steveice10/FBI/releases/latest) *(`.cia-файл`и `.3dsx-файл`)*
* Свежая версия [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)

##### <a name="instructions" />Инструкция

##### <a name="part1" />Часть I - Подготовка

1. Выключите консоль
1. Вставьте SD-карту в компьютер
1. Скопируйте `boot.3dsx` в корень SD-карты
1. Скопируйте `GodMode9.firm` из `.zip-архива` GodMode9 в папку `/luma/payloads/` на SD-карте
1. Скопируйте `FBI.3dsx` в папку `/3ds/` на SD-карте
1. Скопируйте `FBI.cia` в папку `/cias/` в корне SD-карты
1. Вставьте SD-карту обратно в консоль

##### <a name="part2" />Часть II - Обновление системы

Если вы, следуя предыдущей версии этого руководства, выполнили CTRTransfer на прошивку 2.1.0 на *New 3DS*, [восстановите бэкап NAND](godmode9-usage#nand_restore), прежде чем приступить к этой части.
{: .notice--danger}

Если, следуя прошлой версии руководства, вы делали CTRTransfered прошивки 2.1.0 в *New 3DS*, [восстановите NAND](godmode9-usage#nand_restore) из резервной копии и только потом выполняйте эту часть.
{: .notice--danger}

Если прежде чем начать выполнять действия из этого руководства у вас уже был установлен EmuNAND и вы хотите перенести содержимое EmuNAND в SysNAND с кастомной прошивкой - сейчас самый подходящий момент. Выполните действия из раздела [перенос EmuNAND](move-emunand), перед выполнением этой части.
{: .notice--info}

1. Обновите прошивку консоли, зайдя в Системные настройки (System Settings), затем "Прочие настройки" (Other Settings), затем листайте вправо до конца и выберите пункт "Обновление" (System Update)
  + Обновление консоли с установленным B9S + Luma (установленых у вас) безопасно
  + При появлении ошибки, поставьте в настройках подключения, в настройках DNS "Получать DNS автоматически" в положение "Да"
  + Если вы все еще получаете ошибку и версия вашего NAND ниже 9.2.0, [выполните 9.2.0 CTRTransfer](9.2.0-ctrtransfer) и попробуйте обновиться еще раз

##### <a name="part3" />Часть III - Интеграция FBI

1. Запустите приложение Загружаемая игра (Download Play)
1. Нажмите (L) + (ВНИЗ) + (SELECT) одновременно чтобы открыть меню Rosalina
1. Выберите "Process patches menu..."
1. Выберите "Patch SM for the service checks"
1. Нажмите (B), чтобы продолжить
1. Выберите "Patch FS for the archive checks"
1. Нажмите (B), чтобы продолжить
1. Нажмите (B) для возврата в главное меню Rosalina
1. Выберите "Miscellaneous options"
1. Выберите "Switch the hb. title to the current app."
1. Нажмите (B), чтобы продолжить
1. Нажмите (B) для возврата в главное меню Rosalina
1. Нажмите (B) для выхода из главного меню Rosalina
1. Нажмите (HOME), затем закройте приложение Загружаемая игра (Download Play)
1. Запустите приложение Загружаемая игра (Download Play)
1. Консоль должна загрузиться в Homebrew Launcher

##### Часть IV - Установка CIA

1. Выберите FBI в списке homebrew
1. Перейдите в `SD` -> `cias`
1. Выберите "\<current directory>"
1. Выберите "Install and delete all CIAs" и нажмите (A) для подтверждения
1. Нажмите (HOME), затем закройте приложение Загружаемая игра (Download Play)

<div id="vk_comments"></div>
<script type="text/javascript">
VK.Widgets.Comments("vk_comments", {limit: 10, attach: "*"});
</script>