# Hello Rust Web Server

## Commit 1 Reflection Notes

Pada milestone ini, saya mempelajari pembuatan web server sederhana (single-threaded) menggunakan Rust.
Method `handle_connection` digunakan untuk membaca request dari browser melalui TCP stream. Untuk membaca data secara efisien, digunakan `BufReader` yang memproses stream baris per baris.
Request HTTP yang diterima direpresentasikan sebagai vector of strings, yang berisi informasi seperti method (GET/POST), path, host, dan headers lainnya.
Setiap kali browser mengakses server, `handle_connection` akan dipanggil dan isi request akan ditampilkan ke terminal. Dari situ bisa dilihat bagaimana alur dasar komunikasi antara client dan server terjadi.