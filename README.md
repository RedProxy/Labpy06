# Pertemuan 11
## Latihan 1

![Gambar 1](image/img1.jpeg)

### Penjelasan

1. Import modul build-in math, yang berfungsi memperluas daftar fungsi matematika
```python
import math
```
2. Fungsi lambda yang menggunakan variabel a-d
```py
def a(x):
    return x**2
    a = lambda x : x ** 2
print(a(30))

def b(x, y):
    return math.sqrt(x**2 + y**2)
b = lambda x, y : x ** 2  + y ** 2
print(b(5, 10))

def c(*args):
    return sum(args)/len(args)
    c = lambda *args : sum(args)/len(args)
print(c(3, 10, 8, 45))

def d(s):
    return "".join(set(s))
    d = lambda s: "".join(set(s))
print(d("Seong"))
```


3. Pemanggilan function lambda

```bash
print(a(30))
print(b(5, 10))
print(c(3, 10, 8, 45))
print(d("Seong"))
```

### Output
![Gambar 2](image/img2.png)

## Tugas Praktikum

![Gambar 3](image/img3.jpeg)

### Flowchart

![Gambar 4](image/flowchart.jpeg)

### Penjelasan

1. Membuat dictionary kosong yang nantinya akan diinput dengan data.
```bash
data={}
```

2. Membuat perulangan dengan while dan terdapat pilihan menu untuk menjalankan program.
```bash
while True:
    print()
    a=input("[(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar] :")
    print()
```
3. Menambahkan data nim, nama, nilai tugas, uts, dan uas. Data yang diinputkan akan masuk ke dalam dictionary data dengan nim sebagai keys sedangkan nama, tugas, uts dan uas sebagai values.
```bash
if a=="t" or a=="T":
    print(" TAMBAH DATA ")
    print("-------------")
    nim=int(input("NIM\t: "))
    nama=input("Nama\t: ")
    tugas=int(input("Tugas\t: ")) 
    uts=int(input("UTS\t: "))
    uas=int(input("UAS\t: "))
    akhir=(int(tugas)*30/100)+(int(uts)*35/100)+(int(uas)*35/100)
    data[nim]=nama, tugas, uts, uas, akhir
```
- Output Menambahkan Data
![gambar 5](image/tambah.jpeg)
4. Menampilkan atau melihat data. Jika sebelumnya belum menginput data, maka tampilannya akan "Tidak ada data". Apabila sudah menginput data, maka data yang telah diinput tadi akan ditampilkan.
```bash
elif a=="l" or a=="L":
    if data.items():
        print(" DAFTAR NILAI ")
        print("--------------")
        print(72*"=")
        print("| {0:^10} | {1:^10} | {2:^6} | {3:^6} | {4:^6} |   {5:^12}  |".format("NIM", "NAMA", "TUGAS", "UTS", "UAS", "NILAI AKHIR"))
        print(72*"=")
        for item in data.items(): 
            print("| {0:>10} | {1:>10} | {2:>6} | {3:>6} | {4:>6} |   {5:>12}  |".format(nim, nama, tugas, uts, uas, akhir))
            print(72*"=")
        print()
    else:
        print(" DAFTAR NILAI ")
        print("--------------")
        print(72*"=")
        print("| {0:^10} | {1:^10} | {2:^6} | {3:^6} | {4:^6} |   {5:^12}  |".format("NIM", "NAMA", "TUGAS", "UTS", "UAS", "NILAI AKHIR"))
        print(72*"=")
        print("|                             TIDAK ADA DATA                           |")
        print(72*"=")
        print()
```
Output Menampilkan Data
![gambar 6](image/tampil.jpeg)
5. Apabila ingin mengubah data, maka anda akan diminta untuk menginputkan nim terlebih dahulu. Setelah itu input data yang ingin diubah.
```bash
elif a=="u" or a=="U":
    print(" UBAH DATA ")
    print("-----------")
    b=input("Masukkan NIM anda: ")
    print()
    if data.keys():
        tugas=int(input("Tugas\t: ")) 
        uts=int(input("UTS\t: "))
        uas=int(input("UAS\t: "))
        akhir=(int(tugas)*30/100)+(int(uts)*35/100)+(int(uas)*35/100)
```
Output Mengubah Data
![gambar 7](image/ubah.jpeg)
6. Jika ingin menghapus data, anda akan diminta untuk menginput nim. Lalu data yang telah diinput diawal tadi akan dihapus beserta valuesnya (nama, nilai tugas, nilai uts dan nilai uas).
```bash
elif a=="h" or a=="H":
    print(" HAPUS DATA ")
    print("------------")
    b=input("Masukkan NIM anda: ")
    print()
    if data.keys():
        del data[nim]
```
Output Menghapus Data
![gambar 8](image/hapus.jpeg)
7. Apabila ingin mencari data, anda akan diminta untuk menginput nim kemudian data yang anda cari akan muncul berdasarkan nim yang diinput tadi.
```bash
elif a=="c" or a=="C":
    print(" CARI DATA ")
    print("-----------")
    b=input("Masukkan NIM anda: ")
    print()
    if data.keys():
        print(72*"=")
        print("| {0:^10} | {1:^10} | {2:^6} | {3:^6} | {4:^6} |   {5:^12}  |".format("NIM", "NAMA", "TUGAS", "UTS", "UAS", "NILAI AKHIR"))
        print(72*"=")
        print("| {0:>10} | {1:>10} | {2:>6} | {3:>6} | {4:>6} |   {5:>12}  |".format(nim, nama, tugas, uts, uas, akhir))
        print(72*"=")
        print()
```
8. Jika data sudah selesai diinput, pilih menu 'k'/'K' maka program akan terhenti.
```bash
elif a=="k" or a=="K":
     break
```