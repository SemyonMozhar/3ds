---
title: "Установка boot9strap (ntrboot)"
lang: ru
permalink: installing-boot9strap-ntrboot.html
author_profile: true
---
{% include toc title="Разделы" %}
## Что понадобится

* Магнит для ввода консоли в режим ожидания (если используется консоль складной конструкции)
* Флешкартридж с прошитым ntrboot
* Свежая версия [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* Свежая версия [boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *(стандартный boot9strap; не `devkit-файл`, не `ntr-файл`)*
* Свежая версия [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(`.7z-архив`)*
* Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)

## Инструкция

#### Часть I - Подготовительные работы

1. Выключите консоль
1. Вставьте SD-карту в компьютер
1. Скопируйте `SafeB9SInstaller.firm` в корень SD-карты и переименуйте его в `boot.firm`
1. Скопируйте _содержимое_ `starter.zip` в корень вашей SD-карты
1. Создайте папку `boot9strap` в корне SD-карты
1. Скопируйте `boot9strap.firm` и `boot9strap.firm.sha` из `.zip-архива` boot9strap в папку `/boot9strap/` в корне SD-карты

    ![]({{ base_path }}/images/screenshots/boot9strap-ntrboot-file-layout.png)
    {: .notice--info}

1. Вставьте SD-карту обратно в консоль
1. Включите консоль

#### Часть II - ntrboot

1. Используйте магнит, чтобы найти место на консоли, где срабатывает датчик режима ожидания
  + Этот шаг не требуется выполнять для консоли old 2DS (которая имеет переключатель режима ожидания)
1. Выключите консоль
1. Вставьте ваш флешкартридж в консоль
1. Поместите магнит на место, где срабатывает датчик режима ожидания
  + На консоли old 2DS вместо этого включите переключатель режима ожидания
1. На несколько секунд зажмите кнопки (Power) + (START) + (SELECT) + (X), затем отпустите
  + Может потребоваться несколько попыток, поскольку позиционирование неудобное
1. Если эксплойт сработал, запустится SafeB9SInstaller

#### Часть III - Установка boot9strap

1. Дождитесь окончания всех проверок безопасности
1. При появлении запроса, введите указанную комбинацию кнопок для установки boot9strap
1. После завершения принудительно выключите консоль, удерживая кнопку питания
  + Ваша консоль будет загружаться только в SafeB9SInstaller до выполнения следующей части

#### Часть IV - Настройка Luma3DS

1. Вставьте SD-карту в компьютер
1. Удалите файл `boot.firm` из корня SD-карты
1. Скопируйте файл `boot.firm` из `.7z-архива` Luma3DS в корень SD-карты
1. Вставьте SD-карту обратно в консоль
1. Включите консоль
1. Ваша консоль должна загрузиться в меню конфигурации Luma3DS
  + Если экран остаётся чёрным, то перейдите к разделу [проблемы и их решения](troubleshooting#ts_sys_b9s)
1. Нажимая (A) выберите следующие пункты:    
  + **"Show NAND or user string in System Settings"**
1. Нажмите (START), чтобы сохранить настройки и перезагрузиться
  + Если появляется ошибка, просто переходите к следующей странице

___

Следующий шаг: [Завершение установки](finalizing-setup)
{: .notice--sucess}

___

Это дополнительные разделы, которые позволят вернуть флешкартридж в исходное состояние (чтобы использовать флешкартридж для его стандартных функций).

Обратите внимание, что Acekard 2i сохраняет возможность запускать `.nds-файлы`после установки эксплойта ntrboot. В таком случае Acekard 2i будет работать только на приставках с кастомной прошивкой! После того, как вы установите эксплойт ntrboot, картридж перестанет запускать `.nds-файлы` на NDS, NDSL, DSi, или 3DS со стоковой прошивкой.

Не приступайте к нижеследующим частям, пока не выполните предыдущие инструкции на этой странице.

#### Часть V (i) - Удаление ntrboot (прошитого через NDS)

1. Извлеките флешкартридж из **целевой 3DS**
1. Вставьте флешкартридж без SD-карты обратно в **исходную NDS / NDSL**
1. Нажмите (Y), чтобы выбрать "restore flashrom"
1. Нажмите (B) для выхода

#### Часть V (ii) - Удаление ntrboot (прошитого с помощью нескольких 3DS)

1. Запустите Luma3DS chainloader, держа нажатой кнопку (START) во время загрузки на **исходной 3DS**
1. Выберите "ntrboot_flasher"
1. Выберите "Restore Flash"
1. Нажмите (Y) чтобы продолжить
1. Дождитесь окончания процесса
1. Нажмите (B) для возврата в главное меню
1. Выберите "EXIT" чтобы выключить **исходную 3DS**

#### Часть V (iii) - Удаление ntrboot (прошитого с помощью одной 3DS)

###### Что понадобится

* Свежая версия [ntrboot_flasher](https://github.com/kitling/ntrboot_flasher/releases/latest)
* Резервная копия прошивки, соответствующей версии вашего флешкартриджа:
  + <i class="fa fa-magnet" aria-hidden="true" title="Это магнитная ссылка. Используйте торрент-клиент для работы с ней."></i> - [`R4i_Gold_3DS_RTS-Flashrom.zip`](magnet:?xt=urn:btih:0bd5db43b86bcba7aa862c65e15ef8a6358b7099&dn=R4i_Gold_3DS_RTS-Flashrom.zip&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce)
  + <i class="fa fa-magnet" aria-hidden="true" title="Это магнитная ссылка. Используйте торрент-клиент для работы с ней."></i> - [`Acekard_2i_(HW_44)-Flashrom.zip`](magnet:?xt=urn:btih:1f8830ce7fea3a806999734fb8a457fa3e649c1d&dn=Acekard_2i_%28HW_44%29-Flashrom.zip&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce)
  + <i class="fa fa-magnet" aria-hidden="true" title="Это магнитная ссылка. Используйте торрент-клиент для работы с ней."></i> - [`Acekard_2i_(HW_81)-Flashrom.zip`](magnet:?xt=urn:btih:948e6865b57fa2fc469d68df500f774a6d5887a4&dn=Acekard_2i_%28HW_81%29-Flashrom.zip&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce)
  + Пользователи Acekard 2i должны были отметить HW Rev картриджа ранее
  + Пользователи Acekard 2i не отметившие HW Rev флешкартриджа могут воспользоваться функцией "Dump Flash" в ntrboot_flasher чтобы увидеть её

###### Инструкции

1. Выключите консоль
1. Вставьте SD-карту в компьютер
1. Создайте папку `ntrboot` в корне SD-карты
1. Скопируйте `backup.bin`из `.zip-архива` с резервной копией прошивки вашего картриджа в папку `/ntrboot/` в корне вашей SD-карты
1. Создайте папку `payloads` в папке `luma` на SD-карте 
1. Скопируйте `ntrboot_flasher.firm` из `.zip-архива` ntrboot_flasher в папку `/luma/payloads/` на SD-карте **исходной 3DS**
1. Вставьте SD-карту обратно в устройство
1. Вставьте в консоль ваш DS / DSi флешкартридж, совместимый с ntrboot
1. Запустите ntrboot_flasher, держа нажатой кнопку (START) во время загрузки
1. Выберите "Restore Flash"
1. Нажмите (Y) чтобы продолжить
1. Дождитесь окончания процесса
1. Нажмите (B) для возврата в главное меню
1. Выберите «EXIT» для выключения устройства