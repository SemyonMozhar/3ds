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

##### <a name="instructions" />Инструкция

##### <a name="part1" />Часть I - Обновление Luma3DS

##### <a name="lumaupdater" />Способ I - Luma3ds Updater

1. Установите `lumaupdater.cia` через FBI (как это сделать описано [здесь](games))
1. Запустите lumaupdater из меню Home
1. Выберите "Install stable version" и нажмите (A)
1. При появлении надписи "Update complite", нажмите (START) для перезагрузки и зажмите (SELECT) для того, чтобы попасть в меню настроек Luma
  + Если после включения экран остаётся чёрным, то перейдите к разделу [проблемы и их решения](troubleshooting#ts_sys_a9lh)   
1. Нажимая (A) выберите следующие пункты:    
  + **"Show NAND or user string in System Settings"**
  + **"Enable game patching"**
1. Если у вас **New 3DS**, вы *также* можете включить следующие опции:
  + **"New 3DS CPU" выбрать значение "Clock+L2(x)"**
    + Это увеличит частоту кадров в множестве игр, но может отразиться на стабильности других
    + Если какие-либо игры работают некорректно, отключите эту опцию
	
    ![]({{ base_path }}/images/screenshots/luma-settings.png)
	{: .text-center}
    {: .notice--info}
	
1. Нажмите (START), чтобы сохранить настройки и перезагрузиться
  + Если после обновления Luma не запускается, попробуйте воспользоваться нижеследующим способом

##### <a name="lumasd" />Способ II - Обновление Luma вручную

1. Вставьте SD-карту из приставки в ПК
1. **Скопируйте `boot.firm` из `.7z-архива` Luma3DS в корень SD-карты, соглашаясь на перезапись файлов**
4. Вставляем SD-карту в приставку и перезагрузите ее, удерживая кнопку (SELECT)
  + Если после включения экран остаётся чёрным, то перейдите к разделу [проблемы и их решения](troubleshooting#ts_sys_a9lh)   
1. Нажимая (A) выберите следующие пункты:    
  + **"Show NAND or user string in System Settings"**
  + **"Enable game patching"**
1. Если у вас **New 3DS**, вы *также* можете включить следующие опции:
  + **"New 3DS CPU" выбрать значение "Clock+L2(x)"**
    + Это увеличит частоту кадров в множестве игр, но может отразиться на стабильности других
    + Если какие-либо игры работают некорректно, отключите эту опцию
	
    ![]({{ base_path }}/images/screenshots/luma-settings.png)
	{: .text-center}
    {: .notice--info}
	
1. Нажмите (START), чтобы сохранить настройки и перезагрузиться не отпуская (START)

##### <a name="lumasetup" />Часть II - Настройка Luma3DS

1. Устройство загрузится в меню настройки Luma3DS
  + Если после включения экран остаётся чёрным, то перейдите к разделу [проблемы и их решения](troubleshooting#ts_sys_b9s)
1. Нажимая (A) выберите следующие пункты:    
  + **"Enable game patching"**
  + **"Show NAND or user string in System Settings"**
1. Если у вас **New 3DS**, вы *также* можете включить следующие опции:
  + **"New 3DS CPU" выбрать значение "Clock+L2(x)"**
    + Это увеличит частоту кадров в множестве игр, но может отразиться на стабильности других
    + Если какие-либо игры работают некорректно, отключите эту опцию
	
    ![]({{ base_path }}/images/screenshots/luma-settings.png)
	{: .text-center}
    {: .notice--info}
	
1. Нажмите (START), чтобы сохранить настройки и перезагрузиться

##### <a name="lumactrnand" />Часть III - CTRNAND Luma3DS

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

<div id="vk_comments"></div>
<script type="text/javascript">
VK.Widgets.Comments("vk_comments", {limit: 10, attach: "*"});
</script>