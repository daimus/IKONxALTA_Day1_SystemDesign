# Query

## Redis
Redis merupakan dictionary based database (berbeda dengan SQL). Ia menyimpan data dalam pasangan key-value. Sehingga untuk melakukan padanan query seperti pada soal terlebih dahulu harus mengetahui bagaimana data tersebut disimpan.
1. Jika semua data users disimpan kedalam 1 pasangan key-value (value dalam bentuk JSON, CSV, etc), maka untuk mendapatkan semua data users dapat dilakukan dengan
```
GET users
```
2. Jika semua data dalam redis merupakan data users, maka untuk mendapatkan data mula-mula perlu dicari semua key
```
KEYS *
```
kemudian get semua value berdasarkan key tersebut dengan
```
MGET key1 [...key2]
```

Namun kasus kedua menurut saya jarang dan tidak cocok digunakan. Kasus pertama lebih cocok dan sering digunakan untuk membantu mempercepat (caching) database utama atau 3rd party application.

## Neo4j
Neo4j merupakan graph based database, dimana data disimpan dalam bentuk node dan dapat divisualisasikan untuk menggambarkan hubungan antar node. Untuk mendapatkan semua node user, dapat dilakukan dengan
```
MATCH (users:Users)
RETURN users;
```

## Cassandra