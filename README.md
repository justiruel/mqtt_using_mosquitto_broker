keterangan :
+ client id : di isi terserah yang penting unik, jika kebetulan sama maka salah satu client akan di reject

# instalasi Mosquitto broker
https://medium.com/@shikhar022/steps-to-install-mosquitto-broker-on-windows-10-aec2141d962c

# untuk uji coba gunakan mqtt client : http://workswithweb.com/html/mqttbox/installing_apps.html#install_on_windows


# langkah tambah password mosquitto  (ref http://www.steves-internet-guide.com/mqtt-username-password-example/):

+ buat file C:\Program Files (x86)\mosquitto\pwdfile.txt isi :
```
user:root
```
+ run : mosquitto_passwd -U pwdfile.txt  , maka pwdfile.txt berubah begini :
```
user:$6$u8S1B9Lc7Kl8A1sN$NLEvwE3yyI3cVcCrM1Skkft4cZAMCSU9Ww+ARAIVDnYuWmppxvvIKl7SpeDWQwtQRzO+a1Kgl35g5nO4Sibr+A==
```
+ buka buat file C:\Program Files (x86)\mosquitto\mosquitto.conf, tambahkan :
```
allow_anonymous false
password_file C:\Program Files (x86)\mosquitto\pwdfile.txt
```
+ run services.msc, restart mosquitto




# di laravel, pakai library : https://packagist.org/packages/bluerhinos/phpmqtt

