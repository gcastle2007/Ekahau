# Wlan PI offsets

Пока только скрипт, который запускает profiler на 1 минуту на каждом канале:

So far there is only a script that runs the profiler for 1 minute on each channel:

```
#!/usr/bin/bash
timeout -k 5 60s sudo profiler -c 1
sudo killall profiler
timeout -k 5 60s sudo profiler -c 6
sudo killall profiler
timeout -k 5 60s sudo profiler -c 11
sudo killall profiler
timeout -k 5 60s sudo profiler -c 36
sudo killall profiler
timeout -k 5 60s sudo profiler -c 40
sudo killall profiler
timeout -k 5 60s sudo profiler -c 44
sudo killall profiler
timeout -k 5 60s sudo profiler -c 48
sudo killall profiler
timeout -k 5 60s sudo profiler -c 52
sudo killall profiler
timeout -k 5 60s sudo profiler -c 56
sudo killall profiler
timeout -k 5 60s sudo profiler -c 60
sudo killall profiler
timeout -k 5 60s sudo profiler -c 64
sudo killall profiler
timeout -k 5 60s sudo profiler -c 68
sudo killall profiler
timeout -k 5 60s sudo profiler -c 132
sudo killall profiler
timeout -k 5 60s sudo profiler -c 136
sudo killall profiler
timeout -k 5 60s sudo profiler -c 140
sudo killall profiler
timeout -k 5 60s sudo profiler -c 144
sudo killall profiler
timeout -k 5 60s sudo profiler -c 149
sudo killall profiler
timeout -k 5 60s sudo profiler -c 153
sudo killall profiler
timeout -k 5 60s sudo profiler -c 157
sudo killall profiler
timeout -k 5 60s sudo profiler -c 161
sudo killall profiler
timeout -k 5 60s sudo profiler -c 165
```