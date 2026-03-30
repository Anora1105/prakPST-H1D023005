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

### Program Arduino

```cpp
const int ledPin = 12;

void setup() {

  pinMode(ledPin, OUTPUT);

}

void loop() {

  // Mode cepat
  digitalWrite(ledPin, HIGH);
  delay(200);
  digitalWrite(ledPin, LOW);
  delay(200);

  // Mode sedang
  digitalWrite(ledPin, HIGH);
  delay(500);
  digitalWrite(ledPin, LOW);
  delay(500);

  // Mode mati
  digitalWrite(ledPin, LOW);
  delay(2000);

}
