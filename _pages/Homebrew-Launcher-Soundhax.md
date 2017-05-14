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

{% capture notice-1 %}

Заметьте, что обновление на картридже позволяет обновить только базовые функции консоли, такие как Системные настройки, меню HOME, и т. п. Приложение Звук Nintendo 3DS и сетевые функции, такие как Перенос системы, Интернет-браузер, Площадь StreetPass Mii или eShop с картриджа не обновляются.
<br><br>
Это означает, что обновление картриджем с версии, содержащей старое приложение Звук Nintendo 3DS *(<7.0.0 для Old 3DS регионов EUR, JPN, KOR, и USA)*, до версии с новым приложением Звук Nintendo 3DS сделает невозможной работу [Soundhax](homebrew-launcher-(soundhax))! Вам понадобится [альтернативный метод](homebrew-launcher-(alternatives)) запуска Homebrew Launcher!
{% endcapture %}

<div class="notice--warning">{{ notice-1 | markdownify }}</div>

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

    ![]({{ base_path }}/images/screenshots/soundhax-file-layout.png)
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
  + Если вы видите красный экран, убедитесь что вы скопировали _содержимое_ папки `starter` в корень вашей SD-карты

    ![]({{ base_path }}/images/screenshots/soundhax-launch.png)
	{: .text-center}
    {: .notice--info}

1. Консоль должна загрузиться в Homebrew Launcher

    ![]({{ base_path }}/images/screenshots/homebrew-launcher.png)
	{: .text-center}
    {: .notice--info}

	___

Следующий шаг: [SafeCtrTransfer (Homebrew Launcher)](safectrtransfer-homebrew-launcher)
{: .notice--primary}