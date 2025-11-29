# WLAN Pi Profiler

На версии wlanpi 3.4.2 Profiler не работает. Нужно откатиться на 1.0.18-2.
Как это сделать?

Смотрим, на какую версию мы можем откатиться?

`apt-cache madison wlanpi-profiler`:

```
wlanpi-profiler |   1.0.20-1 | https://packagecloud.io/wlanpi/main/debian bullseye/main arm64 Packages
wlanpi-profiler |   1.0.19-1 | https://packagecloud.io/wlanpi/main/debian bullseye/main arm64 Packages
wlanpi-profiler |   1.0.18-2 | https://packagecloud.io/wlanpi/main/debian bullseye/main arm64 Packages
wlanpi-profiler |     1.0.18 | https://packagecloud.io/wlanpi/main/debian bullseye/main arm64 Packages
wlanpi-profiler |     1.0.17 | https://packagecloud.io/wlanpi/main/debian bullseye/main arm64 Packages
wlanpi-profiler |     1.0.16 | https://packagecloud.io/wlanpi/main/debian bullseye/main arm64 Packages
wlanpi-profiler |     1.0.15 | https://packagecloud.io/wlanpi/main/debian bullseye/main arm64 Packages
wlanpi-profiler |     1.0.14 | https://packagecloud.io/wlanpi/main/debian bullseye/main arm64 Packages
wlanpi-profiler |     1.0.13 | https://packagecloud.io/wlanpi/main/debian bullseye/main arm64 Packages
```

У меня заработала 1.0.18-2, устанавливаем её и радуемся жизни.

`apt install wlanpi-rofiler=1.0.18-2` 