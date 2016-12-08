---
title: "Понижение прошивки при помощи DSiWare (старая версия)"
permalink: /dsiware-downgrade-(old).html
---

**Это старая версия инструкции для тех, у кого есть купленные "Fieldrunners", "Legends of Exidia", "Guitar Rock Tour", или "The Legend of Zelda: Four Swords" на исходной 3DS**
{: .notice--primary}

Если ваша прошивка 11.0.0, 11.1.0, или 11.2.0, то вы можете понизить версию NATIVE_FIRM, используя DSiWare и вторую 3DS с установленной кастомной прошивкой.
{: .notice}   

Если на любой из консолей у вас прошивка ниже, чем 11.2.0, то следует пройти шаги с ctr-httpwn на каждом девайсе с такой прошивкой, чтобы заработала Передача данных (System Transfer) *(хотя, куда проще просто обновиться до 11.2, разницы в процессе даунгрейда вы не заметите - прим.пер.)*.
{: .notice--info}

Этот метод использует уязвимость, которая позволяет DSiWare-приложениям писать и читать в любом месте NAND. 
{: .notice--info}

Это рабочая реализация "FIRM partitions known-plaintext"-эксплойта. Подробнее о нем [здесь](https://www.3dbrew.org/wiki/3DS_System_Flaws).
{: .notice--info}

Гайд предполагает наличие прошитой arm9loaderhax 3DS с кастомной прошивкой, настроенной по этому же гайду, однако, все нижесказанное заработает и с EmuNAND (правда, с небольшими правками: просто делайте все пункты не в SysNAND, а в EmuNAND). Помните, что RedNAND и EmuNAND - слегка разные реализации одного и того же [концепта](http://3dbrew.org/wiki/NAND_Redirection).
{: .notice--info}

Если у вас есть возможность использовать свою точку входа (например, OOT3dHax, FreakyHax), то смело пропускайте все пункты со **Steel Diver: Sub Wars**. 
{: .notice--info}

{% capture notice-4 %}
Этот эксплойт потребует от вас Передачи данных системы ([System Transfer](http://en-americas-support.nintendo.com/app/answers/detail/a_id/13996/)) из приставки с кастомной прошивки на приставку со стоковой прошивкой. Перенос данных будет работать *только* в одном из следующих направлений: 
  + New 3DS -> New 3DS
  + Old 3DS or 2DS -> Old 3DS or 2DS
  + Old 3DS or 2DS -> New 3DS 
{% endcapture %}

<div class="notice--warning">{{ notice-4 | markdownify }}</div>

Обе приставки должны быть одного региона.
{: .notice--warning}

NNID из исходной 3DS будет находится в целевой 3DS до тех пор, пока вы не перенесете его назад в исходную консоль, либо не позвоните в Nintendo (подробности в инструкции).
{: .notice--danger}

Перенос системы можно делать лишь раз в неделю для одного NNID.
{: .notice--danger}

#### Что нужно:

* Две приставки
  + **Исходная 3DS**: 3DS с кастомной прошивкой (arm9loaderhax, либо прошивка с EmuNAND/EmuNAND) *с последней версией системного ПО*. Убедитесь, что помните пароль от Nintendo Network, без него вы не сможете сделать перенос данных. 
  + **Целевая 3DS**: 3DS с официальной прошивкой в диапазоне *между 11.0.0 и 11.2.0*.
* Купленная DSiWare игра из списка ниже (пиратская копия **не** будет работать) на **исходной 3DS**
  + **Fieldrunners**;
  + **Legends of Exidia**;
  + **Guitar Rock Tour**; 
  + **The Legend of Zelda: Four Swords**.
* Свежая версия [3ds_dsiwarehax_installer](https://github.com/yellows8/3ds_dsiwarehax_installer/releases)
* Свежая версия [3DSident](https://github.com/joel16/3DSident/releases/latest)
* Свежая версия [FBI](https://github.com/Steveice10/FBI/releases/latest)
* Свежая версия [dgTool](https://github.com/Plailect/dgTool/releases/latest)
* The Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
* Архив с прошивкой, соответствующей версии **целевой 3DS**:
  + [New 3DS 11.0.0 to 10.4.0](torrents/11.0.0_to_10.4.0_n3ds.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:2d13a5ea1570f911bd5c6423e0c30e51d548837a&dn=11.0.0%5Fto%5F10.4.0%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
  + [Old 3DS 11.0.0 to 10.4.0](torrents/11.0.0_to_10.4.0_o3ds.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:72393bbd99bc285db84a9cabf39d9b3200058d6a&dn=11.0.0%5Fto%5F10.4.0%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce"><i class="fa fa-magnet" aria-hidden="true"></i></a></code><br>
  ~<br>
  + [New 3DS 11.1.0 to 10.4.0](torrents/11.1.0_to_10.4.0_n3ds.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:d7d60c27c18f53bd8508a194656a465f6448bedf&dn=11.1.0%5Fto%5F10.4.0%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>     
  + [Old 3DS 11.1.0 to 10.4.0](torrents/11.1.0_to_10.4.0_o3ds.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:0caf9a948a2d8bf23606d641f6628e2baeb983bb&dn=11.1.0%5Fto%5F10.4.0%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce"><i class="fa fa-magnet" aria-hidden="true"></i></a></code><br>
  ~<br>
  + [New 3DS 11.2.0 to 10.4.0](torrents/11.2.0_to_10.4.0_n3ds.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:881388a552a1ce9a963d391bf1a023642270991c&dn=11.2.0%5Fto%5F10.4.0%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>     
  + [Old 3DS 11.2.0 to 10.4.0](torrents/11.2.0_to_10.4.0_o3ds.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:a479e4ee55efbc18c181d426cd77a34815388151&dn=11.2.0%5Fto%5F10.4.0%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>    
* Скачанная на **исходную 3DS** официальная версия **Steel Diver: Sub Wars** (игра бесплатная, но работать будет только версия, скачанная из eShop). Не нужна при наличии альтернативной точки входа. Если вы не знаете, что такое альтернативная точка входа - скачайте эту игру. 
* Предыдущая версия [steelhax](https://vegaroxas.github.io/files/steelhax-installer.zip)
* Если версия системного ПО на **целевой 3DS** ниже, чем 11.2.0, вам так же придется воспользоваться
  + свежей версией [ctr-httpwn](https://github.com/yellows8/ctr-httpwn/releases/latest).
  
Можно просто обновиться до 11.2, разницы в процессе даунгрейда вы не заметите, **ОДНАКО, если у вас сейчас 11.0.0., то обновившись можете забыть про browserhax!!!** - *прим.пер*.
{: .notice--info}


#### Что делать:

##### Часть I - Подготовка

1. Создайте папку `files9` в корне карты памяти **исходной 3DS**, если таковой не имеется. 
2. **Используйте [save manager](https://github.com/J-D-K/JKSM/releases/latest) для того, чтобы сделать резервные копии всех важных сейвов на целевой 3DS (приставка будет отформатирована!)**
3. Скопируйте `public.sav` из папки `/dsiware/(8-значный ID)/` из архива `3ds_dsiwarehax_installer`, в корень карты памяти **исходной 3DS** (8-значный ID, соответствующий каждой игре и региону описан ниже)      
  + **Fieldrunners USA Region**: `4b464445`
  + **Fieldrunners EUR Region**: `4b464456`
  + **Legends of Exidia USA Region**: `4b4c4545`
  + **Legends of Exidia EUR Region**: `4b4c4556`
  + **Legends of Exidia JPN Region**: `4b4c454a`
  + **Guitar Rock Tour EUR Region**: `4b475256`
  + **Guitar Rock Tour USA Region**: `4b475245`
  + **The Legend of Zelda: Four Swords EUR Region**: `4b513956`   
  + **The Legend of Zelda: Four Swords USA Region**: `4b513945`    
7. Вставьте карту памяти в **исходную 3DS**. 
4. На **исходной 3DS** удерживайте (START) во время загрузки приставки, чтобы попасть в Hourglass9.
5. Перейдите в SysNAND Options, SysNAND Backup/Restore, затем сделайте бекап **(min size)** SysNAND в `NANDmin.bin`.
6. Нажмите (SELECT) в главном меню, чтобы извлечь КП из **исходной 3DS**, а затем вставьте ее в ПК. 
7. Скопируйте `NANDmin.bin` и  `NANDmin.bin.sha` из папки `/files9/` на карте памяти в надежное место; можете сделать копии в нескольких местах или в облачном хранилище. Этот бекап может спасти вам консоль, если что-то пойдет не так. **(Убедитесь, что размер вашего бекапа соответствует размеру указанному в [этом](nand-size) разделе; если это не так, удалите бекап и создайте его заново!)**
7. Вставьте карту памяти из **целевой 3DS** в компьютер. 
8. **Сохраните файлы с обеих карт памяти в разные папки на компьютере (назовите папки таким образом, чтобы понимать какие файлы откуда)!**
9. Верните обе карты памяти на места (не перепутайте).
10. Нажмите (START) для перезагрузки. 

##### Часть II - Установка сохранения

1. Купленная любая из нижеуказанных DSiWare-игр (пиратская копия **не** будет работать):
  + **Fieldrunners**: работает с **USA + EUR**, удалена из eShop для всех регионов; должна быть уже куплена.
  + **Legends of Exidia**: работает с **USA + EUR**;
  + **Guitar Rock Tour**: работает с **EUR**, нет в eShop; должна быть уже куплена.
2. Запустите FBI на **исходной 3DS**.
3. Перейдите в `SD`.
4. Нажмите (A) на `public.sav` и скопируйте его. 
5. Нажмите (B), чтобы вернуться в меню.
6. Перейдите к `TWL NAND` -> `title` -> `00030004`.
7. Перейдите в папку, соответствующую вашей игре и региону:
  + **Fieldrunners USA Region**: `4b464445`
  + **Fieldrunners EUR Region**: `4b464456`
  + **Legends of Exidia USA Region**: `4b4c4545`
  + **Legends of Exidia EUR Region**: `4b4c4556`
  + **Legends of Exidia JPN Region**: `4b4c454a`
  + **Guitar Rock Tour EUR Region**: `4b475256`
  + **Guitar Rock Tour USA Region**: `4b475245`    
  + **The Legend of Zelda: Four Swords EUR Region**: `4b513956`   
  + **The Legend of Zelda: Four Swords USA Region**: `4b513945`    
9. Перейдите в папку `data`.
8. Нажмите (A) на существующем `public.sav` и удалите его.
9. Нажмите (A) на строке `<current directory>` и вставьте `public.sav`.
5. Нажимайте (B), пока не вернетесь в меню программы.
11. Нажмите (START) для выхода. 
3. Запустите купленную DSiWare игру на **исходной 3DS**.
4. Проверьте, работает ли импортированное сохранение.
  + **Fieldrunners**: нажмите кнопку 'Scores' на главном экране;
  + **Legends of Exidia**: после того, как нажмете (START) и пропустите два игровых экрана, выберите первый слот сохранения и нажмите продолжить (continue).
  + **Guitar Rock Tour**: листайте вниз и перейдите в High-Scores -> Drums -> Easy.
  + **The Legend of Zelda: Four Swords**: Просто начните игру.
  + Если игра падает с ошибкой, касающейся `boot.nds`, либо просто выскакиевает белый экран, **значит эксплойт работает и все в порядке!**
  + Если игра работает нормально безо всяких ошибок, значит вы где-то допустили оплошность и неверно установили файл сохранения. 
  + Если выскакивает черный экран, обратитесь к разделу с [проблемами и их решениями](troubleshooting#twl_broken).

##### Часть III - steelhax

С помощью этой части мы сможем войти в Homebrew launcher после переноса системы.
{: .notice--info}

Если у вас есть альтернативная точка входа, переходите к части V. Если вы не знаете, что такое альтернативная точка входа - выполните все пункты этой части. 
{: .notice--info}

1. Скопируйте папку `steelhax-installer` из архива steelhax в папку `/3ds/` на карте памяти **исходной 3DS**.
2. Вставьте карту памяти обратно в 3DS.
3. Убедитесь, что никакие апдейты для **Steel Diver: Sub Wars** не установлены. Для этого перейдите в Системные настройки (System Settings):
  + Зайдите в "Управление данными" (Data Management), "Nintendo 3DS", "Дополнительный контент" (Downloadable Content).
  + Выберите **Steel Diver: Sub Wars**, затем нажмите "удалить" (delete).
  + Закройте Системные настройки. 
2. Запустите **Steel Diver: Sub Wars**
  + Нажмите Запустить программу. Не обновляйтесь, иначе придется по новому удалять апдейт!
3. Нажмите (A), чтобы продолжить, затем выберите/создайте (если нет) Mii. 
4. Покиньте игру.
2. Запустите Homebrew launcher на **исходной 3DS**.
  + Если у вас на приставке arm9loaderhax, то это можно сделать через [hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases).
4. Нажмите (A) для продолжения.
5. Нажмите (A) для подтверждения версии **Steel Diver: Sub Wars**.
6. Нажмите (A) для подтверждения версии системного ПО **исходной 3DS**.
7. Нажмите (START) для выхода из программы.
8. Нажмите (START) для того, чтобы открыть меню Homebrew launcher.
7. Нажмите (X), чтобы перейти к домашнему экрану без перезагрузки. 
  + Может выскочить ошибка "Произошла ошибка" (Error has occurred). Так бывает, просто нажмите (A), чтобы продолжить. 
9. Запустите **Steel Diver: Sub Wars**, чтобы протестировать эксплойт. 
  + Не обновляйте игру. 
  + Если сохранение игры испорчено:
    + Не нажимайте "OK", иначе вы удалите испорченное сохранение (corrupted). Просто выйдите из игры, нажав кнопку (home).
      + Если вы случайно нажмете "OK", придется по новой указывать Mii. 
    + Повторите установку через Homebrew launcher.
    + Все эти действия могут занять много попыток. 
  + Если все сделано верно, устройство перезапустится в Homebrew launcher.
10. Успешно попав в Homebrew launcher, снова запустите steelhax installer.
11. Нажмите (A) для продолжения.
12. Нажмите (A), чтобы подтвердить версию **Steel Diver: Sub Wars**.
16. В этот раз укажите версию ПО на **целевой 3DS** и версию самой **целевой 3DS** и нажмите (A).
  + Даже если после переноса вы планируете понижать систему на второй консоли, здесь укажите ту версию, на которой консоль сейчас. То есть ту версию, на которой будет совершаться перенос данных. 
12. Скопируйте *содержимое* архива `starter.zip` в корень карты памяти **целевой 3DS**.
13. Вставьте карту памяти назад в **целевую 3DS**.

##### Часть IV - ctr-httpwn

Эта часть нужна только в том случае, если прошивка _целевой 3DS_ ниже, чем 11.2.0.
{: .notice--info}

Эта часть позволит провести перенос системы, даже в том случае, если ваша прошивка ниже последней.
{: .notice--info}

Можно просто обновиться до 11.2, разницы в процессе даунгрейда вы не заметите, **ОДНАКО, если у вас сейчас 11.0.0., то обновившись можете забыть про browserhax!!!** - *прим.пер*.
{: .notice--info}

1. Скопируйте и объедините папку `3ds` из архива ctr-httpwn в корень карты памяти **целевой 3DS**.
2. Верните карту памяти назад в **целевую 3DS**.
2. Запустите Homebrew launcher на устройстве используя способы, описанные в [Homebrew Launcher (Браузера нет)](Homebrew-launcher-(no-browser)).
  + **На New 3DSs с версией системного ПО 10.7.0 и 11.0.0 можете для этого  использовать [Homebrew Launcher (Браузер есть)](homebrew-launcher-(browser))**
  + **Убедитесь, что в системе не установлен menuhax, иначе вы не сможете вернуться на домашний экран из Homebrew launcher**.
3. Запустите ctr-httpwn на **целевой 3DS**.
4. Нажмите (A), чтобы продолжить. 
5. Нажмите (START), чтобы выйти из ctr-httpwn.
6. Нажмите (START), чтобы открыть меню Homebrew launcher.
7. Нажмите (X), чтобы вернуться на домашний экран без перезагрузки.
  + Может выскочить ошибка "Произошла ошибка" (Error has occurred). Так бывает, просто нажмите (A), чтобы продолжить. 
8. Переходите к следующей части без **перезагрузки**.
  + **Целевая 3DS** временно пропатчена для доступа к сетевым функциям без проверки номера установленной прошивки.
  + Помните, что выход из Системных настроек перезагружает приставку.
  + Если вы перезагрузили приставку, то следует повторно запустить ctr-httpwn, иначе Перенос системы не будет работать.

##### Часть V - Перенос системы

8. **Сохраните файлы с обеих карт памяти в разные папки на компьютере (назовите папки таким образом, чтобы понимать какие файлы откуда)!**

Не поленитесь скопировать заново, даже если вот только-только это делали!!! 
{: .notice--warning}

9. Верните обе карты памяти на места (не перепутайте).
4. Если на **целевой 3DS** есть Nintendo Network ID, отформатируйте приставку, используя Системные настройки:
  + Перейдите на последнюю вкладку меню "Прочие настройки" (Other Settings), выберите пункт "Форматировать" (Format System Memory), следуйте инструкциям на экране.
5. Прочитайте внимательно:
  + Ваша 3DS с CFW = "Исходная система";
  + Ваша 3DS с официальной прошивкой = "Целевая система";
  + **Переместите DSiWare по запросу!**
  + **НЕ** удаляйте содержимое карты памяти на исходной системе, даже по запросу.
  + Убедитесь, что обе приставки заряжены и батарея не сядет ни у одной из них во время передачи данных. 
  + При запросе на выбор метода переноса данных с карты памяти в случае переноса данных с 2DS/Old 3DS (исходная) на New 3DS (целевая): 
    + **НЕ** выбирайте "Low-Capacity microSD Card Transfer" (опция 2), при таком варианте перенесутся только тикеты, а DSiWare-игры и, что важно, их сохранения - нет. 
    + Быстрый способ: Выберите "PC-Based Transfer" (опция 2) и по запросу на экране приставке, скопировать содержимое карты памяти из исходной консоли на карту памяти целевой приставки (если у вас на old3ds\2ds стоит micro SD с переходником, можно просто переставить карту).
    + Медленный способ: Выберите "Wireless Transfer" (опция 1) для долгого переноса содержимого карты памяти в целевую приставку по воздуху.
6. Перейдите по [этой ссылке](http://www.nintendo.ru/-/Nintendo-2DS-Nintendo-3DS/-Nintendo-3DS-Nintendo-3DS-XL-/-Nintendo-3DS-Nintendo-3DS-XL/-Nintendo-3DS-Nintendo-3DS-XL-592201.html) ([та же информация, но на английском](http://en-americas-support.nintendo.com/app/answers/detail/a_id/227/)) и следуйте официальным инструкциям от nintendo, держа в голове то, что вы прочитали чуть выше. 

##### Часть VI - Восстановление исходной 3DS

1. На **исходной 3DS**, завершите первоначальную настройку.
2. Выполните одно из следующих действий *(или ни одного, если вас не волнует отсутствие NNID на исходной консоли)*.
    + Продолжайте выполнять оставшуюся часть инструкции для **целевой 3DS**, а затем подождите неделю и выполните перенос данных уже с **целевой 3DS** на **исходную** *(помните, что вы не можете перенести данные с New 3DS на Old 3DS)*.
    + Позвоните в Nintendo и скажите им, что у вас больше нет доступа к устройству, к которому привязан ваш NNID (в нашем случае, это уже **целевая 3DS**) и вы бы хотели привязать аккаунт новому устройству (в нашем случае, это **исходная 3DS**).
3. Перезагрузите **исходную 3DS**, удерживайте (START) во время загрузки устройства, чтобы запустить Hourglass9.
4. Перейдите в SysNAND Backup/Restore восстановите SysNAND из файла `NANDmin.bin`.

##### Часть VII - Резервное копирование прошивки целевой 3DS

1. Вставьте карту памяти **целевой 3DS** в ПК.
1. Скопируйте `boot.nds` в корень карты памяти **целевой 3DS**.
1. Создайте папку `dgTool` в корне карты памяти **целевой 3DS**, если таковой там нет.
3. Скопируйте содержимое архива с NFIRM (11.y.y_to_10.4.0_x3ds.zip) в папку `dgTool` в корне **целевой 3DS**.
3. Верните карту памяти в **целевую 3DS**.
3. Запустите установленную DSiWare игру на **целевой 3DS**.
4. Запустите dgTool, используя установленную DSiWare-игру. 
  + **Fieldrunners**: коснитесь кнопки 'Scores' в главном меню;
  + **Legends of Exidia**: после того, как нажмете (A) или (Start) и пропустите два игровых экрана, выберите первый слот сохранения и нажмите продолжить (continue).
  + **Guitar Rock Tour**: листайте вниз и перейдите в High-Scores -> Drums -> Easy.
  + **The Legend of Zelda: Four Swords**: Просто начните игру.
  + Если у игры нет установленного хакнутого сохранения обратитесь к разделу с [проблемами и их решениями](troubleshooting#ts_dsiware).
5. Выберите "Dump f0f1", чтобы сделать бекап NFIRM **целевой 3DS**.
6. Запомните путь, по которому сохраняется результат. 
7. Выйдите из dgTool.
  + Для этого зажмите кнопку питания и держите до тех пор, пока приставка не выключится.
8. Вставьте КП в компьютер и скопируйте `F0F1_N3DS.bin` или `F0F1_O3DS.bin` (зависит от устройства) в надежное место; можете сделать копии в нескольких местах или в облачном хранилище. Этот бекап может спасти вам консоль, если что-то пойдет не так.

##### Часть VIII - Прошивка целевой 3DS.

**НЕ понижайте прошивку с помощью dgTool на приставках с установленным arm9loaderhax. Это гарантированно приведет к брику!**

3. Запустите установленную DSiWare игру на **целевой 3DS**.
4. Запустите dgTool, используя установленную DSiWare-игру. 
  + **Fieldrunners**: коснитесь кнопки 'Scores' в главном меню;
  + **Legends of Exidia**: после того, как нажмете (A) или (Start) и пропустите два игровых экрана, выберите первый слот сохранения и нажмите продолжить (continue).
  + **Guitar Rock Tour**: листайте вниз и перейдите в High-Scores -> Drums -> Easy.
  + **The Legend of Zelda: Four Swords**: Просто начните игру.
3. Выберите "Downgrade FIRM to 10.4" и подтвердите установку файлов прошивки 10.4.0 в **целевую 3DS**.
4. Закройте dgTool.
  + Для этого зажмите кнопку питания и держите до тех пор, пока приставка не выключится.
5. Перезагрузите приставку.

##### Часть IX - Проверка эксплойта

1. Скопируйте и объедините папку `3ds` из архива с 3DSident с папкой `3ds` в корне карты памяти **целевой 3DS**.
2. Вставьте КП в **целевую 3DS**.
3. Запустите Homebrew launcher на **целевой 3DS** используя способы, описанные в [Homebrew Launcher (Браузера нет)](Homebrew-launcher-(no-browser)).
4. Запустите 3DSident.
5. Убедитесь, что в программе следующие значения совпадают:
  + **Kernel version**: 2.50-11
  + **FIRM version**: 2.50-11
  + Если у вас отображаются другие значения, значит вы где-то допустили ошибку. Проделайте все с самого начала. 

Продолжайте выполнять инструкцию с этого места - [Homebrew Launcher (Браузера нет)](Homebrew-launcher-(no-browser)), используя steelhax в качестве точки входа.
{: .notice--primary}

Можете использовать другую точку входа, если хотите. 
{: .notice--info}

Версия прошивки, указанная в настройках **целевой 3DS** не изменится.
{: .notice--info}

Если переноса данных steelhax крашится в черный экран, обратитесь к разделу с [проблемами и их решениями](troubleshooting#ts_steelhax).
{: .notice--warning}