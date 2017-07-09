---
title: "Установка boot9strap (MSET)" #
lang: ru
permalink: installing-boot9strap-mset.html
sidebar:
  nav: "installing-boot9strap-mset"

---

Если вы взламывали ваше устройство ранее и у вас установлена кастомная прошивка на основе EmuNAND, помните, что данное руководство работает только с SysNAND и вы должны выполнять вся шаги находясь в SysNAND. Помните, что RedNAND и EmuNAND - немного разные реализации [одного и того же](http://3dbrew.org/wiki/NAND_Redirection) (англ.).
{: .notice--info}

#### <a name="what_need" />Что понадобится

* Свежая версия [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* Свежая версия [boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *(стандартный boot9strap; не `devkit-файл`, не `ntr-файл` и не `devkit-ntr-файл`)*
* Свежая версия [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(`.7z`-архив)*
* Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
* Любой флешкартридж для DS, работающий на вашей версии прошивки

#### <a name="instructions" />Инструкция

##### <a name="part1" />Часть I - Подготовительные работы

1. Выключите консоль
1. Вставьте SD-карту в компьютер
1. Скопируйте файл `boot.firm` из `.7z-архива` Luma3DS в корень SD-карты
1. Скопируйте _содержимое_ архива `starter.zip` в корень SD-карты
1. Создайте папку `boot9strap` в корне SD-карты
1. Скопируйте `boot9strap.firm` и `boot9strap.firm.sha` из `.zip-архива`boot9strap в папку `/boot9strap/` в корне SD-карты
1. Скопируйте `SafeB9SInstaller.dat` из `.zip-ахрива` SafeB9SInstaller в корень SD-карты
1. Вставьте SD-карту обратно в консоль
1. Скопируйте `SafeB9SInstaller.nds` из `.zip-ахрива` SafeB9SInstaller на ваш DS-флешкартридж
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

##### <a name="part4" />Часть IV - Настройка Luma3DS

1. Устройство загрузится в меню настройки Luma3DS
  + Если после включения экран остаётся чёрным, то перейдите к разделу [проблемы и их решения](troubleshooting#ts_sys_b9s)
1. Нажимая (A) выберите следующие пункты:    
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
  + Если появляется ошибка, просто переходите к следующей странице

___

Следующий шаг: [Завершение установки](finalizing-setup)
{: .notice--success}

<div id="vk_comments"></div>
<script type="text/javascript">
VK.Widgets.Comments("vk_comments", {limit: 10, attach: "*"});
</script>
