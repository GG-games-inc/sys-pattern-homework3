# Домашнее задание к занятию "`Кластеризация и балансировка нагрузки`" - `Белолипецкий Леонид`

---

### Задание 1

```bash
global
    log /dev/log    local0
    log /dev/log    local1 notice
    chroot /var/lib/haproxy
    stats socket /run/haproxy/admin.sock mode 660 level admin
    stats timeout 30s
    user haproxy
    group haproxy

defaults
    log     global
    mode    tcp
    option  tcplog
    option  dontlognull
    timeout connect 5000
    timeout client  50000
    timeout server  50000

listen web_tcp
    bind :8080
    mode tcp
    balance roundrobin
    server s1 127.0.0.1:8888 check
    server s2 127.0.0.1:9999 check

listen stats
    bind :9000
    mode http
    stats enable
    stats uri /stats
    stats refresh 5s
```

![img](img/img1.png)

![img](img/img2.png)

---

### Задание 2

```
Поле для вставки кода...
....
....
....
....
```

![Название скриншота 2](ссылка на скриншот 2)`

