---
title: "Использование SoundHax для запуска Hombrew Launcher"
permalink: /homebrew-launcher-soundhax.html
---

Существует много различных точек входа в Homebrew Launcher.
{: .notice}

SoundHax совместим с версиями прошивки от 9.0.0 до 11.3.0 включительно в регионах EUR, JPN, KOR и USA.
{: .notice--info}

Убедитесь, что Беспроводной режим (Wireless Communication) включен и есть активное интернет-подключение. 
{: .notice--info}

Заметьте, что обновление на картридже позволяет обновить только базовые функции консоли, такие как Системные настройки, меню HOME, и т. п. Приложение Звук Nintendo 3DS и сетевые функции, такие как Перенос системы, Интернет-браузер, Площадь StreetPass Mii или eShop с картриджа не обновляются.
{: .notice--info}

Это означает, что обновление картриджем с версии <9.0.0 сделает невозможным запуск [Soundhax](homebrew-launcher-(soundhax))! Вам понадобится [альтернативный метод](homebrew-launcher-(alternatives)) запуска Homebrew Launcher!
{: .notice--info}

Если версия вашего браузера от 1 до 6 (откройте Системные настройки (System Settings); обратите внимание на нижний правый угол верхнего экрана, на число вида X.X.X-Y, где Y - версия вашего браузера), следует попробовать запустить [HBL используя браузер](https://3ds.customfw.xyz/homebrew-launcher-browser). 
{: .notice--warning}

#### <a name="what_need" />Что понадобится 

* Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
* Последняя версия [SoundHax](http://soundhax.com/) *(для вашего устройства и региона)*
* [otherapp payload](https://smealum.github.io/3ds/#otherapp) *(для вашей версии и региона)*

#### <a name="instructions" />Инструкция

1. Выключите консоль
1. Вставьте SD-карту в компьютер
1. Скопируйте _содержимое_ папки `starter` из архива `starter.zip` в корень вашей SD-карты
1. Скопируйте Soundhax `.m4a` в корень вашей SD-карты
1. Скопируйте otherapp payload в корень вашей SD-карты и переименуйте его в `otherapp.bin`

    <div class="notice--info"><a href="{{ base_path }}/images/screenshots/soundhax-file-layout.png"><div class="screenshot_image"><img src="{{ base_path }}/images/screenshots/soundhax-file-layout-crop.png"></div></a></div>

1. Вставьте SD-карту обратно в консоль
1. Включите консоль
1. Запустите приложение Звук Nintendo 3DS (Nintendo 3DS Sound)

    <div class="notice--info"><a href="{{ base_path }}/images/screenshots/soundhax-welcome.png"><div class="screenshot_image"><img src="{{ base_path }}/images/screenshots/soundhax-welcome-crop.png"></div></a></div>

1. Если вы никогда не запускали Звук Nintendo 3DS (Nintendo 3DS Sound) ранее и видите советы по использованию приложения, пролистайте все сообщения птички, затем закройте приложение и снова запустите его
  + В этой ситуации, при запуске Soundhax сразу, без закрытия, птичка будет появляться при каждом запуске приложения, до тех пор, пока вы не выполните этот пункт
1. Перейдите в `/SDCARD`, затем начните воспроизведение "<3 nedwill 2016"
  + Может потребоваться несколько попыток
  + При зависании отключите питание консоли, зажав кнопку питания, и попробуйте снова
  + Если вы видите красный экран, убедитесь что вы скопировали _содержимое_ папки `starter` в корень вашей SD-карты

    <div class="notice--info"><a href="{{ base_path }}/images/screenshots/soundhax-launch.png"><div class="screenshot_image"><img src="{{ base_path }}/images/screenshots/soundhax-launch-crop.png"></div></a></div>

1. Консоль должна загрузиться в Homebrew Launcher

    <div class="notice--info"><a href="{{ base_path }}/images/screenshots/homebrew-launcher.png"><div class="screenshot_image"><img src="{{ base_path }}/images/screenshots/homebrew-launcher-crop.png"></div></a></div>

___

Следующий шаг: [SafeCtrTransfer (Homebrew Launcher)](safectrtransfer-homebrew-launcher)
{: .notice--primary}