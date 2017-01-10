---
title: "Начнем (Old 3DS)"
permalink: /get-started-(old-3ds).html
---

Выберите в таблице пункт, соответствующий вашей версии приставки.
{: .notice--primary}

{% capture notice-1 %}
Первые две колонки говорят о том в каких промежутках должна находится версия вашей прошивки. Например, "от 9.0.0 до 11.1.0" говорит о том, что к этой строке относятся прошивки версии 9.0.0, 9.1.0, и 9.2.0 итд. 

В общем виде, версия прошивки выглядит так: ХХ.Х.Х-УУZ, где УУ - символы после знака "-" будут указывать на версию установленного браузера, а Z на регион. Если после знака "-" стоит "0", то в вашей системе нет браузера, значит в таблице ваша третья колонка, если число после дефиса больше нуля, то браузер есть и вам следует смотреть на четвертую колонку.

Например, если в настройках указана прошивка "5.0.0-0U", то ваша колонка номер три, поскольку в прошивке нет браузера; и ряд номер 5, поскольку именно в этом ряду находятся прошивки в промежутке от 5.0.0 до 5.1.0.
{% endcapture %}

<div class="notice--info">{{ notice-1 | markdownify }}</div>

Поднять прошивку можно с помощью [картриджа](cart-update). Рекомендую поднимать сразу до 9.2.
{: .notice--warning}

Какая бы версия системного ПО у вас ни стояла, вы можете просто обновиться до самой последней и продолжить выполнять инструкцию.

Если вы обновляетесь с помощью картриджа, содержащего прошивку 9.9.0, или выше *(то есть, если версия 9.9.0, или выше, но версия браузера -25, или ниже, например 10.2.0-24)*, то браузер из прошивки будет удален. Соответственно, нужно будет использовать колонку "Браузера нет".
{: .notice--warning}

Узнать версию прошивки можно в Системных настройках в нижнем правом углу верхнего экрана. 
{: .notice--success}

<table>
  <thead>
    <tr>
      <th style="text-align: center">От</th>
      <th style="text-align: center">До</th>
      <th style="text-align: center">Браузера нет</th>
      <th style="text-align: center">Браузер есть</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center">1.0.0</td>
      <td style="text-align: center">1.1.0</td>
      <td style="text-align: center" colspan="2"><a href="cart-update">Обновление картриджем</a></td>
    </tr>
    <tr>
      <td style="text-align: center">2.1.0</td>
      <td style="text-align: center">2.1.0</td>
      <td style="text-align: center"><a href="cart-update">Обновление картриджем</a></td>
      <td style="text-align: center"><a href="installing-arm9loaderhax">Установка arm9loaderhax</a></td>
    </tr>
    <tr>
      <td style="text-align: center">2.2.0</td>
      <td style="text-align: center">3.1.0</td>
      <td style="text-align: center" colspan="2"><a href="cart-update">Обновление картриджем</a></td>
    </tr>
    <tr>
      <td style="text-align: center">4.0.0</td>
      <td style="text-align: center">4.5.0</td>
      <td style="text-align: center"><a href="decrypt9-(mset)">Decrypt9 (MSET)</a></td>
      <td style="text-align: center"><a href="decrypt9-(browser)">Decrypt9 (используя браузер)</a></td>
    </tr>
    <tr>
      <td style="text-align: center">5.0.0</td>
      <td style="text-align: center">5.1.0</td>
      <td style="text-align: center"><a href="cart-update">Обновление картриджем</a></td>
      <td style="text-align: center"><a href="decrypt9-(browser)">Decrypt9 (используя браузер)</a></td>
    </tr>
    <tr>
      <td style="text-align: center">6.0.0</td>
      <td style="text-align: center">6.3.0</td>
      <td style="text-align: center"><a href="decrypt9-(mset)">Decrypt9 (MSET)</a></td>
      <td style="text-align: center"><a href="decrypt9-(browser)">Decrypt9 (используя браузер)</a></td>
    </tr>
    <tr>
      <td style="text-align: center">7.0.0</td>
      <td style="text-align: center">8.1.0</td>
      <td style="text-align: center"><a href="cart-update">Обновление картриджем</a></td>
      <td style="text-align: center"><a href="decrypt9-(browser)">Decrypt9 (используя браузер)</a></td>
    </tr>
    <tr>
      <td style="text-align: center">9.0.0</td>
      <td style="text-align: center">11.2.0</td>
      <td style="text-align: center" colspan="2"><a href="homebrew-launcher-(soundhax)">Homebrew Launcher (SoundHax)</a></td>
    </tr>
  </tbody>
</table>

