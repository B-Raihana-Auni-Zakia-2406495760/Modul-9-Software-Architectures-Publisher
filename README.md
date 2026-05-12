**a. How much data your publisher program will send to the message broker in one run?**
Program publisher akan mengirimkan tepat 5 data ke message broker dalam satu kali eksekusi.

**b. The url of: "amqp://guest:guest@localhost:5672" is the same as in the subscriber program, what does it mean?**
Artinya program publisher dan subscriber terhubung ke instance message broker RabbitMQ yang sama. Keduanya menggunakan kredensial default yang sama ('guest' sebagai username dan password) pada port yang sama ('5672'). Hal ini memastikan publisher mengirim pesan ke jalur dan antrean yang sama dengan tempat subscriber mendengarkan pesan tersebut.

![RabbitMQ Setup](rabbitmq.png)

![Console Output](console.png)
Penjelasan: Saat menjalankan program publisher, program tersebut mengirimkan 5 event ke message broker. Program subscriber, yang secara aktif listening pada queue, langsung mengonsumsi dan memproses event-event tersebut, lalu mencetak detailnya ke layar konsol.

![Chart Spikes](spike.png)
Penjelasan: spikes pada grafik RabbitMQ terjadi karena publisher mengirimkan beberapa pesan ke dalam queue jauh lebih cepat dibandingkan kondisi idle normal. Setiap kali publisher dijalankan, message rate melonjak drastis dalam waktu singkat, menyebabkan puncak yang terlihat jelas pada grafik "Message rates" sebelum akhirnya kembali turun ke angka nol.