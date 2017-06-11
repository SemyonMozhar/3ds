---
title: "Обновление Luma3DS"
permalink: /update-luma3ds.html
sidebar:
  nav: "update-luma3ds"
---

#### <a name="what_need" />Что понадобится

* Установленный и рабочий [b9s](updating-b9s) последней версии (*если уже делали, то повторно делать не нужно*)
* Установленный и рабочий [FBI](fbi)
* Свежая версия [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(`.7z`-архив)*
* Свежая версия [Luma3ds Updater](https://github.com/KunoichiZ/lumaupdate/releases/latest) (`lumaupdater.cia`)
* Свежая версия [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)

## <a name="detect" />Определение типа и версии взлома 

Определить какая версия взлома стоит на вашей приставке достаточно просто: 

1. Выключите приставку
1. Зажмите кнопку (SELECT) и, удерживая её, включите консоль
1. Запустится меню конфигурации Luma3DS

    ![]({{ base_path }}/images/screenshots/luma.png)
	{: .text-center}
    {: .notice--info}

1. Обратите внимание на версию Luma3DS и перейдите по ссылке, соответствующей вашей версии:
	+ Если Luma3DS меньше, или равна 7.0.5, то у вас a9lh - [перейдите на b9s 1.2](a9lh-to-b9s)
	+ Если Luma3DS 7.1, то у вас b9s 1.0 и нужно [обновить его до версии 1.2](updating-b9s)
	+ Если Luma3DS 8 и выше, то b9s 1.2 - ничего делать не нужно	
	
{% comment %}

##### <a name="lumaupdater" />Способ I - Luma3ds Updater
{: comment}
1. Установите `lumaupdater.cia` через FBI (как это сделать описано [здесь](games))
1. Запустите lumaupdater из меню Home
1. Выберите "Install stable version" и нажмите (A)
1. Нажмите (A) + (X) для установки Luma3DS на SD-карту и в CTRNAND
1. При появлении надписи "Update complite", нажмите (START) для перезагрузки
  + Если после включения экран остаётся чёрным, то перейдите к разделу [проблемы и их решения](troubleshooting#ts_sys_b9s)   
  + Если появилось окно-конфигуратора Luma3DS, то перейдите к разделу [Настройка Luma3DS](update-luma3ds#lumasetup)   

##### <a name="lumasd" />Способ II, Часть I - Обновление Luma вручную

1. Вставьте SD-карту из приставки в ПК
1. **Скопируйте `boot.firm` из `.7z-архива` Luma3DS в корень SD-карты, соглашаясь на перезапись файлов**
1. Вставляем SD-карту в приставку
1. Включите 3DS
  + Если после включения экран остаётся чёрным, то перейдите к разделу [проблемы и их решения](troubleshooting#ts_sys_b9s)   

##### <a name="lumasetup" />Способ II, Часть II - Настройка Luma3DS

1. Устройство загрузится
  + Если после включения экран остаётся чёрным, то перейдите к разделу [проблемы и их решения](troubleshooting#ts_sys_b9s)
  + Если появилось окно-конфигуратора Luma3DS, то нажимая (A) выберите следующие пункты:    
    + **"Enable game patching"**
    + **"Show NAND or user string in System Settings"**
  + Если у вас **New 3DS**, вы *также* можете включить следующие опции:
    + **"New 3DS CPU" выбрать значение "Clock+L2(x)"**
      + Это увеличит частоту кадров в множестве игр, но может отразиться на стабильности других
      + Если какие-либо игры работают некорректно, отключите эту опцию
	
    ![]({{ base_path }}/images/screenshots/luma-settings.png)
	{: .text-center}
    {: .notice--info}
	
  + Нажмите (START), чтобы сохранить настройки и перезагрузиться

##### <a name="lumactrnand" />Способ II, Часть III - CTRNAND Luma3DS

Обратите внимание, что в некоторых версиях Luma3DS, меню Luma3DS chainloader отображается только в том случае, если в папке payloader более одного приложения. Если установлено только одно приложение, удерживание (START) при включении консоли запустит GodMode9 напрямую.
{: .notice--info}

1. Перейдите в `[0:] SDCARD`
1. Нажмите (Y) на файле `boot.firm`, чтобы скопировать его
1. Нажмите (B) для возврата в главное меню
1. Перейдите в `[1:] SYSNAND CTRNAND`
1. Нажмите (Y), чтобы вставить копию `boot.firm`
1. Выберите "Copy path(s)"
1. Нажмите (A), чтобы разрешить запись в SysNAND (lvl1) и введите указанную комбинацию кнопок
1. Нажмите (B) для возврата в главное меню
1. Перейдите в `[0:] SDCARD`
1. Нажмите (Y) на папке `luma`, чтобы скопировать её
1. Нажмите (B) для возврата в главное меню
1. Перейдите в `[1:] SYSNAND CTRNAND` -> `rw`
1. Нажмите (Y), чтобы вставить копию папки `luma` из вашей SD-карты
1. Выберите "Copy path(s)"
{% endcomment %}

<div id="vk_comments"></div>
<script type="text/javascript">
VK.Widgets.Comments("vk_comments", {limit: 10, attach: "*"});
</script>
