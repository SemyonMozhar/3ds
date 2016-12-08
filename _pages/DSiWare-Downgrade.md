---
title: "Понижение прошивки при помощи DSiWare "
permalink: /dsiware-downgrade.html
---

**Если ваша прошивка 11.0.0 или 11.1.0, НЕ ОБНОВЛЯЙТЕСЬ до 11.2.0, если не планируете сейчас следовать этой инструкции. Есть возможность, что сообщество вскоре выпустит новый способ даунгрейда NFIRM с помощью DSiWare _без_ необходимости второй 3DS или хардмода!** 
*Этому замечанию уже несколько месяцев, а метода все нет. Суть в том, что если таковой метод и будет, то точно не на 11.2.0, поскольку на этой прошивке нинтенда закрыла найденную уязвимость - прим. пер. *
{: .notice--primary}

Если у вас уже есть **Fieldrunners**, **Legends of Exidia**, **Guitar Rock Tour**, либо **The Legend of Zelda: Four Swords** на **исходной 3DS**, обратитесь к [старой вверсии инструкции](dsiware-downgrade-(old)).
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
* Купленная в eShop DSiWare-игра на **исходной 3DS**.
  + Пиратская копия игры **НЕ** будет работать. 
  + Размер исполняемого файла игры (`.app`) должен быть больше или равен, `3,457,024 байт`.
  + Размер файла сохранения игры (`public.sav`), должен быть больше или равен `67,584 байт` *(это гарантирует, что `public.sav` достаточно велик, чтобы содержать `savedata.bin` нужного размера)*.
  + Перенос данных подхватить хакнутую игру и сейв только в том случае, если их суммарный размер не увеличится. 
  + Для списка совместимых игр, составленных сообществом, смотрите [список совместимых DSiWare-игр](dsiware-list).
