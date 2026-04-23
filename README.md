# Hello Rust Web Server

## Commit 1 Reflection Notes

Pada milestone ini, saya mempelajari pembuatan web server sederhana (single-threaded) menggunakan Rust.
Method `handle_connection` digunakan untuk membaca request dari browser melalui TCP stream. Untuk membaca data secara efisien, digunakan `BufReader` yang memproses stream baris per baris.
Request HTTP yang diterima direpresentasikan sebagai vector of strings, yang berisi informasi seperti method (GET/POST), path, host, dan headers lainnya.
Setiap kali browser mengakses server, `handle_connection` akan dipanggil dan isi request akan ditampilkan ke terminal. Dari situ bisa dilihat bagaimana alur dasar komunikasi antara client dan server terjadi.

## Commit 2 Reflection Notes

![Commit 2 screen capture](commit2.png)
Pada milestone ini, server ditambahkan kemampuan untuk mengirim response HTML ke browser.
Method `handle_connection` diperbarui dengan membaca file menggunakan `fs::read_to_string("hello.html")`. Response HTTP kemudian disusun dari beberapa bagian: status line (`HTTP/1.1 200 OK`), header `Content-Length`, dan body berupa isi HTML.
Format response harus mengikuti standar HTTP, yaitu setiap bagian dipisahkan dengan `\r\n`.
Setelah itu, `stream.write_all()` digunakan untuk mengirim response ke browser, sehingga halaman HTML dapat dirender. Dari situ bisa dilihat bagaimana server mulai tidak hanya menerima request, tapi juga memberikan response yang sesuai.