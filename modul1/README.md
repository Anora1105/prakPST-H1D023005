## Modul 1 – Percabangan dan Perulangan  
Nama : Ariza Nola Rufiana  
NIM  : H1D023005  

---

# 1.5.4 Pertanyaan Praktikum (Percabangan)

## 1. Pada kondisi apa program masuk ke blok `if`?

Program akan masuk ke blok **if** ketika nilai variabel `timeDelay` **kurang dari atau sama dengan 100**.

Pada kondisi ini, program memberikan jeda selama 3000 milidetik, kemudian nilai `timeDelay` dikembalikan menjadi 1000 milidetik sehingga LED kembali berkedip lambat.

---

## 2. Pada kondisi apa program masuk ke blok `else`?

Program akan masuk ke blok **else** ketika nilai `timeDelay` **masih lebih dari 100**.

Pada kondisi ini, nilai `timeDelay` akan dikurangi sebesar 100 milidetik setiap siklus sehingga LED akan berkedip semakin cepat.

---

## 3. Apa fungsi dari perintah `delay(timeDelay)`?

Perintah `delay(timeDelay)` digunakan untuk memberikan jeda waktu dalam satuan milidetik sebelum program melanjutkan ke perintah berikutnya.

Nilai `timeDelay` menentukan kecepatan kedip LED. Jika nilai delay besar maka LED berkedip lambat, sedangkan jika nilai delay kecil maka LED berkedip cepat.

---

## 4. Modifikasi Program  
### Alur: cepat → sedang → mati

Program berikut dibuat agar LED tidak langsung reset, tetapi berubah dari cepat, kemudian sedang, lalu mati.

Oke paham 👍
Jadi untuk **bagian perulangan (1.6.4)** kamu ingin **format sama persis seperti contoh percabangan**: rapi, paragraf penjelasan biasa, lalu kode program di bawahnya. Aku buat konsisten dengan gaya yang sudah kamu pakai.

---

## Modul 1 – Percabangan dan Perulangan

**Nama : Ariza Nola Rufiana**
**NIM  : H1D023005**

---

# **1.6.4 Pertanyaan Praktikum (Perulangan)**

## **1. Gambarkan rangkaian schematic 5 LED running yang digunakan pada percobaan!**

Rangkaian LED running dibuat dengan menghubungkan lima LED ke pin digital Arduino secara berurutan. Setiap LED dihubungkan melalui resistor sebelum menuju GND agar arus yang masuk ke LED tidak berlebihan.

Susunan rangkaian yang digunakan adalah sebagai berikut:

Pin 2 → Resistor → LED 1 → GND
Pin 3 → Resistor → LED 2 → GND
Pin 4 → Resistor → LED 3 → GND
Pin 5 → Resistor → LED 4 → GND
Pin 6 → Resistor → LED 5 → GND

Dengan susunan tersebut, setiap LED dapat dikontrol secara bergantian menggunakan program perulangan sehingga menghasilkan efek LED berjalan.

---

## **2. Jelaskan bagaimana program membuat efek LED berjalan dari kiri ke kanan!**

Efek LED berjalan dari kiri ke kanan dibuat menggunakan **perulangan for** yang dimulai dari pin paling kecil menuju pin paling besar. Program akan menyalakan LED satu per satu dimulai dari pin 2 sampai pin 6, kemudian mematikannya sebelum melanjutkan ke LED berikutnya.

Dengan adanya jeda waktu (`delay`), perpindahan nyala LED dapat terlihat seperti bergerak dari kiri ke kanan.

Contoh kode:

```cpp
for (int ledPin = 2; ledPin <= 6; ledPin++) {

  digitalWrite(ledPin, HIGH);
  delay(timer);

  digitalWrite(ledPin, LOW);

}
```

---

## **3. Jelaskan bagaimana program membuat LED kembali dari kanan ke kiri!**

Setelah LED selesai menyala dari kiri ke kanan, program menggunakan perulangan `for` kedua yang berjalan secara mundur dari pin terbesar menuju pin terkecil.

Dengan demikian, LED akan menyala kembali dari kanan ke kiri sehingga menghasilkan efek bolak-balik.

Contoh kode:

```cpp
for (int ledPin = 6; ledPin >= 2; ledPin--) {

  digitalWrite(ledPin, HIGH);
  delay(timer);

  digitalWrite(ledPin, LOW);

}
```

---

## **4. Buatkan program agar LED menyala tiga LED kanan dan tiga LED kiri secara bergantian**

Program berikut dibuat untuk menyalakan **tiga LED bagian kiri** terlebih dahulu, kemudian **tiga LED bagian kanan**, secara bergantian dengan jeda waktu tertentu.

### **Program Arduino**

```cpp
int timer = 300;

void setup() {

  pinMode(2, OUTPUT);
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(6, OUTPUT);
  pinMode(7, OUTPUT);

}

void loop() {

  // Menyalakan 3 LED kiri
  digitalWrite(2, HIGH);
  digitalWrite(3, HIGH);
  digitalWrite(4, HIGH);

  // Mematikan 3 LED kanan
  digitalWrite(5, LOW);
  digitalWrite(6, LOW);
  digitalWrite(7, LOW);

  delay(timer);

  // Mematikan 3 LED kiri
  digitalWrite(2, LOW);
  digitalWrite(3, LOW);
  digitalWrite(4, LOW);

  // Menyalakan 3 LED kanan
  digitalWrite(5, HIGH);
  digitalWrite(6, HIGH);
  digitalWrite(7, HIGH);

  delay(timer);

}
```

