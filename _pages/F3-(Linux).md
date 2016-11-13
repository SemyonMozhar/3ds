---
title: "F3 (Linux)"
permalink: /f3-(linux).html
---

В этом разделе рассказывается о том, как проверить карту памяти на ошибки под ОС Linux с помощью F3.
{: .notice}

Процесс может занять до нескольких часов, в зависимости от скорости КП и мощности компьютера!
{: .notice--info}

Этот раздел предназначен для пользователей Linux. Если у вас не Linux, воспользуйтесь [H2testw (windows)](h2testw-(windows)) или [F3X (mac)](f3x-(mac)).
{: .notice--info}

#### Что нужно:

* Свежая версия [F3](https://github.com/AltraMayor/f3/archive/v6.0.zip)

#### Что делать:

1. Разархивируйте архив с f3.
2. Перейдите в каталог с f3 командой `cd` из терминала.
3. Запустите компиляцию F3 командой `make`.
4. Вставьте карту памяти в ПК.
5. Примонтируйте карту памяти.
6. Введите команду `./f3write <your sd card mount point>`
7. Подождите окончания проверки. Ниже пример выходных данных программы:

		$ ./f3write /media/michel/6135-3363/
		Free space: 29.71 GB
		Creating file 1.h2w ... OK!
		...
		Creating file 30.h2w ... OK!
		Free space: 0.00 Byte
		Average Writing speed: 4.90 MB/s

8. Введите команду  `./f3read <your sd card mount point>`
7. Подождите окончания проверки. Ниже пример выходных данных программы:

		$ ./f3read /media/michel/6135-3363/
		                  SECTORS      ok/corrupted/changed/overwritten
		Validating file 1.h2w ... 2097152/        0/      0/      0
		...
		Validating file 30.h2w ... 1491904/        0/      0/      0

		  Data OK: 29.71 GB (62309312 sectors)
		Data LOST: 0.00 Byte (0 sectors)
			       Corrupted: 0.00 Byte (0 sectors)
			Slightly changed: 0.00 Byte (0 sectors)
			     Overwritten: 0.00 Byte (0 sectors)
		Average Reading speed: 9.42 MB/s


Если в результате тестирования вы видите `Data LOST: 0.00 Byte (0 sectors)`, ваша карта в порядке. Можете удалить все файлы с расширением `.h2w`.
{: .notice--success}

При любых других выходных данных знайте, что ваша карта повреждена и мы строго рекомендуем ее заменить!
{: .notice--danger}

Вернитесь к [началу](Get-Started).
{: .notice--primary}
