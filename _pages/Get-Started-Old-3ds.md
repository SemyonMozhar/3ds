---
title: "Начнем (Old 3DS)"
permalink: /get-started-old-3ds.html
---

Выберите подходящую для вашей версии страницу из таблицы ниже.
{: .notice--primary}

{% capture notice-1 %}
Два последних столбца относятся к последнему числу, указанному в версии прошивки вашего устройства (которое обозначает версию установленного браузера в системе). Если версия оканчивается на -0, значит, у вас отсутствует браузер, любое другое число больше 0 говорит о том, что браузер установлен.
<br><br>
Столбцы "С" и "По" обозначают границы диапазона. Это означает, к примеру, что диапазон "с 9.0.0 по 9.2.0" включает в себя 9.0.0, 9.1.0 и 9.2.0.
<br><br>
Например, если у вас версия прошивки "5.0.0-0E", необходимо выбрать ячейку на пересечении колонки "Без браузера" и ряда "С 5.0.0 по 5.1.0" так как версия системы находится в этом диапазоне и в системе не установлен браузер.
{% endcapture %}

<div class="notice--info">{{ notice-1 | markdownify }}</div>

Любую версию системного ПО можно обновить на более высокую из этой же колонки [с помощью картриджа](cart-update) и после этого продолжать выполнять инструкцию. Поэтому этот вариант не описывается в таблице. 
{: .notice--info}

Находясь на 2.1.0 и имея браузер вы всегда можете установить [a9lh](installing-arm9loaderhax)? а потом обновить его до [b9s](updating-to-boot9strap)
{: .notice--info}

{% capture notice-1 %}

Заметьте, что обновление на картридже позволяет обновить только базовые функции консоли, такие как Системные настройки, меню HOME, и т. п. Приложение Звук Nintendo 3DS и сетевые функции, такие как Перенос системы, Интернет-браузер, Площадь StreetPass Mii или eShop с картриджа не обновляются.
<br><br>
Это означает, что обновление картриджем с версии, содержащей старое приложение Звук Nintendo 3DS *(<7.0.0 для Old 3DS регионов EUR, JPN, KOR, и USA)*, до версии с новым приложением Звук Nintendo 3DS сделает невозможной работу [Soundhax](homebrew-launcher-(soundhax))! Вам понадобится [альтернативный метод](homebrew-launcher-(alternatives)) запуска Homebrew Launcher!
{% endcapture %}

Если вы обновились с помощью игрового картриджа, содержащего версию 9.9.0 или выше *(то есть ваша версия сейчас 9.9.0 или выше, однако версия браузера -25 или ниже, например - 10.2.0-24)*, браузер был удалён из системы и в этом случае следует воспользоваться колонкой "Без браузера".
{: .notice--warning}

Версия программного обеспечения вашего устройства отображается в правом нижнем углу верхнего экрана в приложении Системные настройки (System settings).
{: .notice--success}

Обратите внимание, что новый метод [установки boot9strap через hardmod)](installing-boot9strap-hardmod) работает на *всех устройствах, любого региона и версий*! Включая устройства CHN- и TWN-регионов, которые раньше считались невзлымываемыми!
{: .notice--success}

![]({{ base_path }}/images/screenshots/system-version.png)
{: .text-center}
{: .notice--info}

<table>
  <thead>
    <tr>
      <th style="text-align: center; font-weight: bold;">С</th>
      <th style="text-align: center; font-weight: bold;">По</th>
      <th style="text-align: center; font-weight: bold;">Браузера нет</th>
      <th style="text-align: center; font-weight: bold;">Браузер есть</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center; font-weight: bold;">1.0.0</td>
      <td style="text-align: center; font-weight: bold;">3.1.0</td>
      <td style="text-align: center; font-weight: bold;" colspan="2"><a href="installing-boot9strap-hardmod">Установка boot9strap (Hardmod)</a></td>
    </tr>
    <tr>
      <td style="text-align: center; font-weight: bold;">4.0.0</td>
      <td style="text-align: center; font-weight: bold;">4.5.0</td>
      <td style="text-align: center; font-weight: bold;"><a href="installing-boot9strap-mset">Установка boot9strap (MSET)</a> or <br> <a href="installing-boot9strap-hardmod">Установка boot9strap (Hardmod)</a></td>
      <td style="text-align: center; font-weight: bold;"><a href="installing-boot9strap-browser">Установка boot9strap (Browser)</a> or <br> <a href="installing-boot9strap-hardmod">Установка boot9strap (Hardmod)</a></td>
    </tr>
    <tr>
      <td style="text-align: center; font-weight: bold;">5.0.0</td>
      <td style="text-align: center; font-weight: bold;">5.1.0</td>
      <td style="text-align: center; font-weight: bold;"><a href="installing-boot9strap-hardmod">Установка boot9strap (Hardmod)</a></td>
      <td style="text-align: center; font-weight: bold;"><a href="installing-boot9strap-browser">Установка boot9strap (Browser)</a> or <br> <a href="installing-boot9strap-hardmod">Установка boot9strap (Hardmod)</a></td>
    </tr>
    <tr>
      <td style="text-align: center; font-weight: bold;">6.0.0</td>
      <td style="text-align: center; font-weight: bold;">6.3.0</td>
      <td style="text-align: center; font-weight: bold;"><a href="installing-boot9strap-mset">Установка boot9strap (MSET)</a> or <br> <a href="installing-boot9strap-hardmod">Установка boot9strap (Hardmod)</a></td>
      <td style="text-align: center; font-weight: bold;"><a href="installing-boot9strap-browser">Установка boot9strap (Browser)</a> or <br> <a href="installing-boot9strap-hardmod">Установка boot9strap (Hardmod)</a></td>
    </tr>
    <tr>
      <td style="text-align: center; font-weight: bold;">7.0.0</td>
      <td style="text-align: center; font-weight: bold;">8.1.0</td>
      <td style="text-align: center; font-weight: bold;"><a href="installing-boot9strap-hardmod">Установка boot9strap (Hardmod)</a></td>
      <td style="text-align: center; font-weight: bold;"><a href="installing-boot9strap-browser">Установка boot9strap (Browser)</a> or <br> <a href="installing-boot9strap-hardmod">Установка boot9strap (Hardmod)</a></td>
    </tr>
    <tr>
      <td style="text-align: center; font-weight: bold;">9.0.0</td>
      <td style="text-align: center; font-weight: bold;">11.3.0</td>
      <td style="text-align: center; font-weight: bold;" colspan="2"><a href="homebrew-launcher-soundhax">Homebrew Launcher (Soundhax)</a> or <br> <a href="installing-boot9strap-hardmod">Установка boot9strap (Hardmod)</a></td>
    </tr>
    <tr>
      <td style="text-align: center; font-weight: bold;">11.4.0</td>
      <td style="text-align: center; font-weight: bold;">11.4.0</td>
      <td style="text-align: center; font-weight: bold;" colspan="2"><a href="installing-boot9strap-dsiware">Установка boot9strap (DSiWare)</a> or <br> <a href="installing-boot9strap-hardmod">Установка boot9strap (Hardmod)</a></td>
    </tr>
  </tbody>
</table>
