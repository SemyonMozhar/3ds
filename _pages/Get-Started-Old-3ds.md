---
title: "Начнем (Old 3DS)"
permalink: /get-started-old-3ds.html
---

Выберите подходящую для вашей версии страницу из таблицы ниже.
{: .notice--primary}

**НЕ ОБНОВЛЯЙТЕСЬ до самой свежей прошивки 11.4.0, если хотите прошить приставку.**
{: .notice--danger}

{% capture notice-1 %}
Два последних столбца относятся к последнему числу, указанному в версии прошивки вашего устройства (которое обозначает версию установленного браузера в системе). Если версия оканчивается на -0, значит, у вас отсутствует браузер, любое другое число больше 0 говорит о том, что браузер установлен.
<br><br>
Столбцы "С" и "По" обозначают границы диапазона. Это означает, к примеру, что диапазон "с 9.0.0 по 9.2.0" включает в себя 9.0.0, 9.1.0 и 9.2.0.
<br><br>
Например, если у вас версия прошивки "5.0.0-0E", необходимо выбрать ячейку на пересечении колонки "Без браузера" и ряда "С 5.0.0 по 5.1.0" так как версия системы находится в этом диапазоне и в системе не установлен браузер.
{% endcapture %}

<div class="notice--info">{{ notice-1 | markdownify }}</div>

Для всех версий вы также можете выполнить [обновление картриджем](cart-update) до более высокой версии из той же колонки, но вам понадобится [альтернативный метод](homebrew-launcher-alternatives) запуска homebrew launcher, поскольку Soundhax не будет работать.
{: .notice--warning}

Если вы обновились с помощью игрового картриджа, содержащего версию 9.9.0 или выше *(то есть ваша версия сейчас 9.9.0 или выше, однако версия браузера -25 или ниже, например - 10.2.0-24)*, браузер был удалён из системы и в этом случае следует воспользоваться колонкой "Без браузера".
{: .notice--warning}

Версия программного обеспечения вашего устройства отображается в правом нижнем углу верхнего экрана в приложении Системные настройки (System settings).
{: .notice--success}

<div class="notice--info"><center><a href="{{ base_path }}/images/screenshots/system-version.png"><div class="screenshot_image"><img src="{{ base_path }}/images/screenshots/system-version.png"></div></a></center></div>

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
      <td style="text-align: center; font-weight: bold;">1.1.0</td>
      <td style="text-align: center; font-weight: bold;" colspan="2"><a href="cart-update">Обновление картриджем</a></td>
    </tr>
    <tr>
      <td style="text-align: center; font-weight: bold;">2.1.0</td>
      <td style="text-align: center; font-weight: bold;">2.1.0</td>
      <td style="text-align: center; font-weight: bold;"><a href="cart-update">Обновление картриджем</a></td>
      <td style="text-align: center; font-weight: bold;"><a href="installing-arm9loaderhax">Установка arm9loaderhax</a></td>
    </tr>
    <tr>
      <td style="text-align: center; font-weight: bold;">2.2.0</td>
      <td style="text-align: center; font-weight: bold;">3.1.0</td>
      <td style="text-align: center; font-weight: bold;" colspan="2"><a href="cart-update">Обновление картриджем</a></td>
    </tr>
    <tr>
      <td style="text-align: center; font-weight: bold;">4.0.0</td>
      <td style="text-align: center; font-weight: bold;">4.5.0</td>
      <td style="text-align: center; font-weight: bold;"><a href="safectrtransfer-mset">SafeCTRTransfer (MSET)</a></td>
      <td style="text-align: center; font-weight: bold;"><a href="safectrtransfer-browser">SafeCTRTransfer (Используя браузер)</a></td>
    </tr>
    <tr>
      <td style="text-align: center; font-weight: bold;">5.0.0</td>
      <td style="text-align: center; font-weight: bold;">5.1.0</td>
      <td style="text-align: center; font-weight: bold;"><a href="cart-update">Обновление картриджем</a></td>
      <td style="text-align: center; font-weight: bold;"><a href="safectrtransfer-browser">SafeCTRTransfer (Используя браузер)</a></td>
    </tr>
    <tr>
      <td style="text-align: center; font-weight: bold;">6.0.0</td>
      <td style="text-align: center; font-weight: bold;">6.3.0</td>
      <td style="text-align: center; font-weight: bold;"><a href="safectrtransfer-mset">SafeCTRTransfer (MSET)</a></td>
      <td style="text-align: center; font-weight: bold;"><a href="safectrtransfer-browser">SafeCTRTransfer (Используя браузер)</a></td>
    </tr>
    <tr>
      <td style="text-align: center; font-weight: bold;">7.0.0</td>
      <td style="text-align: center; font-weight: bold;">8.1.0</td>
      <td style="text-align: center; font-weight: bold;"><a href="cart-update">Обновление картриджем</a></td>
      <td style="text-align: center; font-weight: bold;"><a href="safectrtransfer-browser">SafeCTRTransfer (Используя браузер)</a></td>
    </tr>
    <tr>
      <td style="text-align: center; font-weight: bold;">9.0.0</td>
      <td style="text-align: center; font-weight: bold;">11.3.0</td>
      <td style="text-align: center; font-weight: bold;"><a href="homebrew-launcher-alternatives">Homebrew Launcher<br>(альтернативные способы запуска)</a></td>
      <td style="text-align: center; font-weight: bold;"><a href="homebrew-launcher-soundhax">Homebrew Launcher (SoundHax)</a></td>
    </tr>
    <tr>
      <td style="text-align: center; font-weight: bold;">11.4.0</td>
      <td style="text-align: center; font-weight: bold;">11.4.0</td>
      <td style="text-align: center; font-weight: bold;" colspan="2">Взлом невозможен</td>
    </tr>
  </tbody>
</table>