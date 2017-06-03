---
title: "Установка boot9strap (Homebrew Launcher)" #
lang: ru
permalink: installing-boot9strap-homebrew-launcher.html
sidebar:
  nav: "installing-boot9strap-homebrew-launcher"
---

Если вы взламывали ваше устройство ранее и у вас установлена кастомная прошивка на основе EmuNAND, помните, что данное руководство работает только с SysNAND и вы должны выполнять вся шаги находясь в SysNAND. Помните, что RedNAND и EmuNAND - немного разные реализации [одного и того же](http://3dbrew.org/wiki/NAND_Redirection) (англ.).
{: .notice--info}

#### <a name="what_need" />Что понадобится

* Свежая версия [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* Свежая версия [boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *(стандартную версию boot9strap; файл, без суффикса `dev`-)* 
* Свежая версия [safehax](https://github.com/TiniVi/safehax/releases/latest)
* Свежая версия [udsploit](https://github.com/smealum/udsploit/releases/latest)
* Свежая версия [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(`.7z`-архив)*

#### <a name="instructions" />Инструкция

##### <a name="part1" />Часть I - Подготовительные работы

1. Не выходя из Homebrew Launcher, извлеките SD-карту и вставьте её в компьютер
1. Скопируйте файл `boot.firm` из `.7z-архива` Luma3DS в корень SD-карты
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
  + Если появляется ошибка "PM INIT FAILED", убедитесь, что используете udsploit со включенным WiFi
  + Если "PM INIT FAILED" *всё ещё* появляется, попробуйте использовать [safehax версии r19](https://github.com/TiniVi/safehax/releases/tag/r19)
  + При зависании отключите питание консоли, зажав кнопку питания, и попробуйте снова
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

___

Следующий шаг: [Завершение установки](finalizing-setup)
{: .notice--success}

<div id="vk_comments"></div>
<script type="text/javascript">
VK.Widgets.Comments("vk_comments", {limit: 10, attach: "*"});
</script>