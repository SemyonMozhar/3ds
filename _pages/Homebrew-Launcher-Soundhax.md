---
title: "Использование SoundHax для запуска Hombrew Launcher"
permalink: /HOMEbrew-launcher-soundhax.html
author_profile: true
---
{% include toc title="Разделы" %}

Существует много различных точек входа в HOMEbrew Launcher.

SoundHax совместим с версиями прошивки от 9.0.0 до 11.3.0 включительно в регионах EUR, JPN, KOR и USA.

Убедитесь, что Беспроводной режим (Wireless Communication) включен, так как udsploit (используется на следующей странице) потребует активный беспроводной модуль для своей работы, и некоторые консоли (New 3DS, New 2DS и Old 2DS) не могут включить Беспроводной режим, находясь в HOMEbrew Launcher. Достаточно включить Беспроводной режим (Wireless Communication); наличие соединения с точкой доступа не обязательно.

Заметьте, что обновление на картридже позволяет обновить только базовые функции консоли, такие как Системные настройки, меню HOME, и т. п. Приложение Звук Nintendo 3DS и сетевые функции, такие как Перенос системы, Интернет-браузер, Площадь StreetPass Mii или eShop с картриджа не обновляются.
{: .notice--warning}

{% capture notice-1 %}

Заметьте, что обновление на картридже позволяет обновить только базовые функции консоли, такие как Системные настройки, меню HOME, и т. п. Приложение Звук Nintendo 3DS и сетевые функции, такие как Перенос системы, Интернет-браузер, Площадь StreetPass Mii или eShop с картриджа не обновляются.
<br><br>
Помните, что обновление картриджем с версии, содержащей старое приложение Звук Nintendo 3DS *(<7.0.0 для Old 3DS регионов EUR, JPN, KOR, и USA)*, сделает невозможной работу [Soundhax](HOMEbrew-launcher-soundhax)! Вам понадобится [альтернативный метод](HOMEbrew-launcher-alternatives) запуска HOMEbrew Launcher!
{% endcapture %}

<div class="notice--warning">{{ notice-1 | markdownify }}</div>

## Что понадобится
<a name="what_need" /> 

* HOMEbrew [STARTer Kit](http://smealum.github.io/ninjhax2/STARTer.zip)
* Последняя версия [SoundHax](http://soundhax.com/) *(для вашего устройства и региона)*
* Свежая версия [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* Свежая версия [boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *(стандартный boot9strap; не `dev-файл`, не `ntr-файл`)*
* Свежая версия [safehax](https://github.com/TiniVi/safehax/releases/latest)
* Свежая версия [udsploit](https://github.com/smealum/udsploit/releases/latest)
* Свежая версия [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(`.7z`-архив)*
* [otherapp payload](https://smealum.github.io/3ds/#otherapp) *(для вашей версии ПО и региона приставки; если версия вашего браузера меньше, чем -7, попробуйте использовать otherapp для версии -7)*

## Инструкция

1. Выключите консоль
1. Вставьте SD-карту в компьютер
1. Скопируйте _содержимое_ архива `STARTer.zip` в корень SD-карты
1. Скопируйте Soundhax `.m4a` в корень вашей SD-карты
1. Скопируйте otherapp payload в корень вашей SD-карты и переименуйте его в `otherapp.bin`
1. Скопируйте `boot.firm` из `.7z-архива` с Luma3DS в корень SD-карты
1. Создайте папку `boot9strap` в корне вашей SD-карты
1. Скопируйте `boot9strap.firm` и `boot9strap.firm.sha` из `.zip-архива` с boot9strap в папку `/boot9strap/` на вашей SD-карте
1. Скопируйте `safehax.3dsx` в папку `/3ds/` на вашей SD-карте
1. Скопируйте `udsploit.3dsx` в папку `/3ds/` на вашей SD-карте
1. Скопируйте `SafeB9SInstaller.bin` из `.zip-архива` с SafeB9SInstaller в корень вашей SD-карты и переименуйте его в `safehaxpayload.bin`

    ![]({{ base_path }}/images/screenshots/boot9strap-hb-file-layout.png)
	{: .text-center}
    {: .notice--info}

1. Вставьте SD-карту обратно в консоль
1. Включите консоль
1. Запустите приложение Звук Nintendo 3DS (Nintendo 3DS Sound)

    ![]({{ base_path }}/images/screenshots/soundhax-welcome.png)
	{: .text-center}
    {: .notice--info}

1. Если вы никогда не запускали Звук Nintendo 3DS (Nintendo 3DS Sound) ранее и видите советы по использованию приложения, пролистайте все сообщения птички, затем закройте приложение и снова запустите его
  + В этой ситуации, при запуске Soundhax сразу, без закрытия, птичка будет появляться при каждом запуске приложения, до тех пор, пока вы не выполните этот пункт
1. Перейдите в `/SDCARD`, затем начните воспроизведение "<3 nedwill 2016"
  + Может потребоваться несколько попыток
  + При зависании отключите питание консоли, зажав кнопку питания, и попробуйте снова
  + Если вы видите красный экран, убедитесь что вы скопировали _содержимое_ папки `STARTer` в корень вашей SD-карты

    ![]({{ base_path }}/images/screenshots/soundhax-launch.png)
	{: .text-center}
    {: .notice--info}

1. Консоль должна загрузиться в HOMEbrew Launcher

    ![]({{ base_path }}/images/screenshots/HOMEbrew-launcher.png)
	{: .text-center}
    {: .notice--info}

	___

Следующий шаг: [Установка boot9strap (HOMEbrew Launcher)](installing-boot9strap-HOMEbrew-launcher)
{: .notice--success}

