# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
2. Apa yang anda ketahui tentang Infrastructure?
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
6. Mengapa teknology container saat ini sangat populer?
7. Apa yang anda ketahui tentang Orchestration Container System?

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini

1. DevOps merupakan peran dalam pengembangan software yang dimana menjadi penengah antara Developer dan Operations. DevOps dibuat untuk automation dan integration agar mempersingkat tahap pengembangan software.
2. Infrastruktur adalah fasilitas yang digunakan oleh developer untuk mendeploy software. Infrastruktur biasanya terdiri dari Hardware(Server) dan Software(OS).
3. Server merupakan sistem komputer yang digunakan untuk menyimpan data dan memberi data yang dibutuhkan oleh client. Beberapa implementasi dari server antara lain Web server (web hosting), Database server (mengelola data), Mail server (mengelola email), dll.
4. Server dalam development biasanya digunakan untuk menyamakan environment tiap developer agar pada saat dilakukan automation(CI/CD), software yang dikembangkan yang kemungkinan bisa cacat tidak langsung terdeploy.
5. Virtualisasi adalah pembagian resource hardware yang digunakan untuk membuat sistem komputer baru di hardware yang sama namun lingkungan sistem komputer yang terpisah. Sedangkan Container hampir sama dengan VM namun resources yang dibagi bergantung pada kebutuhan program yang berjalan di virtual OS tersebut.
6. Container sangat populer digunakan dikarenakan scaling dalam membuat virtual OS yang cepat dan efisien.
7. Orchestration Container System digunakan untuk scheduling microsevice agar resource dengan workload yang digunakan efisien. Salah satu contoh softwarenya adalah Kubernetes yang didesain utnuk menjalankan container dengan jumlah besar.

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

