---
title: "Включение русского языка в играх на приставке не европейского региона"
permalink: lumalocales.html
author_profile: true
---
{% include toc title="Разделы" %}

Этот раздел полезен только в том случае, если у вас европейская американская приставка, но вы хотоите поиграть в нинтендовские игры на русском. Дело в том, что по-умолчанию язык в таких играх выставляется с огладкой на язык системы, а так как в американской приставке нет возможности выставить русский язык интерфейса, приходится пользоваться таким хаком.

## Что понадобится

Если вы купили приставку у меня (в [VK](https://vk.com/market-125012133) или на [OLX](https://www.olx.ua/list/user/1nlHd/)), то у вас уже b9d со всеми необходимыми программами. Ищите их в папке System
{: .notice--info}

* Установленный и рабочий [b9s](a9lh-to-b9s)
* Установленный и рабочий [FBI](fbi)
* Установленный и рабочий [witcher](https://github.com/Possum/lumalocaleswitcher/releases) *(`.cia`-файл)* (NIGHTLY для luma3ds 7.0 и выше)

## Инструкция

#### Включение патчей в настройках luma3ds

Если вы купили приставку у меня (в [VK](https://vk.com/market-125012133) или на [OLX](https://www.olx.ua/list/user/1nlHd/)), то у вас уже активирована эта настройка
{: .notice--info}

1. Выключите приставку
1. Включите приставку, удерживая (SELECT)
1. Нажимая (A) выберите **"Enable game patching"**
1. Нажмите (START), чтобы сохранить настройки и перезагрузить приставку


#### lumalocaleswitcher

1. Установите `lumalocaleswitcher` через FBI (как это сделать описано [здесь](games))
	+ Если вы купили приставку у меня (в [VK](https://vk.com/market-125012133) или на [OLX](https://www.olx.ua/list/user/1nlHd/)), то программа уже установлена и находится в папке "System" 
1. Запустите `lumalocaleswitcher` из меню Home
1. Перейдите в пункт меню "Choose Locales Directory ""
1. Выберите `/luma/locales/titles/%s/locale.txt` и нажмите (A) для подтверждения выбора, а затем еще раз (A), чтобы вернуться на главный экран программы
1. Перейдите в меню "Titles "
1. Выберите игру, язык которой вы хотите поменять
1. Выберите пункт "Change Region", затем "EUR"
1. Выберите пункт "Change Language", затем "RU"
1. Нажмите два раза (B), чтобы вернуться в главное меню программы 
1. Нажмите (START), чтобы закрыть программу

После этого вы сможете играть на русском языке в игры от Nintendo даже на консоли не европейского региона
{: .notice--success}

Для каждой отдельной игры эту манипуляцию следует выполнить всего один раз
{: .notice--success}

