---
title: "Homebrew Launcher (альтернативные методы запуска)"
permalink: /homebrew-launcher-alternatives.html
author_profile: true
---

{% include toc title="Разделы" %}

Homebrew Launcher имеет множество точек входа, или методов запуска.

**Убедитесь, что у вас есть рабочее активное подключение к интернету.**

Если вы не можете использовать browserhax (см. таблицу ниже), у вас нет одной из этих игр и другой 3DS с доступом к Homebrew Launcher, самый дешевый вариант это купить "Nintendo Selects" версию [Ocarina of Time 3D](https://amzn.to/2fkaKdp) (убедитесь, что покупаете картридж своего региона) и [Powersaves](https://amzn.to/2fb3VY7) (совместим со всеми регионами), затем использовать oot3dhax из таблицы ниже.

Убедитесь, что Беспроводной режим (Wireless Communication) включен, так как udsploit (используется на следующей странице) потребует активный беспроводной модуль для своей работы, и некоторые консоли (New 3DS, New 2DS и Old 2DS) не могут включить Беспроводной режим, находясь в Homebrew Launcher. Достаточно включить Беспроводной режим (Wireless Communication); наличие соединения с точкой доступа не обязательно.

## Что понадобится

* Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
* Свежая версия [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* Свежая версия [boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *(стандартный boot9strap; не `dev-файл`, не `ntr-файл`)*
* Свежая версия [safehax](https://github.com/TiniVi/safehax/releases/latest)
* Свежая версия [udsploit](https://github.com/smealum/udsploit/releases/latest)
* Свежая версия [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(`.7z`-архив)*


## Инструкция

1. Выключите консоль
1. Вставьте SD-карту в компьютер
1. Скопируйте _содержимое_ `starter.zip` в корень вашей SD-карты
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

## Альтернативные точки входа

1. Используйте одну из следующих точек входа для запуска Homebrew launcher

	| <sub> | <sub>Что понадобится | <sub>Издания | <sub>Устройства | <sub>Регионы | <sub>Версии игры | <sub>Версии прошивки |
	|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
    | <sub>[browserhax](https://yls8.mtheall.com/3dsbrowserhax.php) | <sub>Ничего | <sub>Предустановленный браузер | <sub>New, Old, 2DS | <sub>EUR, JPN, USA | <sub>All | <sub>от 9.0.0-2 до 11.0.0-33 включительно |
	| <sub>[oot3dhax](https://github.com/yellows8/oot3dhax) | <sub>[*Ocarina of Time 3D*](https://amzn.to/2fkaKdp), <br> Powersaves или другая 3DS с доступом к Homebrew Launcher | <sub>Картридж | <sub>New, Old, 2DS | <sub>EUR, JPN, USA | <sub>Все | <sub>от 9.0.0-X до 11.5.0-X включительно |
	| <sub>[smashbroshax](https://gbatemp.net/threads/397194/) | <sub>[*Super Smash Bros*](https://amzn.to/2ftGA72) | <sub>Картридж, eShop | <sub>New  | <sub>EUR, JPN, USA | <sub><1.1.3, <br> Картриджи с "amiibo" на обложке идут с версией 1.1.4 | <sub>от 9.0.0-X до 11.3.0-X включительно |
	| <sub>[supermysterychunkhax](https://smd.salthax.org/) | <sub>[*Pokemon Super Mystery Dungeon*](https://amzn.to/2ebxZ75), <br> Другая 3DS с доступом к Homebrew Launcher | <sub>Картридж | <sub>New, Old, 2DS | <sub>EUR, JPN, USA | <sub>Все | <sub>9.9.0-X (USA/JPN) / от 10.2.0-X (EUR) до 11.0.0-X (EUR) включительно |
	| <sub>[freakyhax](http://plutooo.github.io/freakyhax/) | <sub>[*Freakyforms Deluxe*](https://amzn.to/2f6eHO7) | <sub>eShop, Картридж | <sub>New, Old, 2DS | <sub>EUR, JPN, USA | <sub>Все | <sub>от 9.0.0-X до 11.3.0-X включительно |
	| <sub>[basehaxx](http://mrnbayoh.github.io/basehaxx/) | <sub>*Pokemon [Omega Ruby](https://amzn.to/2eRILNQ)/[Alpha Sapphire](https://amzn.to/2ebGrmN)*, <br> Другая 3DS с доступом к Homebrew Launcher | <sub>Картридж | <sub>New, Old, 2DS | <sub>EUR, JPN, USA | <sub>1.0, 1.4 | <sub>от 9.0.0-X до 11.3.0-X включительно |
	| <sub>[BASICSploit](https://mrnbayoh.github.io/basicsploit/) | <sub>[*SmileBASIC*](https://www.nintendo.com/games/detail/eYURHNjVdfyrnA3OJGfmlMYIrJUzgOcv) | <sub>eShop | <sub>New, Old, 2DS | <sub>USA | <sub>3.2.1 | <sub>от 9.0.0-X до 11.0.0-X включительно |
	| <sub>[smilehax](https://plutooo.github.io/smilehax/) | <sub>[*SmileBASIC*](https://www.nintendo.com/games/detail/eYURHNjVdfyrnA3OJGfmlMYIrJUzgOcv) | <sub>eShop | <sub>New, Old, 2DS | <sub>JPN, USA | <sub>3.3.1 | <sub>от 9.0.0-X до 11.0.0-X включительно |
	| <sub>[stickerhax](https://github.com/yellows8/stickerhax) | <sub>[*Paper Mario: Sticker Star*](https://amzn.to/2f6aDx8), <br> Другая 3DS с доступом к Homebrew Launcher | <sub>eShop, Картридж | <sub>New, Old, 2DS | <sub>EUR, JPN, KOR, USA | <sub>Все | <sub>от 9.0.0-X до 11.3.0-X включительно |
	| <sub>[Ninjhax 2](http://smealum.github.io/ninjhax2/) | <sub>[*Cubic Ninja*](https://amzn.to/2eRI1by) | <sub>eShop, Картридж | <sub>New, Old, 2DS | <sub>EUR, JPN, USA | <sub>Все | <sub>от 9.0.0-X до 11.5.0-X включительно |
	| <sub>[GenHax](https://github.com/svanheulen/genhax_proxy_installer) | <sub>[*Monster Hunter X*](http://amzn.to/2gsk6Tk) | <sub>eShop | <sub>New | <sub>JPN | <sub>Все | <sub>от 9.9.0-X до 11.2.0-X включительно |
    {: .notice--info}
	
___

Следующий шаг: [Установка boot9strap](installing-boot9strap-homebrew-launcher)
{: .notice--success}

