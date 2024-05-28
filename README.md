# docker-webserver
1. Pastikan docker sudah terinstall di server
2. buat directory difolder mana saja, dengan nama bebas ```mkdir docker-webserver```
3. masuk ke directory yang baru saja anda buat ```cd docker-webserver```
4. buat file Docker file dengan perintah ```nano Dockerfile```
5. copy script ini di Dockerfile
   ```
   FROM arm64v8/php:8.2-apache
   WORKDIR /var/www/html
   RUN apt-get update && apt-get install -y \
    nano \
    && rm -rf /var/lib/apt/lists/*
   XPOSE 80
   ```
6. simpan file tersebut dengan menekan tombol CTRL+O dan keluar dari text editor nano dengan menekan tombol CTRL+X
7. jalankan file Dockerfile untuk membuat images dengan ```docker-build -t webserver:1.0 .```
