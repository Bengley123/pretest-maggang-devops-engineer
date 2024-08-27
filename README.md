# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
   DevOps adalah gabungan dari filosofi kerja, praktik, dan alat yang meningkatkan kemampuan organisasi untuk memberikan aplikasi dan layanan dengan kecepatan tinggi.
2. Apa yang anda ketahui tentang Infrastructure?
   Infrastructure adalah suatu konsep yang dibangun sebagai penyokong suatu sistem yang nantinya akan berjalan untuk digunakan agar lebih baik dan pastinya efisien.
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
   Server adalah sistem yang menyediakan layanan, sumber daya, data ataupun program dari satu komputer ke komputer lainnya yang biasa disebut sebagai klien atau layanan. 
   Salah satu implementasi server sendiri adalah database yang dimana contohnhya ada MySQL, PostgreSQL, dan MariaDB. 
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
   Karena server sangat memaminkan peran kunci untuk tiap-tiap perkembangan fungsi, layanan, dan fitur yang ada pada aplikasi agar selalu efisien. Ini termasuk dalam alasan- 
   alasan yang menjadi landasan server itu penting antara lain:
   - Layanan hosting dan deployment aplikasi
   - Keamanan dan pengelolaan akses
   - Penyimpanan dan management data
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
   Virtualisasi dan container adalah teknologi yang digunakan untuk mengoptimalkan penggunaan sumber daya komputasi, meningkatkan fleksibilitas, dan menyederhanakan 
   manajemen aplikasi. Meskipun keduanya memungkinkan isolasi dan manajemen lingkungan komputasi, mereka berbeda dalam cara kerjanya dan kasus penggunaan yang paling sesuai.
   - Virtualisasi: mempunyai karakteristik antara lain hypervisor, mesin virtual (VM), punya keamanan yang tinggi, overhead yang lebih tinggi.
   - Container: mempunyai karakteristik antara lain Docker, isolasi di level OS, overhead yang rendah, punya portabilitas dan konsistensi, dan punya scalability.
6. Mengapa teknology container saat ini sangat populer?
   Teknologi container sangat populer saat ini karena menawarkan berbagai keuntungan yang membuatnya ideal untuk pengembangan dan deployment aplikasi modern. Berikut adalah 
   beberapa alasan utama mengapa container begitu diminati:
   - Portabilitas
   - Efisiensi Sumber Daya
   - Kecepatan deployment dan skalabilitas
   - Isolasi dan Konsistensi
7. Apa yang anda ketahui tentang Orchestration Container System?
   Orchestration Container System adalah sistem atau alat yang digunakan untuk mengotomatisasi manajemen, deployment, scaling, dan pengoperasian container di lingkungan 
   produksi. Saat aplikasi berjalan dalam skala besar, dengan banyak container yang saling berinteraksi, orchestration container system menjadi sangat penting untuk 
   mengelola kompleksitas ini secara efisien dan memastikan ketersediaan serta performa aplikasi.

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini

## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy
  
(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container
  - image: `dimmaryanto93/udemy-springboot-app:latest`
  - port: `8080`
  - env: 
    - `DATABASE_HOST`: `<ip-domain-db>`
    - `DATABASE_PORT`: `5432` 
    - `DATABASE_NAME`: `<db-name>`
    - `DATABASE_PASSWORD`: `<db-password>`
    - `APPLICATION_PORT`: `8080`
  need:
    - Database PostgreSQL v14.2
2. Frontend container
  - image: `dimmaryanto93/udemy-angular-app:latest`
  - port: `80`
  - env:
    - `APPLICATION_PORT`: `80`
    - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
    - `BACKEND_HOST`: `<ip-backend-apps>`
    - `BACKEND_PORT`: `<port-backend-apps>`
    - `BACKEND_CONTEXT_PATH`: `/`
  - need:
    - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`

