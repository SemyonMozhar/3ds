---
title: "Смена региона "
permalink: /region-changing.html
sidebar:
  nav: "region-changing"
---
<a name="start" />
Эта дополнительная секция рассказывает о смене региона на вашей приставке с arm9loaderhax CFW SysNAND. Смысл в том, чтобы установить 9.2.0 ctrtransfer для того региона, на который вы хотите сменить текущий и внести изменения в файл SecureInfo_A.
{: .notice--primary}

**Смена региона практически бесполезна с тех пор, как в luma3DS добавили поддержку [эмуляции региона](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage) для отдельных игр** (*эта же инструкция, но на русском в группе 3ds_cfw [вконтакте](https://vk.com/topic-125012133_34680173) - прим. пер.*).
{: .notice--info}

Этот процесс отсоединит NNID от приставки, поскольку он больше не будет совместим с вашей консолью из-за того, что она поменяет регион. NNID привязан к конкретному устройству и к его региону, поэтому совершенно не возможно переносить NNID между приставками с разными регионами без применения [комплексных и сложных решений](https://gist.githubusercontent.com/yifanlu/e80db121d38aceb8cca0e03cefd5853b/raw/3c4dd89869156ca0f945a2791e699acfdb32b510/gistfile1.txt).
{: .notice--warning}

Только **New 3DS, которая никогда до этого не была привязана к eShop** и **любая Old 3DS** смогут подключиться к eShop и использовать все его возможности уже в новом регионе.  
{: .notice--warning}

Бывает, что eShop не работает там, где он, казалось бы, должен работать. Такое поведение объясняется особенностями работы серверов Nintendo, на которые я, увы, влияния не имею. 
{: .notice--warning}

Меняя регион при помощи ctrtransfer (в этом гайде используется именно он) по какой-то причине мы убиваем reboot-патч. Из-за этого владельцы old3ds теряют возможность играть в игры, требующие всю оперативную память (например, Monster Hunter, Super Smash Bros, and Pokémon Sun / Moon). Единственный известный мне способ, исправляющий это - форматирование девайса из системных настроек. 
{: .notice--warning}

**У вас уже должен быть установлен arm9loaderhax + Luma3DS.**
{: .notice--danger}

#### <a name="what_need" />Что нужно: 

* Свежая версия [GodMode9](https://github.com/d0k3/GodMode9/releases/)
* Свежая версия [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/latest)
* Образ 9.2.0 ctrtransfer для вашего устройства и региона, который вы собираетесь поставить:
  +    [New 3DS 9.2.0 - EUR - ctrtransfer](magnet:?xt=urn:btih:fed7bfeec0e52b42a77467cfb6ffd3e9dd2d5a70&dn=9.2.0-20E%5Fctrtransfer%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)   
  +    [New 3DS 9.2.0 - JPN - ctrtransfer](magnet:?xt=urn:btih:b22d67fd02b3b0e30ac991e451db0f2d32e7beca&dn=9.2.0-20J%5Fctrtransfer%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    [New 3DS 9.2.0 - USA - ctrtransfer](magnet:?xt=urn:btih:985d47442dc470d1b9f908256bed041c63885f60&dn=9.2.0-20U%5Fctrtransfer%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)    
~
  +    [Old 3DS/2DS 9.2.0 - EUR - ctrtransfer](magnet:?xt=urn:btih:8d6142313971b08f92257e7fb1c1d5689e34ed78&dn=9.2.0-20E%5Fctrtransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    [Old 3DS/2DS 9.2.0 - JPN - ctrtransfer](magnet:?xt=urn:btih:24ad2b85e67013ef1f91178dca7ad2e40663b9b2&dn=9.2.0-20J%5Fctrtransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    [Old 3DS/2DS 9.2.0 - USA - ctrtransfer](magnet:?xt=urn:btih:1dc79a2a0babb45497961888f369423a93135e2b&dn=9.2.0-20U%5Fctrtransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
 
#### <a name="instructions" />Что делать:

**В некоторых приставках вместо `SecureInfo_A` используется `SecureInfo_B`; это нормально, просто по ходу инструкции все действия производите над `SecureInfo_B`.**    

##### <a name="part1" />Часть I - Подготовка

1. Скопируйте `GodMode9.bin` из архива GodMode9 в папку `/luma/payloads` в корне КП и переименуйте `GodMode9.bin` в `up_GodMode9.bin`.
2. Скопируйте `Decrypt9WIP.bin` из архива Decrypt9WIP в папку `/luma/payloads` в корне КП и переименуйте `Decrypt9WIP.bin` в `x_Decrypt9WIP.bin`.
3. Скопируйте файлы .bin` и `.bin.sha` образа 9.2.0 ctrtransfer из архива с 9.2.0 ctrtransfer в папку /files9/` в корне карты памяти. 
4. Вставьте карту памяти в консоль. 

##### <a name="part2" />Часть II - Резервное копирование тикетов

5. Запустите Decrypt9 из под arm9loaderhax, удерживая (X) во время старта консоли. 
6. Перейдите в меню "Ticket/Titlekey Options", выберите "Ticket Dump (SysNAND)".
7. Нажмите (SELECT) и извлеките КП, а затем вставьте ее в компьютер. 
8. Удалите все файлы с разрешением `.tik` из папки `/files9/`, которые **не начинаются** с "00-".
9. Все файлы с разрешением `.tik`, начинающиеся с "00-" оставьте в папке. 
  + Если файлов, начинающихся с "00-" в папке нет, просто двигайтесь дальше.
10. Вставьте карту памяти назад в 3DS и нажмите (B), чтобы вернуться в главное меню.
11. Перейдите в "SysNAND Options", "System Save Dump", и выберите "Dump configsave.bin".

##### <a name="part3" />Часть III - ctrtransfer

5. Запустите Decrypt9 из под arm9loaderhax, удерживая (X) во время старта консоли. 
6. Перейдите в меню "SysNAND Options", а затем в "CTRNAND Transfer" и в "Auto CTRNAND Transfer".
7. Выберите свой образ 9.2.0 ctrtransfer и нажмите (A).
8. **Сделайте резервную копию SysNAND в файл `NANDmin.bin` по запросу и нажмите (А) для подтверждения**.
9. Процесс пройдет полностью автоматически и займет много времени. 
10. Как только процесс завершится, нажмите (SELECT), чтобы извлечь КП. 
8. Вставьте КП в компьютер, скопируйте `NAND_N3DS.bin` или `NAND_O3DS.bin` (зависит от вашей модели) в надежное место.
  + Сделайте копии в нескольких местах или в облачном хранилище; 
  + Этот бекап может спасти вам консоль, если что-то пойдет не так.
  + **Убедитесь, что размер вашего бекапа соответствует размеру указанному в [этом](nand-size) разделе; если это не так, удалите бекап и создайте его заново!**
12. Удалите файлы .bin и .bin.sha от 9.2.0 ctrtransfer из папки /files9/ на карте памяти.
10. Вставьте карту памяти в консоль.

##### <a name="part4" />Часть IV - Редактирование SecureInfo

1. Отключите приставку. 
2. Включите консоль, удерживая кнопку (ВВЕРХ)
**(Будьте ОЧЕНЬ внимательны - с этой утилитой можно натворить делов, что не спасет и arm9loaderhax!!!)**.
2. Перейдите в `SYSNAND CTRNAND` -> `rw` -> `sys`.
3. Нажмите (Y) на файле `SecureInfo_A`, чтобы скопировать его.
4. Нажмите (Y) чтобы вставить копию `SecureInfo_A`.
5. Выберите "Copy path(s)".
6. Нажмите (A), чтобы разблокировать SysNAND на запись, затем нажмите указанную комбинацию клавиш. 
7. Выберите "Choose new name".
8. С помощью крестовины переименуйте файл в `SecureInfo_C`, нажмите (A) по окончанию (соглашайтесь на замену существующего `SecureInfo_C`, если таковой имеется). 
9. Пролистайте вниз до `SecureInfo_C`, который мы только что создали. 
10. Нажмите (A) на файле `SecureInfo_C` и выберите "Show in Hexeditor".
11. Нажмите (A), чтобы продолжить. 
12. Нажмите (A), чтобы войти в режим редактирования. 
13. Перейдите на начало строки под номером 00000100 и нажмите (A).
14. Удерживая (A), нажимайте (ВВЕРХ) или (ВНИЗ) для редактирования значения. 
15. Поменяйте первое число в строке (из двух цифр) в соответствии с номером, указанным ниже *каждый номер принадлежит к определенному региону; выберите тот, на который вы меняете*:
    - "00" : JPN
    - "01" : USA
    - "02" : EUR
16. Нажмите (B), чтобы выйти из режима редактирования, (А), чтобы сохранить изменения, а затем еще раз (В).
17. Если все сделано правильно, то вы увидите оба файла - `SecureInfo_A` и `SecureInfo_C`. (`SecureInfo_C` автоматически используется вместо `SecureInfo_A`в том случае, если luma3DS находит его в директории).
18. Нажмите (START) для перезагрузки. 

##### <a name="part5" />Часть V - Восстановление тикетов

1. Запустите FBI.
2. Выберите "SD".
3. Выберите "files9".
4. Выберите "\<current directory>".
5. Выберите "Install and delete all tickets".
6. Подождите. Будет казаться, что приставка зависла, но это не так. Дайте ей немного подумать.
7. Нажмите (A) для подтверждения.
8. Нажмите (B), чтобы отказаться от установки тикетов из CDN.
9. Выйдите из FBI нажатием кнопки (home).

##### <a name="part6" />Часть VI - Региональные настройки

1. Откройте Системные настройки.
2. Перейдите в пункт "Прочие настройки" (Other Settings), "Профиль" (Profile), "Настройки региона" (Region Settings).
3. Выберите страну нужного региона.
2. Перейдите в пункт "Прочие настройки" (Other Settings), "Язык" (Language).
4. Выберите нужный язык. 
5. Обновите SysNAND нового региона до актуальной версии.

##### <a name="part7" />Часть VII - Восстановление конфигов

1. Перезагрузитесь, удерживая кнопку (X), чтобы запукстить Decrypt9 через arm9loaderhax.
2. Перейдите в "SysNAND Options", "System Save Inject", и выберите "Inject configsave.bin".


Old 3DSs / 2DSs желательно отформатировать (через TinyFormat или Системные настройки), иначе игры требующие режима расширенной памяти могут не заработать (Monster Hunter, Super Smash Bros, Pokemon Sun/Moon, итп).
{: .notice--info}

Форматирование устройства в ходе процедуры ctrtransfer *без восстановления конфига* может привести к проблемам с яркостью и мерцанием.
{: .notice--info}