# Исправление сетевых ошибок Windows

На данной странице приведены команды для командной строки (Администратор) для решения некоторых сетевых ошибок Windows.

{% code overflow="wrap" lineNumbers="true" %}
```batch
:: Сброс настроек стека TCP/IP (IPv4 & IPv6)
netsh int ip reset
netsh int ipv6 reset
:: Очистка кэш сопоставителя DNS
ipconfig /flushdns
:: Сброс настроек WinSock
netsh winsock reset
:: Применение функции «Автоматическая настройка окна для HTTP-трафика», которая должна повысить скорость сети.
netsh int tcp set global autotuninglevel=normal
:: Сброс сетевых настроек
ipconfig /release
ipconfig /renew
```
{% endcode %}

{% hint style="info" %}
После ввода всех команд (или только необходимых) – перезагрузите компьютер!
{% endhint %}
