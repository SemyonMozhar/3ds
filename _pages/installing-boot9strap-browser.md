---
title: "Установка boot9strap (Браузер)" #
lang: ru
permalink: installing-boot9strap-browser.html
author_profile: true
---
{% include toc title="Разделы" %}

Если вы взламывали ваше устройство ранее и у вас установлена кастомная прошивка на основе EmuNAND, помните, что данное руководство работает только с SysNAND и вы должны выполнять вся шаги находясь в SysNAND. Помните, что RedNAND и EmuNAND - немного разные реализации [одного и того же](http://3dbrew.org/wiki/NAND_Redirection) (англ.).
{: .notice--info}

## Что понадобится
<a name="what_need" />

* Свежая версия [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* Свежая версия [boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *(стандартный boot9strap; не `dev-файл`, не `ntr-файл`)*
* Свежая версия [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(`.7z`-архив)*
* Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)

## Инструкция
<a name="instructions" />

#### Часть I - Подготовительные работы
<a name="part1" />

1. Выключите консоль
1. Вставьте SD-карту в компьютер
1. Скопируйте файл `boot.firm` из `.7z-архива` Luma3DS в корень SD-карты
1. Скопируйте _содержимое_ архива `starter.zip` в корень SD-карты
1. Создайте папку `boot9strap` в корне SD-карты
1. Скопируйте `boot9strap.firm` и `boot9strap.firm.sha` из `.zip-архива`boot9strap в папку `/boot9strap/` в корне SD-карты
1. Скопируйте `SafeB9SInstaller.dat` и `Launcher.dat` из `.zip-ахрива` SafeB9SInstaller в корень SD-карты

    ![]({{ base_path }}/images/screenshots/boot9strap-browser-file-layout.png)
    {: .notice--info}

1. Вставьте SD-карту обратно в консоль
1. Включите консоль

#### Часть II - Запуск SafeB9SInstaller
<a name="part2" />

1. Запустите браузер на консоли и перейдите по одной из следующих ссылок
  + `https://goo.gl/Pk5IZs` или `https://dukesrg.github.io/?SafeB9SInstaller.dat`
  + `https://goo.gl/f8GbSf` или `http://go.gateway-3ds.com/`
  + `https://goo.gl/ASCLSV` или `http://www.reboot.ms/3ds/load.html?Launcher.dat`
  + `https://goo.gl/etmY59` или `http://dukesrg.dynu.net/3ds/rop?GW17567.dat&Launcher.dat`
  + **Или сосканируйте камерой QR, если QR-сканер есть в вашей версии прошивки:**

	Для того, чтобы попасть в QR-scanner, нажмите одновременно (L)+(R), находясь на домашнем экране, а затем нажмите пиктограмму с изображением QR-кода на нижнем экране.
	{: .notice--info}

	![]({{ base_path }}/images/QR/dukeGithub.png)	![]({{ base_path }}/images/QR/gateway.png)
	<br>
	![]({{ base_path }}/images/QR/goReboot.png)	![]({{ base_path }}/images/QR/dukeDynu.png)
	{: .text-center}
    {: .notice--info}
  
  + В случае, если первая ссылка не сработала, попробуйте все остальные (некоторое консоли не могут использовать первую ссылку, в то время как другие не могут использовать последние три)
  + При возникновении ошибки, обратитесь к разделу [Проблемы и их решения](troubleshooting#ts_browser)
1. Если эксплойт сработал, запустится SafeB9SInstaller

#### Часть III - Установка boot9strap
<a name="part3" />

1. Подождите окончания всех проверок безопастности
1. При появлении запроса, введите указанную комбинацию кнопок для установки boot9strap
1. После завершения процесса, нажмите (A) для перезагрузки

#### Часть IV - Настройка Luma3DS
<a name="part4" />

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

