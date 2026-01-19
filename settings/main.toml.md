---
description: Ручное редактирование главного файла настроек Shark Remote.
---

# Файл конфигурации Shark Remote

{% hint style="success" %}
Файл: main.toml
{% endhint %}

{% hint style="info" %}
Более наглядно можно посмотреть в [WebUI](https://sharkremote.neocities.org/webui).\
Представленный здесь список настроек совместим только с Shark Remote 7+
{% endhint %}

## \[BOT]

<table><thead><tr><th width="297">Настройка</th><th width="244">Описание</th><th>Принимаемые значения</th></tr></thead><tbody><tr><td><code>token</code></td><td>Токен Telegram бота</td><td>токен Telegram бота</td></tr><tr><td><code>admin</code></td><td>Администратор Telegram бота (главный пользователь)</td><td>username администратора (скорее всего просто ваш), записывать без @</td></tr><tr><td><code>userid_for_notifications</code></td><td>Уведомлять о включении Telegram бота в чате (<a href="https://github.com/community/community/assets/51060911/8734e403-3279-41ef-a234-934c4fcc0818">пример</a>)</td><td>UserID пользователя, которому нужно отправить уведомление</td></tr><tr><td><code>imgbb_api_key</code></td><td>API ключ сервиса ImgBB для работы команд <code>/screen w</code> и <code>/screen u</code> (<a href="https://teletype.in/@zalexanninev15/wit_changelog#gNHU">подпробнее</a>)</td><td>API ключ сервиса ImgBB</td></tr><tr><td><code>clients</code></td><td>IP адреса компьютеров в локальной сети для объединения нескольких компьютеров в одного Telegram бота. Для разделения IP адресов используйте точку с запятой. Для работы функции требуется утилита <a href="../lan-component.md"><strong>Shark Remote LA</strong>N</a>.</td><td>Пример 1: 192.168.0.29<br>Пример 2:<br>192.168.0.29;192.168.0.21</td></tr><tr><td><code>skip_token_validation</code></td><td>Пропустить проверку токена Telegram бота: управление состоянием проверки токена (рекомендуется включить галочку, если имеются проблемы с подключением к Telegram или боту)</td><td><code>false</code> или <code>true</code></td></tr><tr><td><code>use_installed_python_for_plugins</code></td><td>Использовать в качестве основы для создания виртуального окружения (или использования напрямую, если нет библиотек для установки) уже установленный Python из системы. Если <code>false</code>, то будет загружен и использован Python 3.13.3. Требуется только для плагинов на Python, если таковые отсутствуют, то Python не будет использоваться</td><td><code>false</code> или <code>true</code></td></tr><tr><td><code>wsl_linux</code></td><td>Использовать определённый дистрибутив в WSL. Названия можно посмотреть в PowerShell командой: <code>wsl --list --verbose</code><br>По умолчанию используется дистрибутив отмеченный <strong>*</strong></td><td>Название дистрибутива</td></tr></tbody></table>

## \[ACCESS\_CONTROL]

Настройки данного раздела управляют контролем доступа для второго, обычного, пользователя (не администратора).

**`blocked_commands`**

<table><thead><tr><th width="382">Обозначение</th><th>Описание</th></tr></thead><tbody><tr><td>Любая команда Telegram бота, которая начинается с "/"</td><td>Блокировка команды</td></tr><tr><td>#avx#</td><td>Блокировка команды /avx (изменение настроек Shark Remote)</td></tr><tr><td>#filemanager#</td><td>Блокировка команды /fm и /vial (файловый менеджер)</td></tr><tr><td>#all_plugins#</td><td>Блокировка доступа ко всем плагинам</td></tr><tr><td>#all_variables#</td><td>Блокировка доступа ко всем пользовательским переменным</td></tr><tr><td>#file#</td><td>Блокировка приёма всех файлов от пользователя</td></tr><tr><td>#file_desktop#</td><td>Блокировка приёма файлов от пользователя, которые он хочет установить в качестве обоев Рабочего стола (подпись "desktop")</td></tr><tr><td>#file_tprint#</td><td>Блокировка приёма файлов от пользователя, которые он желает распечатать на принтере (подпись "tprint")</td></tr><tr><td>#file_iprint#</td><td>Блокировка приёма изображений-документов от пользователя, которые он желает распечатать на принтере (подпись "iprint")</td></tr><tr><td>#file_torrent#</td><td>Блокировка приёма torrent-файлов от пользователя, которые он хочет использовать для скачивания через qBittorrent (подпись "torrent")</td></tr><tr><td>#file_zip#</td><td>Блокировка приёма zip-файлов от пользователя с подписью "zip"</td></tr><tr><td>#file_run#</td><td>Блокировка приёма исполнямых файлов от пользователя с подписью "run"</td></tr><tr><td>#audio#</td><td>Блокировка всех аудиофайлов от пользователя</td></tr><tr><td>#audio_play#</td><td>Блокировка аудиофайлов от пользователя, которые он хочет воспроизвести на компьютере (подпись "play")</td></tr><tr><td>#amk#</td><td>Блокировка кнопок клавиатуры (под строкой ввода текста)</td></tr><tr><td>#mk0#</td><td>Блокировка кнопки клавиатуры "🖥 Мониторинг"</td></tr><tr><td>#mk1#</td><td>Блокировка кнопки клавиатуры "🕹 Управление"</td></tr><tr><td>#mk2#</td><td>Блокировка кнопки клавиатуры "📜 Задачи"</td></tr><tr><td>#mk3#</td><td>Блокировка кнопки клавиатуры "🗃 Файлы и папки"</td></tr><tr><td>#mk4#</td><td>Блокировка кнопки клавиатуры "🌐 Сеть"</td></tr><tr><td>#mk5#</td><td>Блокировка кнопки клавиатуры "😎 Плагины и переменные"</td></tr><tr><td>#mk6#</td><td>Блокировка кнопки клавиатуры "📩 Отправка и сохранение"</td></tr><tr><td>#mk7#</td><td>Блокировка кнопки клавиатуры "🤏 Другое"</td></tr><tr><td>#mk_fav#</td><td>Блокировка кнопки клавиатуры "⭐ Избранное"</td></tr><tr><td>#mk_pcs#</td><td>Блокировка кнопки клавиатуры "☢️ Клиенты"</td></tr></tbody></table>

{% hint style="info" %}
Пример записи: `#audio#;#file_torrent#;/info;#mk1#`

Если же блокировка всего одна, то её следует просто записать (без ";" в конце).
{% endhint %}

#### `user` - username пользователя, записывать без @

## \[GEOLOCATION]

Раздел настроек для управления геолокацией компьютера (из Telegram бота) с помощью публичного IP-адреса.

#### `selected_service`

Сервис для определения геолокации.

| Значение | Сервис определения геолокации PC                                                                                 |
| -------- | ---------------------------------------------------------------------------------------------------------------- |
| 0        | ip2location.io (по умолчанию)                                                                                    |
| 1        | ipwhois.io                                                                                                       |
| 2        | ipgeolocation.io (трубуется API ключ, который необходимо вписать в значение настройки `ipgeolocationio_api_key`) |
| 3        | ip-api.com                                                                                                       |

## \[PRINT\_OPTIONS]

Настройки печати текста.

| Настройка | Описание                                         |
| --------- | ------------------------------------------------ |
| `font`    | Точное название  шрифта установленного в системе |
| `size`    | Размер выбранного шрифта (целые значения)        |
| `printer` | Название принтера для печати                     |

## \[UI]

Раздел настроек для конфигурации графического интерфейса Shark Remote.

<table><thead><tr><th width="280">Настройка</th><th>Описание</th><th>Принимаемые значения</th></tr></thead><tbody><tr><td><code>use_window_mini_mode</code></td><td>Использовать Мини-режим для окна управления бото, настройка создана для любителей минимализма. Возврат в обычное окно – вторая иконка с правой стороны или используя сочетание клавиш Ctrl+M (подробности можно узнать на <a href="../faq/hotkeys.md">этой странице</a>)</td><td><code>false</code> или <code>true</code></td></tr><tr><td><code>use_ninja_mode</code></td><td>Скроет весь интерфейс, Shark Remote будет функционировать в скрытом режиме</td><td><code>false</code> или <code>true</code></td></tr><tr><td><code>menu_color</code></td><td>Цвет полоски выбора в меню приложения, <em>Новогодний цвет</em> имеет расширенные визуальные решения</td><td><code>default</code>, <code>native</code> (цвет с учётом акцентного цвета в Windows), <code>brave</code>, <code>unigram</code>, <code>vivaldi</code>, <code>github</code>, <code>μtorrent</code>, <code>happy_new_year</code>, <code>happy_new_year_with_icons</code>, <code>happy_new_year_with_icons_and_hide_log</code></td></tr><tr><td><code>use_window_transparency</code></td><td>Использовать прозрачность для главного окна</td><td><code>false</code> или <code>true</code></td></tr><tr><td><code>use_window_animation</code></td><td>Использовать анимацию плавного появления окна</td><td><code>false</code> или <code>true</code> (<code>false</code> при значении <code>true</code> для <code>use_window_transparency</code>)</td></tr><tr><td><code>use_forced_performance</code></td><td>Режим производительности: специальный авторский алгоритм определения и оптимизации окна Shark Remote, чтобы достичь максимальной производительности/избавиться от "лагов". Данный режим может включаться и автоматически при запуске Shark Remote (требуется согласие пользователя) на интегрированных видеокартах от Intel, старых видеокартах от NVIDIA и AMD, а также при запуске ПО в виртуальных машинах, что позволяет улучшить общую отзывчивость UI. Рекомендуется включать вручную (через данную настройку), только если имеются реальные проблемы с отзывчивостью UI.</td><td><code>0</code> - выключить, <code>1</code> - включить, <code>2</code> - никогда не предлагать (и выключить, если было ранее включено)</td></tr><tr><td><code>use_webview2</code></td><td>Использовать WebView2 для отображения страницы с настройками Shark Remote. Если <code>false</code>, то произойдёт открытие в браузере, настройки не будут автоматически загружены и применены после изменения</td><td><code>false</code> или <code>true</code></td></tr><tr><td><code>skip_splash_screen</code></td><td>Пропустить показ плашки загрузки (Splash Screen) - скрытие Splash Screen во время загрузки Shark Remote</td><td><code>false</code> или <code>true</code></td></tr><tr><td><code>use_forced_permonitorv2</code></td><td>Принудительно задействует <em>PerMonitorV2</em> на экранах с высоким разрешение, чтобы решить проблемы с отображением (может помочь, если наблюдаются проблемы отображения UI на экранах 1920x1080 и выше)</td><td><code>false</code> или <code>true</code></td></tr><tr><td><code>use_auto_scale_100</code></td><td>Управление применением масштаба в 100% при запуске Shark Remote</td><td><code>false</code> или <code>true</code></td></tr><tr><td><code>use_auto_resize_windows</code></td><td>Частичный автоматический подгон размера окон (может помочь, если наблюдаются проблемы отображения UI на экранах 1920x1080 и выше)</td><td><code>false</code> или <code>true</code></td></tr><tr><td><code>use_forced_auto_resize_windows</code></td><td>Частичный автоматический подгон размера окон (может помочь, если наблюдаются проблемы отображения UI на экранах 1920x1080 и выше, данный вариант работает всегда)</td><td><code>false</code> или <code>true</code></td></tr></tbody></table>

## \[OTHER]

Раздел настроек для изменения дополнительных настроек.

<table><thead><tr><th width="281">Настройка</th><th>Описание</th><th>Принимаемые значения</th></tr></thead><tbody><tr><td><code>check_for_updates</code></td><td>Управление проверкой обновления (даже в ручном режиме!)</td><td><code>false</code> или <code>true</code></td></tr><tr><td><code>use_online_checks</code></td><td>Игнорирует проверки доступности критически важных Интернет-сервисов и продолжает работу (может вызывать проблемы в работе Shark Remote, если проблемы имеются)</td><td><code>false</code> или <code>true</code></td></tr><tr><td><code>install_plugins_without_limits</code></td><td>Убирает ограничение на размер установочных файлов плагинов (не более 10 Мб), позволяя устанавливать плагины любого размера</td><td><code>false</code> или <code>true</code></td></tr><tr><td><code>file_version</code></td><td>Версия конфигурационного файла, используется для определения совместимости версии Shark Remote и файла конфигурации, что позволяет избежать проблем при загрузке значений настроек из конфигурационного файла</td><td>Версия конфигурационного файла (изменять вручную <strong>нельзя</strong>, от этого зависит работоспособность Shark Remote)</td></tr></tbody></table>
