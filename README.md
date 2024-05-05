![image1](/img/image1.png)
Untuk mejalankan program tersebut, pada terminal akan dieksekusi `cargo run --bin server` sebagai server dan tiga client dijalankan menggunakan perintah `cargo run --bin client`, tiga client tersebut terhubung pada server yang sama dengan port yang berbeda, saat teks diberikan melalui client, maka server akan menerima teks tersebut dan melakukan broadcast ke seluruh client yang terhubung dengan server.

![image2](/img/image2.png)
Saat memodifikasi port pada sisi client, maka pada program server juga perlu dilakukan modifikasi portnya menjadi 8080 pada bagian TCP Listener, hal ini membuat server dan client dapat terhubung dengan koneksi websocket yang sama dengan port yang berbeda dari sebelumnya.