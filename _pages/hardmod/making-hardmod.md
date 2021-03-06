---
title: "Хардмод" #
lang: ru
permalink: making-hardmod.html
author_profile: true
---
{% include toc title="Разделы" %}

Это руководство для тех, кто хочет выполнить хардмод и снять дамп NAND с любых приставок семейства Nintendo 3DS. Руководство по внедрению bootstrap в уже снятый дамп находится [здесь](installing-boot9strap-hardmod)
{: .notice--info}

Это руководство предназначено в первую очередь для тех, кто хочет интегрировать b9s в прошивку приставки и получить возможность выполнить бэкап, если что-то пойдет не так. **Все существующие модели 3DS поддаются хардмоду.** Для краткости, я буду называть системы просто «3DS», говоря обо всех моделях в целом.
{: .notice--info}

{% capture notice-1 %}   
NAND - это вид используемой флеш памяти, находящейся в 3DS, которая служит для хранения такой важной информации, как прошивка. Прошивка запускается из NAND с помощью загрузчика, во время включения консоли. Мы можем сделать дамп NAND без участия загрузчика, считав содержимое чипа памяти, припаявшись к нему напрямую. Это и называется хардмодом. 
<br><br>
Использование хардмода, кроме всего, позволит вернуть приставку к жизни едва ли не из любого состояния, поэтому следует сохранить ваш NAND файл в безопасное место после дампа, например в облачное хранилище. Вы никогда не знаете, когда этот файл вам может пригодится и если вы когда-нибудь брикните консоль и у вас не будет NAND файла, вы практически обречены. Я предупредил.
<br><br>
Важно понимать, что дамп NAND снятый через хардмод и дамп, снятый через ПО непосредственно через приставку взаимозаменяемы. То есть вы можете восстановить дамп хардмода через GodMode9 и наоборот - залить дамп, снятый через GM9 в приставку через хардмод. 
<br><br>
Важно уметь обращаться с паяльником для того, чтобы успешно завершить руководство. Целью данного руководства не является обучение вас работе с паяльником. Поэтому, если вы не знаете как паять - обратитесь к специалисту, либо потренируйтесь на чем-то не столь дорогом. 
<br><br>
За все ваши действия вы сами несете ответственность, поэтому не жалуйтесь, если что-то пошло не так и вы получили бесполезный кусок пластика вместо дорогой приставки.
{% endcapture %}

<div class="notice--info">{{ notice-1 | markdownify }}</div>

Мы рассмотрим лишь реализацию временного хардмода. То есть после успешного снятия и модификации дампа NAND все провода будут отпаиваться от материнской платы. Методы перманентного хардмода ищите в других руководствах. 
{: .notice--info}

## Выберите консоль

<table>
  <thead>
    <tr>
      <th style="text-align: center; font-weight: bold;">Old 3DS</th>
      <th style="text-align: center; font-weight: bold;">New 3DS</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center; font-weight: bold;"><a href="making-hardmod-old3ds"><img src="/images/old3ds.png"></a></td>
      <td style="text-align: center; font-weight: bold;"><a href="making-hardmod-new3ds"><img src="/images/new3ds.png"></a></td>
    </tr>
  </tbody>
  <thead>
    <tr>
      <td style="text-align: center; font-weight: bold;">Old 3DS XL</td>
      <td style="text-align: center; font-weight: bold;">New 3DS XL</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center; font-weight: bold;"><a href="making-hardmod-old3dsxl"><img src="/images/old3dsxl.png"></a></td>
      <td style="text-align: center; font-weight: bold;"><a href="making-hardmod-new3dsxl"><img src="/images/new3dsxl.png"></a></td>
    </tr>
  </tbody>
  <thead>
    <tr>
      <td style="text-align: center; font-weight: bold;">2DS</td>
      <td style="text-align: center; font-weight: bold;">New 2DS XL</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center; font-weight: bold;"><a href="making-hardmod-2ds"><img src="/images/2ds.png"></a></td>
      <td style="text-align: center; font-weight: bold;"><a href="making-hardmod-new2dsxl"><img src="/images/new2dsxl.png"></a></td>
    </tr>
  </tbody>
</table>
