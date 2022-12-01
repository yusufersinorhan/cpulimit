# cpulimit
Birden fazla node kurulumunda ya da çok yüksek cpu tüketimini yapan mining işlemlerinde CPU kullanımını limitleme rehberi. 

### CPULIMIT PROGRAMI KURULUMU
```
sudo apt install cpulimit
```

### YÜKSEK KULLANIM YAPAN PROGRAMI BULMAK
```
htop
```
htop komutu ile resimdeki ekranı açıyoruz. Kırmızı kutu içine aldığım kısımda her programın künye numarası olan "PID" numarasını görüyoruz. Mavi kutu içinde ise programın çalıştırıldığı ana komut neyse onu görüyoruz. 


![image](https://github.com/yusufersinorhan/cpulimit/blob/main/cpulimitleme.jpg)


### SCREEN AÇALIM
```
screen -S cpulimit
```

Bu ekran da birkaç farklı şekilde limitleme yapabiliyoruz;

-PID numarasıyla limitleme (ben şimdilik bunu kullanıyorum)

-Klasör bazlı limitleme

-Komut bazlı limitleme

İstediğinizi seçebilirsiniz. 



### PID NUMARASIYLA CPU KULLANIMI LİMİTLEME
```
cpulimit -p 30393 -l 40
```
30393 pid kodlu programı %40 cpu kullanacak şekilde limitleyeceğiz. Buradaki yüzdeyi siz istediğiniz gibi değiştirebilirsiniz. Uzi miner yeni problemi bulduğu anda anlık pik yükselişler olabilir ancak cpulimit 1-2 sn içinde tekrar kontrolü ele geçiriyor ve limitliyor.



### KLASÖR BAZLI CPU KULLANIMI LİMİTLEME
```
cpulimit -P $HOME/uzi-miner -l 40
```
$HOME/uzi-miner klasörü içinde çalıştırılacak programların cpu kullanımını %40 da limitler.



### KOMUT BAZLI KULLANIMI LİMİTLEME
```
cpulimit -e uzi-miner -l 40
```

uzi-miner komutu altında çalışan ( resimde mavi dikdörtgen içine aldığım kısım ) programın cpu kullanımını %40 da limitler.


Buradan istediğiniz limitleme yöntemini seçin uygulayın 





