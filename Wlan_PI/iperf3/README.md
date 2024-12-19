# Вариант запуска iperf3 для обработки запросов сразу от нескольких клиентов на разных портах, через ngix.

```
sudo tee /usr/share/nginx/modules/iperf.conf << 'EOF'
load_module "/usr/lib64/nginx/modules/ngx_stream_module.so";

stream {
    server {
        listen                  192.168.1.2:5201 so_keepalive=on;
        proxy_pass              tcp;
        proxy_buffer_size 128k;
    }

    upstream tcp {
        hash $remote_addr;
        server 127.0.0.1:5202 max_conns=1;
        server 127.0.0.1:5203 max_conns=1;
        server 127.0.0.1:5204 max_conns=1;
        server 127.0.0.1:5205 max_conns=1;
        server 127.0.0.1:5206 max_conns=1;
        server 127.0.0.1:5207 max_conns=1;
        server 127.0.0.1:5208 max_conns=1;
        server 127.0.0.1:5209 max_conns=1;
    }

}
EOF

sudo systemctl restart nginx
sudo killall iperf3

for port in {5202..5209}; do
    iperf3 --server --port $port --logfile /home/adner/iperf.log --daemon --idle-timeout 2
done
```
(c) @c60acf23