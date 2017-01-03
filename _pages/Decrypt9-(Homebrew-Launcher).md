---
title: "Decrypt9 (Homebrew Launcher)"
permalink: /decrypt9-(Homebrew-launcher).html
sidebar:
  nav: "decrypt9-(Homebrew-launcher)"
---
<a name="start" />
Если ваша прошивка 11.0.0 или 11.1.0, готовьтесь ожидать результата от 20 минут до часа. waithax не зря именуется в народе slowhax. 
{: .notice--info}

#### <a name="what_need" />Что нужно: 

* Свежая версия [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/)
* Свежая версия [safehax](https://github.com/TiniVi/safehax/releases/latest/)
* Свежий билд [svchax](images/svchax.3dsx)
* Свежий билд форка [waithax](https://github.com/TiniVi/waithax/releases/latest)

#### <a name="instructions" />Что делать:

2. Создайте папку `files9` в корне карты памяти, если папки нет - создайте ее. 
3. Скопируйте `safehax.3dsx` в папку `/3ds/` на вашей карте памяти.
4. Скопируйте `safehax.smdh` в папку `/3ds/` на вашей карте памяти.
4. Скопируйте `waithax.3dsx` в папку `/3ds/` на вашей карте памяти.
5. Скопируйте `svchax.3dsx` в папку `/3ds/` на вашей карте памяти.
3. Скопируйте `Decrypt9WIP.bin` из архива с Decrypt9WIP в корень карты памяти и переименуйте `Decrypt9WIP.bin` в `arm9.bin`.
4. Вставьте карту памяти в приставку.
4. Запустите Homebrew launcher.
5. Получите доступ к kernel11:
  + Если ваша прошивка ниже, чем 11.0.0, или вы недавно делали понижение NFIRM (через хардмод, или использование DSiWare), сделайте это запустив svchax *(срабатывает почти мгновенно, но может запуститься не с первой попытки)*.
  + Если ваша прошивка 11.0.0 или 11.1.0,  сделайте это запустив waithax *(готовьтесь ожидать результата от 20 минут до часа; на New 3DS работает быстрее)*.
6. Закройте kernel11-эксплойт (svchax или waithax).
4. Запустите safehax.
4. Если эксплойт сработал верно, запустится Decrypt9.

Переходите к [2.1.0 ctrtransfer](2.1.0-ctrtransfer).    
{: .notice--primary}
