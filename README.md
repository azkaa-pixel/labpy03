# modul praktik 03 - pengulangan 
Nama  :  ghefira azka fardani 

Kelas  : TI.24.A5

NIM  : 312410521

## latihan 
## latihan 1 

1. Tampilkan n bilangan acak yang lebih kecil dari 0.5.

2. nilai n diisi pada saat runtime

3. anda bisa menggunakan kombinasi while dan for untuk menyelesaikannya

4. gunakan fungsi random() yang dapat diimport terlebih dahulu

### - flowchart
![foto]
### - code program
```phython
from random import random
```
Di sini, kita mengimpor fungsi random dari modul random. Fungsi ini menghasilkan angka acak antara 0 dan 1.
```phython
n = int(input("Masukkan nilai N: "))
```
Program meminta pengguna untuk memasukkan nilai ```N```, yang kemudian diubah menjadi integer. Ini adalah jumlah bilangan acak yang ingin ditampilkan.
```phython
count = 0
```
Variabel ```count``` diinisialisasi dengan 0. Variabel ini akan digunakan untuk menghitung berapa banyak bilangan acak yang lebih kecil dari 0.5 yang telah ditampilkan.
```phython
while count < n:
```
Kita menggunakan loop ```while``` yang akan terus berjalan selama ```count``` kurang dari ```n```. Ini berarti loop akan berlanjut sampai kita telah menampilkan ```n``` 
angka acak yang memenuhi
```phython
angka_acak = random()
```
Di dalam loop, kita menghasilkan angka acak menggunakan fungsi ```random()``` dan menyimpannya dalam variabel ```angka_acak```.
```phython
if angka_acak < 0.5:
```
Program memeriksa apakah ```angka_acak``` lebih kecil dari 0.5. Jika ya, kita akan melakukan langkah berikutnya.
```phython
count += 1
print(f"data ke: {count} => {angka_acak}")
```
Jika angka acak memenuhi syarat, kita menambah nilai ```count``` sebesar 1 dan mencetak angka tersebut beserta nomor urutnya.
```phython
print("Selesai")
```
Setelah loop selesai (artinya sudah menampilkan ```n``` angka acak), program akan mencetak "Selesai".

