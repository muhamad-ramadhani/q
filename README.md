<p style="font-size:14px" align="right">
<a href="https://t.me/PemulungAirdropID" target="_blank">Join our telegram <img src="https://user-images.githubusercontent.com/72949170/194228482-0f875615-e155-4b12-8716-8111addd6cba.jpg" width="30"/></a>
</p>

<p align="center">
  <img width="70%" height="auto" src="https://user-images.githubusercontent.com/72949170/201467990-8e240d58-4092-4a9f-b846-73b8fb7d1af8.png">
</p>

# Q BLOCKCHAIN TESTNET

|  Komponen |  Persyaratan Minimum |
| ------------ | ------------ |
| CPU  | Intel Core i3 or i5  |
| RAM | 4 GB DDR4 |
| Penyimpanan  | 500 GB HDD |
| Koneksi | 100 Mbit/s |
| OS | Ubuntu 16.04 |

Dokumen Official :
> https://docs.qtestnet.org/how-to-setup-validator/

Faucet :
> https://faucet.qtestnet.org/

Explorer : 
> https://explorer.qtestnet.org/

Validator Status :
> https://stats.qtestnet.org/

Discord
> https://discord.gg/g7zDfaMqdA


## 1. Install bahan (Kalau udah, skip aja)
- Install docker
```
apt install git docker docker-compose
```

## 2. Install Node 
```
git clone https://gitlab.com/q-dev/testnet-public-tools.git
```

## 3. Create Password
- Masuk ke directory ```testnet-validator```
```
cd testnet-public-tools/testnet-validator
```
- Buat flle untuk menyimpan password
```
mkdir keystore
```
- Buat file dan buat password kalian didalamnya
```
nano keystore/pwd.txt
```
jika sudah, tekan ```CTRL```+```X```+```Y``` lalu ```enter```

- Buat memastikan password sudah terbuat kalian bisa gunakan command ini
```
cat keystore/pwd.txt
```


## 4. Create Wallet
```
docker run --entrypoint="" --rm -v $PWD:/data -it qblockchain/q-client:testnet geth account new --datadir=/data --password=/data/keystore/pwd.txt
```

Simpan data kalian

- Klaim Faucet (ambil semuanya buat jaga2)
https://faucet.qtestnet.org/

- Konfigurasi ```.env```
```
nano .env
```
| Variabel | Detail |
|----------|------------|
| ADDRESS | Masukan address kalian (tanpa 0x didepannya) |
| IP | Masukan IP VPS kalian |

![image](https://user-images.githubusercontent.com/72949170/201468804-e91a1218-52cc-4f60-ac39-227e14b62694.png)

- Konfigurasi ```.json```
```
nano config.json
```
Ganti address & password dengan punya kalian

![image](https://user-images.githubusercontent.com/72949170/201468825-8943cdcd-162b-44c5-8a4f-f3bac0919868.png)

## 5. Stake di Contract Validator 
```
docker run --rm -v $PWD:/data -v $PWD/config.json:/build/config.json qblockchain/js-interface:testnet validators.js
```
- Daftar validator
```
nano docker-compose.yaml
```
dibagian ```entrypoint``` setelah ```geth``` tambahkan data dibawah
```
"--ethstats=VALIDATOR_NAME:TESTNET_ACCESS_KEY@stats.qtestnet.org",
```
ganti ```VALIDATOR_NAME``` jadi nama kalian
dan ganti ```TESTNET_ACCESS_KEY``` jadi punya kalian, request TESTNET_ACCESS_KEY bisa di discord,
Tanyain aja dev nya "Helo helo ser where my access key"

![image](https://user-images.githubusercontent.com/72949170/201468880-3cdb75bb-d7d8-44a4-89f4-716ef6084d02.png)

- Setelah ganti, Tekan tekan ```CTRL```+```X```+```Y``` lalu ```enter``` untuk keluar


## 6. Jalankan Validator
```
docker-compose up -d
```

untuk cek log, kalian bisa pakai command dibawah
```
docker-compose logs -f --tail "100"
```

Search nama validator kalian
https://stats.qtestnet.org/

## DONE, UNTUK UPDATE SELANJUTNYA KALIAN BISA PANTAU <a href="https://t.me/PemulungAirdropID" target="_blank">CHANNEL KITA </a>
</p>





