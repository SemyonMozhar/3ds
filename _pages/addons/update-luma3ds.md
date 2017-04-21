---
title: "Обновление Luma3DS"
permalink: /update-luma3ds.html
sidebar:
  nav: "update-luma3ds"
---

#### <a name="what_need" />Что понадобится
* Установленный и рабочий [a9lh](installing-arm9loaderhax)
* Установленный и рабочий [FBI](fbi)
* Свежая версия [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(`.7z`-архив)*
* Свежая версия [Luma3ds Updater](https://github.com/Hamcha/lumaupdate/releases) (`lumaupdater.cia`)

##### <a name="instructions" />Инструкция

##### <a name="part1" />Способ I - Luma3ds Updater

1. Установите `lumaupdater.cia` через FBI (как это сделать описано [здесь](games))
1. Запустите lumaupdater из меню Home
1. Выберите Install normal version и нажмите (A)
1. При появлении надписи Update complite, нажмите (START) для перезагрузки и зажмите (SELECT) для того, чтобы попасть в меню настроек Luma
  + Если после включения экран остаётся чёрным, то перейдите к разделу [проблемы и их решения](troubleshooting#ts_sys_a9lh)   
1. Нажимая (A) выберите следующие пункты:    
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R"**
  + **"Show NAND or user string in System Settings"**
  + **"Enable game patching"**
1. Если у вас **New 3DS**, вы *также* можете включить следующие опции:
  + **"New 3DS CPU" выбрать значение "Clock+L2(x)"**
    + Это увеличит частоту кадров в множестве игр, но может отразиться на стабильности других
    + Если какие-либо игры работают некорректно, отключите эту опцию
1. Нажмите (START), чтобы сохранить настройки и перезагрузиться
  + Если после обновления Luma не запускается, попробуйте воспользоваться нижеследующим способом

##### <a name="part2" />Способ II - Обновление Luma вручную

1. Вставьте SD-карту из приставки в ПК
1. **Скопируйте `arm9loaderhax.bin` из `.7z-архива` Luma3DS в корень SD-карты, соглашаясь на перезапись файлов**
2. Распаковываем архив и переходим в папку out 
4. Вставляем SD-карту в приставку и перезагрузите ее, удерживая кнопку (SELECT)
  + Если после включения экран остаётся чёрным, то перейдите к разделу [проблемы и их решения](troubleshooting#ts_sys_a9lh)   
1. Нажимая (A) выберите следующие пункты:    
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R"**
  + **"Show NAND or user string in System Settings"**
  + **"Enable game patching"**
1. Если у вас **New 3DS**, вы *также* можете включить следующие опции:
  + **"New 3DS CPU" выбрать значение "Clock+L2(x)"**
    + Это увеличит частоту кадров в множестве игр, но может отразиться на стабильности других
    + Если какие-либо игры работают некорректно, отключите эту опцию
1. Нажмите (START), чтобы сохранить настройки и перезагрузиться

После того как luma обновлена рекомендую обновить ее и во внутренней памяти приставки [следующим образом](https://3ds.customfw.xyz/installing-arm9loaderhax#lumactrnand)
{: .notice--warning}