**a. How much data your publisher program will send to the message broker in one run?**
Program publisher akan mengirimkan tepat 5 data ke message broker dalam satu kali eksekusi.

**b. The url of: "amqp://guest:guest@localhost:5672" is the same as in the subscriber program, what does it mean?**
Artinya program publisher dan subscriber terhubung ke instance message broker RabbitMQ yang sama. Keduanya menggunakan kredensial default yang sama ('guest' sebagai username dan password) pada port yang sama ('5672'). Hal ini memastikan publisher mengirim pesan ke jalur dan antrean yang sama dengan tempat subscriber mendengarkan pesan tersebut.