---

### **Penjelasan Program**

Program dimulai dengan mendeklarasikan variabel `timer` yang berfungsi untuk mengatur waktu jeda antar pergantian LED. Pada bagian `setup()`, semua pin dari 2 hingga 7 diatur sebagai output agar dapat digunakan untuk mengontrol LED.

Pada bagian `loop()`, program pertama-tama menyalakan tiga LED kiri yaitu pada pin 2, 3, dan 4, sedangkan LED kanan dimatikan. Setelah jeda waktu tertentu, LED kiri dimatikan dan LED kanan pada pin 5, 6, dan 7 dinyalakan.

Proses ini berlangsung terus-menerus sehingga menghasilkan efek LED kiri dan kanan menyala secara bergantian.

Siap, kita lanjut **Bagian 1.7 Pertanyaan Analisis** dengan **format sama seperti sebelumnya** supaya konsisten dengan laporanmu. Bahasanya aku buat **natural, seperti laporan praktikum**, bukan seperti menjawab soal langsung.

---

# **1.7 Pertanyaan Analisis**

## **1. Uraikan hasil tugas pada praktikum yang telah dilakukan pada setiap percobaan!**

Pada praktikum yang telah dilakukan, terdapat dua jenis percobaan yaitu percobaan percabangan dan percobaan perulangan. Pada percobaan percabangan, LED berhasil menyala dan mati dengan waktu kedip yang berubah secara bertahap. Awalnya LED berkedip dengan waktu yang relatif lambat, kemudian semakin cepat seiring berkurangnya nilai delay. Ketika nilai delay mencapai batas tertentu, program menjalankan kondisi reset sehingga LED kembali ke kondisi awal.

Pada percobaan perulangan, rangkaian LED running berhasil menampilkan efek LED yang menyala secara berurutan. LED dapat bergerak dari kiri ke kanan dan kembali dari kanan ke kiri dengan bantuan perulangan. Selain itu, pada percobaan tambahan, LED juga berhasil dibuat menyala secara bergantian antara bagian kiri dan kanan, yang menunjukkan bahwa perulangan mampu mengatur urutan kerja LED secara sistematis.

---

## **2. Bagaimana pengaruh penggunaan struktur perulangan (seperti for dan while) terhadap jalannya program pada Arduino?**

Penggunaan struktur perulangan seperti `for` dan `while` sangat berpengaruh terhadap jalannya program pada Arduino karena memungkinkan suatu perintah dijalankan secara berulang tanpa harus menuliskan kode yang sama berkali-kali. Dengan adanya perulangan, program menjadi lebih efisien, ringkas, dan mudah dipahami.

Pada percobaan LED running, perulangan `for` digunakan untuk menyalakan LED secara berurutan dari satu pin ke pin lainnya. Hal ini membuat proses perpindahan nyala LED menjadi teratur dan berulang secara otomatis. Tanpa menggunakan perulangan, program akan menjadi lebih panjang dan sulit untuk dikelola.

---

## **3. Bagaimana cara kerja percabangan (`if-else`) dalam menentukan kondisi LED menyala atau mati berdasarkan input yang diberikan?**

Percabangan `if-else` bekerja dengan cara memeriksa suatu kondisi tertentu, kemudian menentukan tindakan yang harus dilakukan berdasarkan hasil pemeriksaan tersebut. Jika kondisi yang diuji bernilai benar (`true`), maka program akan menjalankan perintah pada blok `if`. Sebaliknya, jika kondisi bernilai salah (`false`), maka program akan menjalankan perintah pada blok `else`.

Pada percobaan percabangan LED, nilai variabel `timeDelay` digunakan sebagai kondisi untuk menentukan apakah program akan mempercepat kedipan LED atau mengembalikan nilai delay ke kondisi awal. Dengan mekanisme ini, LED dapat berubah kecepatan kedipnya sesuai dengan kondisi yang telah ditentukan dalam program.

---

## **4. Bagaimana kombinasi antara perulangan dan percabangan dapat digunakan untuk membuat sistem Arduino yang responsif terhadap perubahan kondisi lingkungan?**

Kombinasi antara perulangan dan percabangan memungkinkan Arduino menjalankan program secara terus-menerus sekaligus mampu merespons perubahan kondisi yang terjadi. Perulangan digunakan untuk menjalankan proses secara berulang, sedangkan percabangan digunakan untuk mengambil keputusan berdasarkan kondisi tertentu.

Sebagai contoh, dalam sistem yang menggunakan sensor, perulangan dapat digunakan untuk membaca nilai sensor secara terus-menerus, sementara percabangan digunakan untuk menentukan apakah LED harus menyala atau mati berdasarkan nilai yang diterima. Dengan kombinasi tersebut, sistem Arduino dapat menjadi lebih responsif terhadap perubahan kondisi lingkungan, seperti perubahan cahaya, suhu, atau jarak.