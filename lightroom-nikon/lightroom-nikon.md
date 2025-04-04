---
date: 2015-08-15
categories:
  - photo
tags:
  - Lightroom
  - Photo
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2015/blob/main/lightroom-nikon/lightroom-nikon.md
permalink: https://harrix.dev/ru/articles/2015/lightroom-nikon/
lang: ru
---

# В Lightroom фотографии становятся темнее. Nikon

![Featured image](featured-image.svg)

Долго мучался с проблемой, что при добавлении фотографий в raw формате в Lightroom с фотоаппарата Nikon d5100, фотографии становятся темнее, чем соответствующие jpg варианты.

Итак, всё дело в том, что в настройках у меня был включен `D-Lighting`, позволяющий делать снимки, где темные и яркие участки более выровнены друг с другом в jpg варианте. `Lightroom` не умеет, как оказалось, работать с данной настройкой в raw варианте.

Если вы работаете с RAW, то вам эта настройка будет не нужна. Отключите.

Вот вам jpg с включенным D-Lighting:

![JPG с D-Lighting](img/jpg-with-d-lighting.jpg)

_Рисунок 1 — JPG с D-Lighting_

Вот так эта фотка выглядит в Lightroom, если загрузить RAW версию снимка:

![Lightroom с D-Lighting](img/lightroom-with-d-lighting.jpg)

_Рисунок 2 — Lightroom с D-Lighting_

Как видим, jpg гораздо ярче (D-Light поработал).

А вот так выглядит jpg `с отключенным D-Light`:

![JPG без D-Lighting](img/jpg-without-d-lighting.jpg)

_Рисунок 3 — JPG без D-Lighting_

А в Lightroom выглядит так:

![Lightroom без D-Lighting](img/lightroom-without-d-lighting.jpg)

_Рисунок 4 — Lightroom без D-Lighting_

Как видим, по экспозиции варианты не отличаются почти.

Ниже показано, как отключить этот режим на примере `Nikon d5100` в режиме `M`:

![Вход в настройки на фотоаппарате](img/settings_01.jpg)

_Рисунок 5 — Вход в настройки на фотоаппарате_

![Настройка ADL](img/settings_02.jpg)

_Рисунок 6 — Настройка ADL_

![Отключение «Активный D-lighting»](img/settings_03.jpg)

_Рисунок 7 — Отключение «Активный D-lighting»_
