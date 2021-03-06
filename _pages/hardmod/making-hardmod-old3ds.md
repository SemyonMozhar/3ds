---
title: "Пайка хардмода в Old 3DS" #
lang: ru
permalink: making-hardmod-old3ds.html
author_profile: true
---
{% include toc title="Разделы" %}

Это руководство для тех, кто хочет выполнить хардмод и снять дамп NAND с 2DS. Руководство по внедрению bootstrap в уже снятый дамп находится [здесь](installing-boot9strap-hardmod)
{: .notice--info}

{% capture notice-1 %}   
Для хардмода годятся далеко не все картридеры! Список совместимых и протестированных приведен ниже. Однако и здесь есть подводные камни. Например, на некоторых NAND-чипах производства TOSHIBA будут работать только кардридеры, совместимые с eMMC 5.1. Зачастую ридеры с поддержкой USB 3.0 и microsd больше, чем 128 Гб будут без проблем работать с eMMC 5.1. 
* [Anker® USB 3.0 (68UNMCRD-B2U): Realtek RTS5306](https://www.amazon.com/gp/product/B006T9B6R2/ref=oh_aui_detailpage_o00_s00?ie=UTF8&psc=1	)
* [TekRepublic TUC-300: Realtek RTS5307](https://www.amazon.com/Tek-Republic-TUC-300-Portable-Reader/dp/B00D50UNRM/ref=sr_1_fkmr0_1?s=electronics&ie=UTF8&qid=1423979888&sr=1-1-fkmr0&keywords=TekRepublic+TUC-300)
* [SanDisk SDDR-121-A11M: GL827](https://www.amazon.com/SanDisk-SDDR-121-A11M-MobileMate-Memory-Reader/dp/B000WR3Z3A/ref=sr_1_3?ie=UTF8&qid=1426031853&sr=8-3&keywords=microsd+card+reader)
* [Transcend P8 TS-RDP8K: ALCOR AU6476](https://www.amazon.com/Transcend-Flash-Memory-Reader-TS-RDP8K/dp/B001NS0OZ4)
* [Anker® USB 3.0 4-Slot card Reader(A7612): RT5301](http://www.amazon.com/gp/product/B006T9B6R2/ref=ox_sc_act_title_1?ie=UTF8&psc=1&smid=A294P4X9EWVXLJ)
<br><br>
В России и Украине проще всего достать [Transcend P8 TS-RDP8K](https://www.amazon.com/Transcend-Flash-Memory-Reader-TS-RDP8K/dp/B001NS0OZ4), но eMMC 5.1 он не поддерживает. Самый универсальный вариант - [Anker® USB 3.0 (68UNMCRD-B2U)](https://www.amazon.com/gp/product/B006T9B6R2/ref=oh_aui_detailpage_o00_s00?ie=UTF8&psc=1), но кроме как через Amazon его не достать.
{% endcapture %}

<div class="notice--warning">{{ notice-1 | markdownify }}</div>

## Что понадобится

* Паяльник: один с тонким наконечником
* Пайка: я использую паяльник с флюсосодержащим припоем с соотношением олова к свинцу 60/40. Не используйте припой, содержащий кислотный флюс, так как это вызывает коррозию материнской платы и может все повредить
* Паяльный флюс
* Крестовая отвертка [Phillips #000](https://ru.ifixit.com/Store/Tools/Phillips-000-Screwdriver/IF145-030-3) или [JIS #000](https://ru.ifixit.com/Store/Tools/JIS-Driver-Set/IF145-115-1): рекомендуется отвертка [Phillips #000](https://ru.ifixit.com/Store/Tools/Phillips-000-Screwdriver/IF145-030-3) или [JIS #000](https://ru.ifixit.com/Store/Tools/JIS-Driver-Set/IF145-115-1). Вы также можете использовать [Phillips #00](https://ru.ifixit.com/Store/Tools/Phillips-00-Screwdriver/IF145-006-3) или [JIS #00](https://ru.ifixit.com/Store/Tools/JIS-Driver-Set/IF145-115-1), но рискуете сломать винты, если не будете осторожны<br>
Я использую вот такой набор: [Kalaidun  25 in 1](https://ru.aliexpress.com/item/Screwdriver-Set-25-in-1-Torx-Screwdriver-Repair-Tool-Set-For-iPhone-Cellphone-Tablet-PC-Worldwide/32696703618.html?ws_ab_test=searchweb0_0,searchweb201602_3_10152_10065_10151_10068_5400011_5430020_5410020_10307_10303_10137_10060_10155_10154_10056_10055_10054_10059_100031_10099_10103_10102_10052_10053_10142_10107_10050_10051_10170_5380020_5390020_10084_10083_10119_5370020_10080_10082_10081_10110_10111_10112_10113_10114_10311_10312_10313_10314_10315_10078_10079_10073_10120_5420011_10125-10102_10120,searchweb201603_5,ppcSwitch_5&btsid=0c9deb2d-e096-48cc-86fe-3162777cb23d&algo_expid=809042af-9533-4303-8d8c-9e18df48c770-0&algo_pvid=809042af-9533-4303-8d8c-9e18df48c770&transAbTest=ae803_2)
* Программа [win32diskimager](https://sourceforge.net/projects/win32diskimager/) на вашем компьютере
* Программа [3DS NAND Checker](https://gbatemp.net/threads/2ds-3ds-nand-checker.439170/)
* Провода: Я лично рекомендую вам использовать [эти](https://ru.aliexpress.com/item/10-Meters-26AWG-UL1007-Electronic-Wire-1-3mm-PVC-26-AWG-Electronic-Cable/32776859051.html?aff_platform=aaf&cpt=1501878660749&sk=eub6yrrBy&aff_trace_key=69239865cbdd4c2aab6f7036b8ec20dc-1501878660749-04055-eub6yrrBy) провода, но если вы не хотите их покупать, можете просто использовать провода, вырванные из наушников, а затем купить отдельные разъемы для подключения. Все, что вам нужно сделать, - припаять четыре провода на охватываемый конец разъема
* Переходник с SD-карты на microSD
* microSD картридер из списка выше
* Пинцет для работы со шлейфами приставки

Лично мной протестированы [Transcend P8 TS-RDP8K](https://www.amazon.com/Transcend-Flash-Memory-Reader-TS-RDP8K/dp/B001NS0OZ4), и [Anker® USB 3.0 (68UNMCRD-B2U)](https://www.amazon.com/gp/product/B006T9B6R2/ref=oh_aui_detailpage_o00_s00?ie=UTF8&psc=1). Первый прекрасно себя показал на eMMC версии ниже, чем 5.1 (все Old3DS и OLD3DS XL), второй же является универсальным решением и полностью совместим с eMMC 5.1 и ниже. С его помощью можно прошить любую ревизию 3DS.

## Инструкция

#### Часть I - Подготавливаем SD-переходник

1. Возьмите любой ненужный *переходник с SD-карты на microSD*
1. Аккуратно раскройте его ножом и отделите лицевую часть от задней

	Либо можете вырезать аккуратное отверстие на лицевой части, чтобы добраться до ножек переходника
	{: .notice--info}

1. Припаяйте провода к ножкам, согласно схеме

	Используйте провода разного цвета, чтобы не запутаться какой провод какому контакте соответствует. Запишите эту информацию, либо отметьте на самом проводе. 
	{: .notice--info}
	
	Можете откусить лишние ножки, чтобы они не мешали вам паять и не замыкали. 
	{: .notice--info}

    ![]({{ base_path }}/images/sd2hm.png)
	{: .text-center}
    {: .notice--info}

1. Рекомендую оставлять не более 15см провода. 

#### Часть II - Разбираем консоль

1.	Отключите все периферийные устройства (зарядку, SD-карту, прочее) от консоли и положите их в безопасное место.
1.	Переверните консоль и открутите два винта, что крепят заднюю крышку. 

	**Примечание:** Винты не откручиваются полностью, они остаются прикрепленными к задней крышке. Открепите заднюю крышку, потянув её наверх.
	{: .notice--info}

    ![]({{ base_path }}/images/ifixit/3ds/1.png)
	{: .text-center}
    {: .notice--info}
	
1.	После этого вам необходимо вытащить батарею из консоли

    ![]({{ base_path }}/images/ifixit/3ds/2.png)
	{: .text-center}
    {: .notice--info}

1.	Теперь открутите винты, которые удерживают заднюю панель и положите их в безопасное место.

    ![]({{ base_path }}/images/ifixit/3ds/3.png)
	{: .text-center}
    {: .notice--info}

1.	Когда вы открутите все винты и начнете открывать крышку, вы увидите печатную плату (PCB), **НЕ ПРИМЕНЯЙТЕ СИЛУ ДЛЯ ОТКРЫТИЯ ПАНЕЛИ**. Под крышкой находятся два шлейфа от боковых кнопок. Аккуратно отсоедините их от материнской платы и продолжайте разбор.

    ![]({{ base_path }}/images/ifixit/3ds/4.png)
	{: .text-center}
    {: .notice--info}
	
1. Аккуратно отсоедините WiFi- и ИК-модуль. 

    ![]({{ base_path }}/images/ifixit/3ds/5.png)
	{: .text-center}
    {: .notice--info}
	
1. Открутите винты, удерживающие аналоговый джойстик и плату картридера. Осторожно открепите защелку, которая удерживает шлейф аналога и аккуратно отложите его в сторону. Будьте предельно осторожны - защелки очень хрупкие! Отсоедините кардридер от платы. Будьте внимательны, он держится при помощи двустороннего скотча. Возможно, понадобится поддеть его канцелярским ножом. 

    ![]({{ base_path }}/images/ifixit/3ds/6.png)
	{: .text-center}
    {: .notice--info}

1. Открутите оставшиеся винты и аккуратно отстегните отмеченные синим защелки и уберите шлейфы.

    ![]({{ base_path }}/images/ifixit/3ds/7.png)
	{: .text-center}
    {: .notice--info}
	
1. Осоторжно переверните плату.

    ![]({{ base_path }}/images/ifixit/3ds/8.png)
	{: .text-center}
    {: .notice--info}
	
#### Часть III - Впаиваем провода переходника в приставку 
	
{% capture notice-2 %}
Вы будете паять близко к чипу NAND. Припаивать мы будем 4 основных контакта. **DAT0 (Data Zero)**, **CMD** и **CLK (CLOCK)** находятся на нижней части платы. **GND (Ground или заземление)**, мы будем припаивать к металлическому корпусу слота для картриджей или SD-карты, который находится на верхней части материнской платы. Другие DAT-контакты (DAT1, DAT2 и DAT3) вам не потребуются, и в этом гайде вы их не найдете, однако, вы можете припаять провода и к ним, если вам нужна более высокая скорость передачи для записи и чтения NAND'а. Это опциональная операция и в этом гайде не используется, поскольку чип и так дампится достаточно быстро. Выигрыш в пару минут не стоит времени, затраченного на пайку дополнительных контактов.

![]({{ base_path }}/images/ifixit/3ds/o3ds_tp.png)
{: .text-center}

{% endcapture %}

<div class="notice--info">{{ notice-2 | markdownify }}</div>

1.	Нанесите флюс на кончик провода и используйте его как кисточку, нанеся флюс на контакты, к которым необходимо припаять.
1.	Начните припаивать 4 провода к каждому из контактов: DAT0, CMD и CLK, а также к GND. Убедитесь, что вы припаяли всё чисто, аккуратно и к нужным точкам.

	Убедитесь, что провода, выходящие из SD-адаптера припаяны к соответствующим точкам, иначе ничего работать не будет. Для пущей надежности прозвоните их мультиметром, или любым другим прибором.
	{: .notice--warning}

1.	Соберите вашу приставку. Можете не закручивать болты, либо закрутить всего несколько. Аккуратно верните все шлейфы на место. Защелки очень хрупкие, поэтому действуйте пинцетом и будьте предельно осторожны! Можете пока не подключать аналоговый джойстик и камеру. 
1. Вставьте батарею в приставку и включите ее, чтобы удостоверится в её работоспособности. На этом этапе приставка все ещё должна работать в обычном режиме.

	Могут возникнуть следующие проблемы: 
	+ **При включении приставки загорается синий диод, раздается щелчок из динамика, затем приставка выключается** - неправильно подключены шлейфы экранов (или одного из них), переподключите их и попробуйте снова
	+ **При включении на экране приставки оба экрана светятся синим** - где-то замыкают провода; проверяйте пайку. 
	+ **Курсор быстро перемещается по экрану ВПРАВО** - это из-за отключенного аналога; игнорируйте

#### Часть IV - Снятие дампа NAND

1. Поставьте отключенную приставку на зарядку. 
1. Вставьте припаянный переходник в кардридер и включите приставку. **КАРТРИДЕР ДОЛЖЕН БЫТЬ ОТКЛЮЧЕН ОТ КОМПЬЮТЕРА!!!**
1. Оба экрана должны светиться синим

    ![]({{ base_path }}/images/ifixit/bsod.jpg)
	{: .text-center}
    {: .notice--info}

1. На этой стадии вы уже можете считывать/записывать NAND. **Не выключайте консоль и подключайте ридер в USB порт вашего компьютера.**
1. На компьютере, кликните правой кнопкой мыши на значок `win32diskimage` и выберите «Запуск от имени администратора». Введите пароль администратора, если требуется, и программа запуститься.
1.	Назовите файл в строке "Image file" `NAND.bin`. Нажмите на кнопку **Read** для дампа NAND на компьютер в файл `NAND.bin`. Процесс может занять несколько минут. Если вы хотите восстановить бэкап NAND на ваше устройство, то нажмите **Write**, и выберите файл вашего бекапа.
1.	Если всё прошло успешно, то дамп NAND появится в директории, которую вы указали. 

Желательно снять несколько копий NAND, чтобы убедиться, что бекап сделан верно. Откройте 3DS NAND Checker и нажмите любую кнопку. Программа должна тут же закрыться и сгенерировать два папки в том же каталоге, которые называются `imgs` и `logs` Перекиньте ВСЕ сделанные вами NAND-файлы в папку `imgs`. Теперь, запустите программу снова и она сравнит размеры и хэши файлов, выведя результат в консоль или в файл лога (который должен появится в папке `logs`). Если они одинаковые, то данный файл можно использовать для инъекции b9s. Если контрольная сумма разная, проверьте пайку и делайте всё по новой.
{: .notice--warning}

___

Следующий шаг: [Установка boot9strap (Hardmod)](installing-boot9strap-hardmod)
{: .notice--success}