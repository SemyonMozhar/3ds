---
title: "Запуск Decrypt9 через Homebrew Launcher"
permalink: /decrypt9-(Homebrew-launcher).html
sidebar:
  nav: "decrypt9-(Homebrew-launcher)"
---

#### <a name="what_need" />Что понадобится

* Свежая версия [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/latest/)
* Свежая версия [safehax](https://github.com/TiniVi/safehax/releases/latest)
* Свежая версия [fasthax](https://github.com/nedwill/fasthax/releases/latest)

#### <a name="instructions" />Инструкция

1. Вытащите SD-карту, не выходя из Homebrew Launcher, и вставьте её в компьютер
2. Создайте папку `files9` в корне вашей SD-карты, если таковой нет
3. Скопируйте `safehax.3dsx` в папку `/3ds/` на SD-карте
4. Скопируйте `fasthax.3dsx` в папку `/3ds/` на SD-карте
5. Скопируйте `Decrypt9WIP.bin` из `.zip-архива` Decrypt9WIP в корень SD-карты и переименуйте `Decrypt9WIP.bin` в `safehaxpayload.bin`
6. Вставьте SD-карту в 3DS
4. Запустите fasthax, найдя его в списке приложений homebrew 
  + Вам может потребоваться пролистать список вниз, чтобы увидеть нужный пункт
4. После того, как он закончит работу, нажмите (START), чтобы вернуться в HBL
  + Может потребовать нескольких попыток.
5. Запустите safehax, найдя его в списке приложений hombrew 
  + Вам может потребоваться пролистать список вниз, чтобы увидеть нужный пункт
4. Если эксплойт сработал верно, запустится Decrypt9

Следующий шаг: [2.1.0 ctrtransfer](2.1.0-ctrtransfer)    
{: .notice--primary}