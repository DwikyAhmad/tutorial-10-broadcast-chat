# 2.1. Original code of broadcast chat.
![image1](/img/image1.png)
Untuk mejalankan program tersebut, pada terminal akan dieksekusi `cargo run --bin server` sebagai server dan tiga client dijalankan menggunakan perintah `cargo run --bin client`, tiga client tersebut terhubung pada server yang sama dengan port yang berbeda, saat teks diberikan melalui client, maka server akan menerima teks tersebut dan melakukan broadcast ke seluruh client yang terhubung dengan server.

# 2.2. Modifying the websocket port
![image2](/img/image2.png)
Saat memodifikasi port pada sisi client, maka pada program server juga perlu dilakukan modifikasi portnya menjadi 8080 pada bagian TCP Listener, hal ini membuat server dan client dapat terhubung dengan koneksi websocket yang sama dengan port yang berbeda dari sebelumnya.

# 2.3. Small changes. Add some information to client
![image3](/img/image3.png)
Pada src/bin/server.rs, mengubah line `bcast_tx.send(text.into())?;` menjadi `bcast_tx.send(format!("{:?}: {}", addr, text))?;` dengan ini messsage yang di broadcast tidak hanya text message, tetapi address dari client yang mengirimkan teks tersebut akan ikut di broadcast juga, lalu pada src/bin/client.rs line `println!("From server: {}", text);` diubah menjadi `println!("Dwiky's Computer - From Server: {}", text);` untuk modifikasi mengikuti tutorial.