### - hasil
![foto](https://github.com/azkaa-pixel/labpy03/blob/185abe26690bc600f5bf638e55d2dd71350e0828/labpy03%20lat%201.jpg)

## latihan 2
Seorang pengusaha menginvestasikan uangnya untuk memulai usahanya dengan modal awal 100 juta, pada bulan pertama dan kedua belum mendapatkan laba. 
pada bulan ketiga baru mulai mendapatkan laba sebesar 1% dan pada bulan ke 5, pendapatan meningkat 5%, selanjutnya pada bulan ke 8 mengalami penurunan keuntungan sebesar 2%,
sehingga laba menjadi 3%. Hitung total keuntungan selama 8 bulan berjalan usahanya.
### - flowchart
![foto]()
### - code program 
```phython
modal_awal = 100_000_000  # 100 juta
```
Di sini, kita mendefinisikan modal awal sebesar 100 juta IDR.
```phython
laba_per_bulan = [0, 0, 0.01, 0, 0.05, 0, 0, -0.02, 0.03]  # Bulan 1-8
```
Ini adalah daftar (list) yang berisi persentase laba untuk setiap bulan dari bulan 1 hingga bulan 8. Misalnya, pada bulan ketiga, laba adalah 1% dari modal,
sedangkan pada bulan kedelapan, terdapat kerugian sebesar 2%.
```phython
total_keuntungan = 0
```
Variabel ```total_keuntungan``` diinisialisasi dengan nilai 0. Ini akan digunakan untuk menghitung total laba yang diperoleh selama 8 bulan.
```phython
for bulan in range(1, 9):
    laba_bulan_ini = modal_awal * laba_per_bulan[bulan]
    total_keuntungan += laba_bulan_ini
```
Di sini, kita menggunakan loop ```for``` untuk iterasi dari bulan 1 hingga 8. Dalam setiap iterasi:

-Menghitung Laba Bulan Ini: Laba untuk bulan saat ini dihitung dengan mengalikan ```modal_awal``` dengan persentase laba dari list ```laba_per_bulan``` berdasarkan indeks bulan.

-Menambahkan ke Total Keuntungan: Laba bulan ini ditambahkan ke ```total_keuntungan```.
```phython
print(f"Total keuntungan selama 8 bulan: {total_keuntungan:,.0f} IDR")
```
Terakhir, kita mencetak total keuntungan yang telah dihitung selama 8 bulan. 
Format ```:,.0f``` digunakan untuk menampilkan angka dalam format yang lebih mudah dibaca (dengan pemisah ribuan dan tanpa desimal).
### - hasil
![foto](https://github.com/azkaa-pixel/labpy03/blob/185abe26690bc600f5bf638e55d2dd71350e0828/labpy03%20lat%202.jpg)
## latihan 3
Buat program yang mensimulasikan mesin ATM sederhana. Pengguna memiliki saldo awal sebesar Rp 1.000.000, dan dapat menarik uang hingga saldo habis atau memilih untuk keluar.
### - flowchart
![foto]()
### - code program 
```phython
def _init_(self, saldo_awal):
    self.saldo = saldo_awal
```
Ini adalah konstruktor dari kelas ```ATM```. Namun, ada kesalahan pengetikan di sini.
Metode seharusnya bernama ```__init__``` (dengan dua garis bawah di depan dan belakang) untuk berfungsi sebagai konstruktor. 
Metode ini menginisialisasi objek dengan ```saldo``` yang diberikan saat objek dibuat.

```phython
def tampilkan_saldo(self):
    print(f"Saldo Anda saat ini: Rp {self.saldo}")
```
Metode ini mencetak saldo saat ini dari pengguna.
```phython
def tarik_uang(self, jumlah):
    if jumlah > self.saldo:
        print("Maaf, saldo tidak cukup.")
    elif jumlah <= 0:
        print("Jumlah penarikan harus lebih dari Rp 0.")
    else:
        self.saldo -= jumlah
        print(f"Anda telah menarik uang sebesar Rp {jumlah}.")
        self.tampilkan_saldo()
```
Metode ini menangani proses penarikan uang:

-Jika jumlah yang ingin ditarik lebih besar dari saldo, akan muncul pesan bahwa saldo tidak cukup.
-Jika jumlah penarikan kurang dari atau sama dengan nol, akan muncul pesan bahwa jumlah harus lebih dari Rp 0.
-Jika penarikan valid, saldo akan dikurangi, dan saldo yang tersisa akan ditampilkan.
```phython
def menu(self):
    while True:
        print("\n=== Mesin ATM ===")
        print("1. Tampilkan Saldo")
        print("2. Tarik Uang")
        print("3. Keluar")
        pilihan = input("Pilih menu (1/2/3): ")
```
Metode ini menciptakan antarmuka pengguna yang berulang untuk berinteraksi dengan mesin ATM:

-Menampilkan opsi menu.
-Mengambil input dari pengguna untuk memilih menu.
-Menggunakan struktur kontrol untuk memanggil metode yang sesuai berdasarkan pilihan pengguna.
-Jika pengguna memilih untuk keluar, loop akan berhenti dan mencetak pesan terima kasih.
```phython
atm = ATM(1000000)
atm.menu()
```
Di sini, objek ```atm``` dari kelas ```ATM``` diinisialisasi dengan saldo awal Rp 1.000.000 dan metode ```menu``` dipanggil untuk memulai interaksi dengan pengguna.
### - hasil
![foto](https://github.com/azkaa-pixel/labpy03/blob/185abe26690bc600f5bf638e55d2dd71350e0828/labpy03%20lat%203.jpg)

