# Домашнее задание к занятию "`10.1 «Keepalived/vrrp»`" - `Макевкин Савелий`

---

### Задание 1
MASTER 
```
vrrp_instance test {

state MASTER

interface enp0s3

virtual_router_id 10

priority 110

advert_int 4

authentication {

auth_type AH

auth_pass 1111

}

unicast_peer {

192.168.31.172

}

virtual_ipaddress {

192.168.31.90 dev enp0s3 label enp0s3:vip

}

}

```


BACKUP
```
vrrp_instance test {

state BACKUP

interface enp0s3

virtual_router_id 10

priority 90

advert_int 4
authentication {

auth_type AH

auth_pass 1111

}

unicast_peer {

192.168.31.207

}

virtual_ipaddress {

192.168.31.90 dev enp0s3 label enp0s3:vip

}

}

```

MASTER

![z1](https://github.com/smakevkin/10-01-hw/blob/main/1.png)




BACKUP

![z2](https://github.com/smakevkin/10-01-hw/blob/main/2.png)


https://user-images.githubusercontent.com/50344064/230801286-ff5fe6b8-372b-4fd7-a75f-8c7bd0e2d135.mp4

