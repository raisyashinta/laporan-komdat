<h1 align="center">Laporan Projek Akhir <br> Komunikasi Data dan Jaringan Komputer <br> Kelompok 4 - Paralel 3</h1>

### Anggota
<table>
    <thead>
        <tr>
            <th></th>
            <th>NAMA</th>
            <th>NIM</th>
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

# Aplikasi Web "Nullboard"
## Sekilas tentang Nullboard
**Nullboard** adalah papan kanban / pengelola daftar tugas yang memiliki tampilan minimalis, dirancang agar ringkas, mudah dibaca, dan cepat digunakan oleh pengguna. Nullboard memungkinkan pengguna nya menuliskan daftar tugas yang dimilki dan menyesuaikan sesuai dengan masing-masing board yang dibuat.

Original repository: https://github.com/rsoper/nullboard

Web official: https://nullboard.io/preview

---
## Instalasi
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
![image](https://github.com/raisyashinta/laporan-komdat/assets/90228957/d89fc21e-82c8-406e-8994-851c3dbbcef0)


**2. Membuat VPS**

   a. Login pada website [Azure](https://azure.microsoft.com/).

   b. Akses Portal Azure for Students, kemudian pilih Start free.

   c. Isi identitas kemudian selesaikan puzzle yang tersedia, dan pilih Verify academic status pada halaman Student Verification.

   d. Lanjutkan semua proses yang ada dan isi data sesuai dengan apa yang diminta.

   e. Jika proses verifikasi berhasil, maka akan otomatis diarahkan ke halaman Azure Education Dashboard dan bisa mulai menggunakan layanan Azure dengan credit sebesar $100 atau selama 365 hari secara gratis.

   f. Kemudian create resource (scope access control for administrative actions).
   
   ![image](https://github.com/raisyashinta/laporan-komdat/assets/90228957/10c66e13-0977-47c4-aad8-3d58b3d03d3e)


   g. Lalu create virtual machine menggunakan resource yang berhasil dibuat sebelumnya.
   
   ![image](https://github.com/raisyashinta/laporan-komdat/assets/90228957/12ec19ac-2ccc-4ec5-874d-c505f4e3721b)


   h. Setting konfigurasi menggunakan password agar lebih mudah. Masukkan username dan password.
   
   ![image](https://github.com/raisyashinta/laporan-komdat/assets/90228957/4bdc21cb-8102-4bd2-94e0-42a13a958c74)


   i. Pada tab networking, pilih semua port yang ada.
   
   ![image](https://github.com/raisyashinta/laporan-komdat/assets/90228957/5eee7adc-0283-4c55-a809-113c797c7d07)


   j. Kemudian review + create. Setelah selesai melakukan review, langsung klik create.
   
   ![image](https://github.com/raisyashinta/laporan-komdat/assets/90228957/2feedfa6-160a-4833-98a3-710aca7352a4)


   k. Jika semua tahapan berhasil di lakukan, maka berhasil masuk ke vm dengan tampilan sebagai berikut.
   
   ![image](https://github.com/raisyashinta/laporan-komdat/assets/90228957/fdfab62e-91ed-4bc8-9a8e-6f082862504a)




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

**5. Deploy Docker ke VPS**

Setelah selesai menginstall Docker, selanjutnya Create Compose dengan cara membuat folder melalui terminal dengan command berikut:
```
$ mkdir nullboard
$ cd nullboard
$ nano docker-compose.yml
```
![image](https://github.com/raisyashinta/laporan-komdat/assets/90228957/32531865-7131-4dd2-a059-82817adeb03f)


selanjutnya copy code yang ada pada docker-compose.yml tersebut dan paste ke terminal.

lalu ctrl+S dan ctrl+X (save dan exit).

kemudian tuliskan perintah berikut pada terminal dan tunggu hingga selesai (webapp berhasil di-deploy)
```
$ docker compose up -d --build
```

---
## Cara Pemakaian
Cara pemakaian Nullboard ini sangat mudah, karena Webapp ini telah menyediakan interface yang mudah dimengerti dan pengguna juga tidak perlu melakukan sign up/sign in pada aplikasi ini.

**Nullboard** juga dapat dijalankan pada semua sistem yang dapat menjalankan Docker :
- Windows6
- macOS
- Linux


Berikut merupakan tampilan saat pengguna pertama kali mengakses Nullboard:
![image](https://github.com/raisyashinta/laporan-komdat/assets/90228957/42fef0f9-753a-407d-a7e8-497da9d1d534)


**Nullboard** memiliki fitur sebagai berikut :
- Membuat, menambahkan, serta menghapus notes
- Menambahkan board baru serta menghapus board yang ada
  ![Screenshot (875)](https://github.com/raisyashinta/laporan-komdat/assets/90228957/7eb8d070-35d7-4dbd-8b87-9e343a79a6b3)
- Export dan Import Board
- Auto-backup
- UI Preferences (Color theme, Font size)
- ![image](https://github.com/raisyashinta/laporan-komdat/assets/90228957/0e883edf-110e-4a9c-9ba2-2489791cf4f5)
- Undo/redo untuk 50 kali revisi per board

Berikut tampilan Nullboard (light mode) saat pengguna menuliskan task kepanitiaan nya:
![image](https://github.com/raisyashinta/laporan-komdat/assets/90228957/a443e265-1188-4465-9cd6-272ca01efb0d)

Berikut tampilan Nullboard (dark mode) saat pengguna menuliskan task kepanitiaan nya:
![image](https://github.com/raisyashinta/laporan-komdat/assets/90228957/304194e0-4125-4cab-a828-0f0c5cfa4ff0)

---
## Pembahasan
Nullboard adalah sebuah Webapp yang sangat mudah dan praktis untuk digunakan dalam pencatatan task terutama bagi seorang product manager saat sedang dalam tahap pengembangan sebuah product bersama tim pengembang lain.


Berikut merupakan kelebihan yang dimiliki oleh **Nullboard** :
- Single-page web app (hanya satu file HTML, paket jQuery kuno, dan paket font web)
- Mudah dipahami oleh penggguna
- Semua data disimpan pada penyimpanan lokal
- Memiliki Keyboard shortcuts, termasuk Tab'ing melalui notes
- Mendukung multiple boards dengan near-instant switching
- Memiliki opsi dark dan light theme  


Beberapa kekurangan yang masih dimiliki oleh **Nullboard** :
- Hanya dicoba pada Firefox and Chrome, belum dicoba pada Safari dan Microsoft Edge
- Harus berhati-hati saat membersihkan cache karena menggunakan penyimpanan lokal
- Karena penyimpanan lokal, maka jika pengguna membuka Nullboard menggunakan browser yang berbeda maka data akan berbeda juga
- Jika pengguna membuka Nullboard pada browser yang sama, namun pada akun yang berbeda maka data akan berbeda juga
- User Experience masih sangat kurang jika dibuka menggunakan mobile device (tap/touch input), karena Nullboard dibuat untuk penggunaan Keyboard/Mouse

**Nullboard vs Wekan**

- Antarmuka Pengguna (UI/UX)
  
Nullboard: menawarkan antarmuka pengguna yang sangat sederhana dan minimalis, sehingga tidak membingungkan dengan cukup banyak fitur tambahan.

Wekan: memiliki antarmuka yang lebih lengkap dan fitur yang lebih lengkap, namun thal tersebut membuatnya terasa lambat. 

- Fitur-fitur Tambahan
  
Nullboard: tidak memiliki integrasi pihak ketiga yang kuat dan penyimpanan lokal sehingga tidak bergantung pada cloud.

Wekan: memiliki integrasi dengan pihak ketiga seperti Dropbox, dan integrasi webhook untuk mengatur izin akses lebih rinci. Wekan juga tidak memiliki opsi penyimpanan lokal di komputer, sehingga memiliki ketergantungan pada server atau cloud.

- Skalabilitas Proyek
  
Nullboard: cocok digunakan untuk proyek kecil hingga menengah karena memiliki fitur yang sederhana dan terbatas.

Wekan: cocok igunakan dalam proyek-proyek besar dengan jumlah tim yang lebih banyak karena memiliki lebih banyak fitur dan fleksibel.

---
## Referensi

[Nullboard](https://github.com/rsoper/nullboard)

[Informasi Layanan Microsoft Azure](https://servicedesk.telkomuniversity.ac.id/faq/informasi-layanan-microsoft-azure-telkom-university/)

[How To Deploy Docker In Ubuntu Server Using Azure Portal](https://www.c-sharpcorner.com/article/how-to-deploy-docker-in-ubuntu-server-using-azure-portal/)

[Docker: Pengenalan dan Cara Install Docker pada VPS Ubuntu](https://jagoweb.com/docker--pengenalan-dan-cara-install-docker-pada-vps-ubuntu)

[WeKan](https://wekan-github-io.translate.goog/?_x_tr_sl=en&_x_tr_tl=id&_x_tr_hl=id&_x_tr_pto=tc)
