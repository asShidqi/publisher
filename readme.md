a. jumlah data yang dikirim oleh program adalah 5
b. artinya adalah baik publisher maupun subscriber terhubung ke server RabbitMQ yang sama

![alt text](image.png)

![alt text](image-1.png)
Ketika saya menjalankan perintah cargo run pada publisher, program akan mengirim 5 buah event bertipe UserCreatedEventMessage ke message broker (RabbitMQ).
Setiap event berisi data seperti user_id dan user_name.
Kemudian, program subscriber yang sudah aktif sebelumnya akan menerima dan memproses semua event tersebut melalui queue bernama user_created.

![alt text](image-2.png)
Lonjakan (spike) yang terlihat pada chart menunjukkan adanya peningkatan jumlah pesan yang tiba-tiba di message broker.

Spike ini terjadi setiap kali saya menjalankan kembali publisher dengan cargo run