* Архив с необходимыми файлами для sudokuhax injection вашего региона
  + [`DSiWare_USA_sudokuhax_v0_injection.zip`](torrents/DSiWare_usa_sudokuhax_v0_injection.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:43a52b6c2b0536203e3415fa7c5ac9a3a2925bd9&dn=DSiWare_usa_sudokuhax_v0_injection.zip&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
  + EUR - Скоро будет
  + JPN - Скоро будет
* Свежая версия [3DSident](https://github.com/joel16/3DSident/releases/latest)
* Свежий коммит [GodMode9](images/GodMode9-20161207-130503.zip) *(68b81ad)*
* Свежая версия [FBI](https://github.com/Steveice10/FBI/releases/latest)
* Свежая версия [dgTool](https://github.com/Plailect/dgTool/releases/latest)
* The Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
* Архив с NFIRM, соответствующей версии **целевой 3DS**:
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
  
Можно просто обновиться до 11.2, разницы в процессе даунгрейда вы не заметите - *прим.пер*.
{: .notice--info}


#### Что делать:

##### Часть I - Подготовка

1. **Используйте [save manager](https://github.com/J-D-K/JKSM/releases/latest) для того, чтобы сделать резервные копии всех важных сейвов на целевой 3DS (приставка будет отформатирована!)**
2. Создайте папку `files9` в корне карты памяти **исходной 3DS**, если таковой не имеется. 
3. Скопируйте `GodMode9.bin` из архива GodMode9 в папку `/luma/payloads` в корне КП **исходной 3DS** и переименуйте `GodMode9.bin` в `up_GodMode9.bin`.
4. Скопируйте `sudoku_v0.app` из архива `DSiWare_sudokuhax_v0_injection.zip` в корне КП **исходной 3DS**.
5. Скопируйте `savedata.bin` из архива `DSiWare_sudokuhax_v0_injection.zip` в корне КП **исходной 3DS**.
6. Вставьте карту памяти в **исходную 3DS**. 
7. На **исходной 3DS** удерживайте (START) во время загрузки приставки, чтобы попасть в Hourglass9.
8. Перейдите в SysNAND Options, SysNAND Backup/Restore, затем сделайте бекап **(min size)** SysNAND в `NANDmin.bin`.
9. Нажмите (SELECT) в главном меню, чтобы извлечь КП из **исходной 3DS**, а затем вставьте ее в ПК. 
10. Скопируйте `NANDmin.bin` и  `NANDmin.bin.sha` из папки `/files9/` на карте памяти в надежное место; можете сделать копии в нескольких местах или в облачном хранилище. Этот бекап может спасти вам консоль, если что-то пойдет не так. **(Убедитесь, что размер вашего бекапа соответствует размеру указанному в [этом](nand-size) разделе; если это не так, удалите бекап и создайте его заново!)**
11. Вставьте карту памяти из **целевой 3DS** в компьютер. 
12. **Сохраните файлы с обеих карт памяти в разные папки на компьютере (назовите папки таким образом, чтобы понимать какие файлы откуда)!**
13. Верните обе карты памяти на места (не перепутайте).
14. Нажмите (START) для перезагрузки. 
15. Купите любую игру в eShop (нет, пиратская копия не пройдет, нужно именно купить) на **исходной 3DS**.
16. Перейдите в системные настройки (System Settings), "Управление данными" (Data Management), "DSiWare" на **исходной 3DS**.
17. Скопируйте все DSiWare-игры которые уже есть на карте памяти в Память системы (System Memory).
18. Скопируйте DSiWare-игру, которую вы собираетесь использовать, на карту памяти. 
19. Отключите **исходную 3DS** и вставьте карту памяти в ПК. 
20. Перейдите по адресу `/Nintendo 3DS/(32-х значный ID)/(32-х значный ID)/Nintendo DSiWare/`
21. Запишите 8-ми значный ID, содержащийся в имени `.bin`-файла в этой папке. 
  + Например, если вы видите файл `4B4C4545.bin`, запишите `4B4C4545`. 
22. Верните карту памяти в **исходную 3DS** и включите приставку.
23. Перейдите в системные настройки (System Settings), "Управление данными" (Data Management), "DSiWare" на **исходной 3DS**.
24. Удалите DSiWare-игру из карты памяти *(не удаляйте из памяти системы)*.

##### Часть II - Установка сохранения

1. Запустите GodMode9 из под arm9loaderhax, удерживая (ВВЕРХ) во время загрузки.
6. Перейдите в `SDCARD`.
3. Нажмите (Y) на `sudoku_v0.app`, чтобы скопировать его.
4. Нажмите (B), чтобы вернуться в главное меню программы.
5. Перейдите в `SYSNAND TWNLN` -> `title` -> `00030004` -> `(8-ми значный ID)`
  + 8-ми значный ID - тот самый, который вы записали в пункте 21 части I.
3. Перейдите в папку `content`.
4. Нажмите (A) на `.app`-файле, находящемся в  этой папке.
8. Выберите "Inject data \@offset".
9. Нажмите (A), чтобы выбрать смещение `00000000`.
10. Нажмите (A), чтобы разрешить запись в SysNAND и введите указанную комбинацию кнопок.
4. Нажмите (B), чтобы вернуться в главное меню программы.
5. Перейдите в `SYSNAND TWNLN` -> `title` -> `00030004` -> `(8-ми значный ID)`
  + 8-ми значный ID - тот самый, который вы записали в пункте 21 части I.
13. Перейдите в `data`.
14. Нажмите (A) на `public.sav`.
15. Выберите "Mount as FAT image"
  + Если вы не видите такого пункта, убедитесь, что вы запускаете крайний коммит программы [GodMode9](images/GodMode9-20161207-130503.zip), а не свежий релиз. 
  + Если вы не видите этой опции даже на крайнем коммите, [напишите об этом](https://github.com/d0k3/GodMode9/issues).
19. Вы перейдете назад в главное меню.
20. Перейдите в `SDCARD`.
13. Нажмите (Y) на файле `savedata.bin`, чтобы скопировать его.
4. Нажмите (B), чтобы вернуться в главное меню программы.
15. Перейдите в `FAT IMAGE`.
16. Нажмите (Y), чтобы вставить `savedata.bin`.
17. Выберите "Copy path(s)".
10. Нажмите (A), чтобы разрешить запись в SysNAND и введите указанную комбинацию кнопок.
  + Если `savedata.bin` уже есть в образе, то выберите "Overwrite file(s)".
19. Нажмите (Start) для перезагрузки.
20. Запустите DSiWare-игру на **исходной 3DS**.
4. Проверьте, работает ли импортированное сохранение, нажав на экран, либо на какую-либо кнопку.
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

Можно просто обновиться до 11.2, разницы в процессе даунгрейда вы не заметите - *прим.пер*.
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
