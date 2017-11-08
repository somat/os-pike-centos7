## OpenStack Administration 1 - Pike - CentOS 7

Tulisan ini akan membahas tentang instalasi dan konfigurasi OpenStack Pike menggunakan distribusi Linux CentOS 7.

#### Peralatan yang digunakan

Peralatan yang digunakan di dalam praktik ini adalah sebagai berikut:

1. Laptop dengan ram 8 GB, HDD 30GB
2. Sistem operasi Linux Fedora 26
3. VirtualBox
4. ISO CentOS 7 minimal

#### Persiapan di komputer host/di laptop

Pertama kita perlu mempersiapkan laptop untuk praktik, yaitu sebagai berikut:

1. Setup ip forwarding dan NAT di komputer host

```
# firewall-cmd --direct --add-rule ipv4 nat POSTROUTING 0 -o wlp3s0 -j MASQUERADE
# firewall-cmd --direct --add-rule ipv4 filter FORWARD 0 -i vboxnet0 -o wlp3s0 -m state --state RELATED,ESTABLISHED -j ACCEPT
# firewall-cmd --direct --add-rule ipv4 filter FORWARD 0 -i vboxnet0 -o wlp3s0 -j ACCEPT
```

2. Membuat dua host-only adapter di VirtualBox
3. Membuat sebuah template mesin virtual CentOS 7

Pembahasan:

1. Persiapan
   1. Persiapan Mesin Virtual
   1. Konfigurasi Jaringan
   1. Konfigurasi NTP
   1. Install Paket OpenStack
1. Instalasi dan Konfigurasi Layanan
   1. Database
   1. Message queue
   1. Memcached
   1. Identity - Keystone
   1. Image - Glance
   1. Compute - Nova
   1. Networking - Neutron
   1. Dashboard - Horizon
   1. Block Storage - Cinder

### Referensi

* [Repository Utian](https://github.com/utianayuba/liberty-leap42)
* [Dokumentasi OpenStack Pike](https://docs.openstack.org/install-guide/)
