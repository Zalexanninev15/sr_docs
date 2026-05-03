---
description: Разработка плагинов с использованием AutoIt3.
---

# AutoIt

## Следуйте инструкции <a href="#user-content-1-sozdaite-papku-s-nazvaniem-v-vide-imeni-budushego-plagina" id="user-content-1-sozdaite-papku-s-nazvaniem-v-vide-imeni-budushego-plagina"></a>

1\. Создайте папку с _названием в виде имени будущего плагина._

Далее можете продолжить следовать инструкции или скачать готовый пример и на его основе создать свой плагин. Чтобы установить данный плагин, не распаковывая, перетащите файл на список установленных плагинов. Для просмотра и редактирования рекомендую воспользоваться архиватором [7-Zip](https://www.7-zip.org/) со сжатием **Нормальное.**

{% file src="../.gitbook/assets/SimpleAuto3.srp" %}
Пример готового плагина
{% endfile %}

2\. В данной папке (далее в гайде просто **main\_folder**)

{% hint style="info" %}
**{main\_folder}** = **main\_folder**. Все переменные в гайде обозначаются в фигурных скобках.
{% endhint %}

3\. Создайте следующую структуру файлов:

```
{main_folder}\main.manifest
{main_folder}\main.au3
```

4\. В файл **main.manifest** (текстовый файл манифеста плагина с надстройками) вставьте следующий текст:

{% code title="main.manifest" lineNumbers="true" %}
```ini
chat_action_type = 1
message_type = 0
arguments_count = 0
plugin_type = 1
```
{% endcode %}

{% hint style="info" %}
### **Описание**

**chat\_action\_type** - тип действия, которое будет написано в чате во время работы файла

_Значения_

* 0 - ничего не писать
* 1 - "Бот набирает сообщение..".

**message\_type** - тип возвращаемого сообщения в Telegram бота

_Значения_

* 0 - Текстовое сообщение
* 1 - Текстовое сообщение с поддержкой HTML форматирования
* 2 - Ничего не возвращать

_Значения для данного параметра не применяются к плагинам на AutoIt!_

**arguments\_count** - количество обязательных принимаемых аргументов плагина от пользователя

_Значения_

* От 0 до 4

_Значения для данного параметра не применяются к плагинам на AutoIt, но этот параметр и значение необходимы для корректной обработки плагина._
{% endhint %}

5\. Основной код можно написать в файле **main.au3** в любом текстовом редакторе или редакторе кода. Рекомендуется Visual Studio Code с плагином [AutoIt](https://marketplace.visualstudio.com/items?itemName=Damien.autoit).

6\. Вставьте в файл **main.au3** следующий код (базовый пример):

{% code title="main.au3" lineNumbers="true" %}
```autoit
#app {plugin_name}, Version="{plugin_version}", Author={author}, Command={call_command}

run('cmd')
```
{% endcode %}

{% hint style="info" %}
Данный пример кода откроет Командную строку.
{% endhint %}

7\. Заполните данные (всё без пробелов):

* **{plugin\_name}** - название плагина, такое же как для **{main\_folder}**
* **{plugin\_version}** - версия в формате x.x.x.x, где x - число (например: 1.0.0.4)
* **{author}** - автор плагина
* **{call\_command}** - команда для вызова плагина (обязательно начинается с **/**), например: /hello

Должно получиться что-то похожее: `#app HelloWorld, Version="1.0.0.0", Author=developer, Command=/hello`

{% hint style="danger" %}
Данная строка является обязательной для файла плагина!
{% endhint %}

8\. Создайте zip архив с папкой **{main\_folder}** (рекомендую воспользоваться архиватором [7-Zip](https://www.7-zip.org/) со сжатием **Нормальное**)

[<img src="https://user-images.githubusercontent.com/51060911/191972666-a2732f62-6bf0-4ff8-9e4c-eeaee52e6f08.png" alt="image" data-size="original">](https://user-images.githubusercontent.com/51060911/191972666-a2732f62-6bf0-4ff8-9e4c-eeaee52e6f08.png)

{% hint style="danger" %}
Нужно заархивировать не саму папку, а её содержимое!
{% endhint %}

9\. Переименуйте файл в **{main\_folder}** и измените расширение архива на `srp`

10\. Установите файл через Shark Remote.

11\. Тестируйте!

{% hint style="info" %}
Размер установочного файла плагина (созданного архива) должен не превышать 10 мегабайт, иначе установить будет нельзя. Однако, если вы точно уверены в своём плагине, то можно использовать настройку `install_plugins_without_limits` ([подробнее](../settings/main.toml.md))
{% endhint %}
