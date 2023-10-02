<h1 align="center">Laporan Projek Akhir <br> Komunikasi Data dan Jaringan Komputer <br> Kelompok 4 - Paralel 3</h1>

# Anggota
<table>
    <thead>
        <tr>
            <th></th>
            <th>Nama</th>
            <th>Nim</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>RAISYA SHINTA SIREGAR</td>
            <td>G6401211010</td>
        </tr>
        <tr>
            <td>2</td>
            <td>ANNADIA DWINA HAQIQI</td>
            <td>G6401211019</td>
        </tr>
        <tr>
            <td>3</td>
            <td>FAIZUSSABIQ KHOIRI</td>
            <td>G6401211021</td>
        </tr>
        <tr>
            <td>4</td>
            <td>ANDHIKA RAFI LAZUARDI</td>
            <td>G6401211139</td>
        </tr>
</tbody>
</table>


---


# Nullboard
Original repository : https://github.com/rsoper/nullboard

Web official : https://nullboard.io/preview

**Nullboard** adalah tampilan minimalis pada papan kanban / pengelola daftar tugas, dirancang agar ringkas, mudah dibaca, dan cepat digunakan.


**Nullboard** memiliki fitur sebagai berikut :
- Membuat, menambahkan, serta menghapus notes
- Menambahkan board baru serta menghapus board yang ada
- Export dan Import Board
- Auto-backup
- UI Preferences (Color theme, Font size, Font option)
- Undo/redo untuk 50 kali revisi per board


Berikut merupakan kelebihan yang dimiliki oleh **Nullboard** :
- Single-page web app (hanya satu file HTML, paket jQuery kuno, dan paket font web)
- Dapat digunakan saat offline (komputer tidak terhubung dengan jaringan)
- Semua data disimpan pada penyimpanan lokal
- Memiliki Keyboard shortcuts, termasuk Tab'ing melalui notes
- Mendukung multiple boards dengan near-instant switching


Beberapa kekurangan yang masih dimiliki oleh **Nullboard** :
- Hanya dicoba pada Firefox and Chrome, belum dicoba pada Safari dan Microsoft Edge
- Harus berhati-hati saat membersihkan cache karena menggunakan penyimpanan lokal
- User Experience masih sangat kurang jika dibuka menggunakan mobile device (tap/touch input), karena Nullboard dibuat untuk penggunaan Keyboard/Mouse
  

**Nullboard** juga dapat dijalankan pada semua sistem yang dapat menjalankan Docker :
- Windows6
- macOS
- Linux

---
# Instalasi
Kami menginstall aplikasi pada VM lokal (menggunakan vps azure) sistem operasi yang digunakan adalah Ubuntu 22.04.2.0 LTS

#### Kebutuhan Sistem :
- Linux atau Windows.
- HTML
- Docker

#### Proses Instalasi :
**1. Git clone kemudian run docker.**
    ```
    docker-compose up -d
    ```

**2. Membuat VPS**

   a. Login pada website [Azure](https://azure.microsoft.com/).

   b. Akses Portal Azure for Students, kemudian pilih Start free.

   c. Isi identitas kemudian selesaikan puzzle yang tersedia, dan pilih Verify academic status pada halaman Student Verification.

   d. Lanjutkan semua proses yang ada dan isi data sesuai dengan apa yang diminta.

   e. Jika proses verifikasi berhasil, maka akan otomatis diarahkan ke halaman Azure Education Dashboard dan bisa mulai menggunakan layanan Azure dengan credit sebesar $100 atau selama 365 hari secara gratis.

   f. Kemudian create resource group (scope access control for administrative actions).

   g. Lalu create server ubuntu 22.04 menggunakan resource group yang berhasil dibuat sebelumnya.

**3. Set up SSH**

Login kedalam server menggunakan SSH.

 ```
 $ ssh dhika@74.249.96.197
 ```

**4. Set up Docker di VPS**

berikut merupakan langkah-langkah penginstallan Docker:
```
$ sudo apt update
$ sudo apt install apt-transport-https ca-certificates curl software-properties-common
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
$ sudo apt update
$ sudo apt install docker-ce
$ sudo systemctl status docker
$ sudo usermod -aG docker  ${USER}
$ su - ${USER}
$ docker ps
```

**5. Deploy Doker ke VPS**

Setelah selesai menginstall Docker, selanjutnya Create Compose dengan cara membuat folder melalui terminal dengan command berikut:
```
$ mkdir nullboard
$ cd nullboard
$ nano docker-compose.yml
```

selanjutnya copy code yang ada pada docker-compose.yml tersebut dan paste ke terminal.

lalu ctrl+S dan ctrl+X (save dan exit).

kemudian tuliskan perintah berikut pada terminal dan tunggu hingga selesai (webapp berhasil di-deploy)
```
$ docker compose up -d --build
```






   

