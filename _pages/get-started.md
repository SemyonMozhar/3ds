---
title: "Начнем"
permalink: /get-started.html
---

Эта страница содержит инструкции по установке boot9strap на *не взломанную* 3DS или 2DS. Если у вас уже установлен arm9loaderhax, и вы хотите обновиться до boot9strap, следуйте инструкциям в разделе [Обновление до boot9strap](updating-to-boot9strap).
{: .notice--warning}

Цвет вашего устройства может отличаться от представленного на картинках, вам стоит обратить внимание на расположение кнопок и особенности каждого типа устройства, чтобы сделать правильный выбор.
{: .notice}

Нажмите на изображение Вашего устройства, чтобы перейти на соответствующую страницу.
{: .notice--primary}

Разные модели, версии, и регионы устройств требуют различных действий для установки кастомной прошивки с boot9strap. Эта страница поможет вам понять, откуда именно следует начать.
{: .notice--info}

Если вы уже взламывали вашу 3DS ранее и использовали кастомную прошивку на основе EmuNAND, следуйте инструкциям, находясь на SysNAND. В конце все ваши данные будут перенесены из EmuNAND в SysNAND с b9s.
{: .notice--info}

Прежде чем начать, рекомендуется проверить свою SD-карту на ошибки с помощью [H2testw (Windows)](h2testw-windows), [F3 (Linux)](f3-linux), или [F3X (Mac)](f3x-mac)!
{: .notice--warning}

Если вы пользователь Windows, то перед началом работ убедитесь, что в вашей системе включено отображение расширений файлов. Если вы не знаете как это сделать, следуйте этой инструкции: [Расширения файлов (Windows)](file-extensions-windows)!
{: .notice--info}

Обратите внимание, что новый метод [установки boot9strap через hardmod](installing-boot9strap-hardmod) работает на *всех устройствах, любого региона и версий*! Включая устройства CHN- и TWN-регионов, которые раньше считались невзлымываемыми!*
{: .notice--success}

{% capture notice-1 %}
Сообщается о волне банов, выданных Nintendo пользователям CFW. Чтобы защитить себя, выполните следующие шаги перед началом этого руководства:

1. Откройте Системные настройки (System settings), затем "Интернет-настройки" (Internet Settings), затем "SpotPass", затем "Отправка информации о системе" (Sending of System Information)
1. Отключите опцию "Отправка информации о системе" (Sending of System Information)
1. Закройте Системные настройки (System settings)
1. Откройте Список друзей (Friend's List) (значок в виде лица на верхней строчке меню HOME, на нижнем экране)
  + Если появляется ошибка и вас не пускают в меню, значит Список друзей уже отключен
1. Перейдите в настройки Списка друзей, затем "Настройки сообщений друга" (Friend Notification Settings), затем "Показать друзьям, во что вы играете" (Show friends what you're playing)
1. Отключите опцию "Показать друзьям, во что вы играете"
1. Закройте Список друзей
{% endcapture %}

<div class="notice--danger">{{ notice-1 | markdownify }}</div>

| New 3DS | Old 3DS или 2DS |
|:-:|:-:|
| [![New 3DS](/images/new3ds.png)](get-started-new-3ds) <br><br> [![New 3DS XL](/images/new3dsxl.png)](get-started-new-3ds) | [![Old 3DS](/images/old3ds.png)](get-started-old-3ds) &nbsp;&nbsp; [![Old 3DS XL](/images/old3dsxl.png)](get-started-old-3ds) <br><br> [![2DS](/images/2ds.png)](get-started-old-3ds) |

<!-- Put this div tag to the place, where the Comments block will be -->
<div id="vk_comments"></div>
<script type="text/javascript">
VK.Widgets.Comments("vk_comments", {limit: 10, attach: "*"});
</script>