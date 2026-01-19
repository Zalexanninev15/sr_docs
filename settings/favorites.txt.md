# Файл Меню Избранного

{% hint style="success" %}
Файл: favorites.txt
{% endhint %}

**Меню Избранного** доступно в Telegram боте. Можно использовать команды Telegram бота Shark Remote, встраивать в кнопки Web-приложения, а также создавать обычные ссылки.

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption><p>Пример стандартного меню</p></figcaption></figure>

Всевозможные типы кнопок изображены ниже в виде готовых примеров, которые можно сразу скопировать и вставить в файл **favorites.txt**, с описанием каждого элемента.

Пример 1 (работает только в Telegram Desktop):

`Эхо=>function:@/shell cmd /c echo Hi!`

Описание:

* `Эхо` - текст кнопки
* `=>function:` - означает, что это кнопка Меню Избранного
* `@` - обозначает, что данная кнопка является командой (вставка команды после нажатия кнопки)
* `/shell cmd /c echo Hi!` - выполняемая команда

Пример 2:

`Просто ссылка=>function:?https://github.com/Zalexanninev15`

Описание:

* `Просто ссылка` - текст кнопки
* `=>function:` - означает, что это кнопка Меню Избранного
* `?` - обозначает, что данная кнопка является ссылкой
* `https://github.com/Zalexanninev15` - открываемая ссылка.\
  Также допускается username Telegram бота (без **@**). Пример:\
  `N.E.T.C.A.L.C.=>function:?STEPLOGIC_NetCalc_bot` (а вот [сам Telegram бот](https://t.me/STEPLOGIC_NetCalc_bot))

Пример 3:

`WebApp=>function:!https://myip.ru`

Описание:

* `WebApp` - текст кнопки
* `=>function:` - означает, что это кнопка Меню Избранного
* `!` - обозначает, что данная кнопка открывает Web-приложение в Telegram
* `https://myip.ru` - открываемая ссылка Web-приложения (обязательно HTTPS), ссылка может вести на любой сайт. Открываемый сайт может и не быть Web-приложением в Интернете. \
  Также допускается username Telegram бота (без **@**) с Мини-приложением. Пример:\
  `Test Attach=>function:!asmico_attach_bot` (а вот [сам Telegram бот](https://t.me/asmico_attach_bot))
