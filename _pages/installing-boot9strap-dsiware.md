---
title: "Установка boot9strap (DSiWare)" #
lang: ru
permalink: installing-boot9strap-dsiware.html
---

Существует два различных способа установки boot9strap с помощью DSiWare на 11.5.0.
{: .notice--info}

Один из этих методов работает только с четырьмя конкретными играми, которые больше не продаются в eShop, в то время как другой работает с довольно большим количеством игр, которые по-прежнему продаются в eShop.
{: .notice--info}

Оба этих метода требуют два устройства. На одной 3DS (или 2DS) должна быть установлена кастомная прошивка (такая как boot9strap или arm9loaderhax) и в дальнейшем она будет называется *исходная 3DS*, в то время как другая 3DS (или 2DS) должная быть на не взломаной прошивке 11.5.0 и в дальнейшем она будет называться *целевая 3DS*.
{: .notice--info}

Если на вашей **целевой 3DS** установлена прошивка 11.4 - обновите ее до 11.5 через системные настройки (Системные настройки (System Settings), затем “Прочие настройки” (Other Settings), затем листайте вправо до конца и выберите пункт “Обновление” (System Update))
{: .notice--warning}

Обе приставки ДОЛЖНЫ быть одного региона.
{: .notice--warning}

Оба этих метода подразумевают что 3DS используют кастомную прошивку boot9strap или arm9loaderhax и были взломаны по настоящему руководство. Хотя это можно сделать и другими методами используя другие пользовательские прошивки, это выходит за рамки данного руководства.
{: .notice--info}

Оба этих метода используют "FIRM partitions known-plaintext" exploit описаный [здесь](https://www.3dbrew.org/wiki/3DS_System_Flaws) (англ.), и уязвимость, позволяющую DSiWare тайтлам читать и записывать что угодно в зашифрованном NAND.
{: .notice--info}

{% capture notice-4 %}
Оба этих метода требуют от вас произвести Передачу данных системы ([System Transfer](http://en-americas-support.nintendo.com/app/answers/detail/a_id/13996/)) из приставки с кастомной прошивкой на приставку со стоковой прошивкой. Перенос данных будет работать *только* в одном из следующих направлений:    

  + New 3DS или New 2DS -> New 3DS или New 2DS    
  + Old 3DS или Old 2DS -> Old 3DS или Old 2DS    
  + Old 3DS или Old 2DS -> New 3DS или New 2DS    
  
{% endcapture %}

<div class="notice--warning">{{ notice-4 | markdownify }}</div>

В обоих этих методах NNID из исходной 3DS будет находится в целевой 3DS до тех пор, пока вы не перенесете его назад в исходную консоль, либо не позвоните в Nintendo! (подробную информацию можно найти в инструкциях)
{: .notice--danger}

Перенос системы можно делать лишь раз в неделю для одного NNID.
{: .notice--danger}

___

{% capture notice-1 %}

[Установка boot9strap (Инъекция в сохранения DSiWare)](installing-boot9strap-dsiware-save-injection)
<br><br>
Этот метод требует, чтобы на исходной 3DS была установлена легальная копия одной из следующих игр:
    
    + "Fieldrunners"
    + "Legends of Exidia"
    + "Guitar Rock Tour"
    + "The Legend of Zelda: Four Swords"
    
Пиратские копии игры *не* будут работать, как и все игры нелегально скаченные из eShop.

{% endcapture %}

<div class="notice--success">{{ notice-1 | markdownify }}</div>

{% capture notice-1 %}

[Установка boot9strap (Инъекция в игры DSiWare)](installing-boot9strap-dsiware-game-injection)
<br><br>
Этот метод требует, чтобы на исходной 3DS была установлена легальная копия игры, присутствующая в списке на странице [Установка boot9strap (Список уязвимых игр DSiWare)](installing-boot9strap-dsiware-game-injection-list).
<br><br>
Пиратская копия игры *не* будет работать.

{% endcapture %}

<div class="notice--success">{{ notice-1 | markdownify }}</div>

