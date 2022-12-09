# Sub Rutin/Fungsi
## Latihan 1
![latihan1](https://user-images.githubusercontent.com/116176746/206343131-5cac03e5-add2-4bfe-b3a9-ab6df0ec315e.png)
```python

import math

def a(x)
    return x**2

#jika menggunakan lambda
A=lambda x:x**2
print(A(2))

def b(x, y):
return math.sqrt(x**2 + y**2)

#jika menggunakan lambda
B=lambda x,y:math.sqrt(x**2 + y**2)
print(B(2,2))

def c(*args):
return sum(args)/len(args)

#jika mengguankan lambda
C= lambda *args:sum(args)/len(args)
print(C(3,5,1,2,4))
```

output:
\
![lambda](https://user-images.githubusercontent.com/116176746/206615335-f019cc09-a89c-4c82-aa52-a44a098b7f23.png)

## Tugas Praktikum
>Buat program sederhana dengan mengaplikasikan penggunaan fungsi
yang akan menampilkan daftar nilai mahasiswa, dengan ketentuan:
• Fungsi tambah() untuk menambah data
• Fungsi tapilkan() untuk menampilkan data
• Fungsi hapus(nama) untuk menghapus data berdasarkan nama
• Fungsi ubah(nama) untuk mengubah data berdasarkan nama

Code:   
```python
dataMhs = {}


def head_tbl():
    print("=========================================================================")
    print("| No |     NIM     |       NAMA        |  TUGAS  |  UTS | UAS |  AKHIR  |")
    print("=========================================================================")


def Tambah():
    nim = input("Masukan NIM          : ")
    nama = input("Masukan Nama         : ")
    tugas = input("Masukan Nilai Tugas  : ")
    if tugas == "":
        tugas = 0
    uts = input("Masukan Nilai UTS    : ")
    if uts == "":
        uts = 0
    uas = input("Masukan Nilai UAS    : ")
    if uas == "":
        uas = 0

    akhir = ((int(tugas) / 100 * 30) +
             (int(uts) / 100 * 35) + (int(uas) / 100 * 35))
    dataMhs[nim] = {"nama": nama, "tugas": tugas,
                    "uts": uts, "uas": uas, "akhir": akhir}


def Tampilkan():
    print("Daftar Nilai")
    head_tbl()
    if len(dataMhs) == 0:
        print("|                         TIDAK ADA DATA                                |")
    else:
        x = 1
        for i, j in dataMhs.items():
            print('| {0:^3}| {1:11} | {2:<17} | {3:7} | {4:4} | {5:3} | {6:7.2f} |'.format(x, i, dataMhs[i]["nama"],
                                                                                           dataMhs[i]["tugas"],
                                                                                           dataMhs[i]["uts"],
                                                                                           dataMhs[i]["uas"],
                                                                                           dataMhs[i]["akhir"]))
            x += 1
    print("=========================================================================")


def cariNIM(nim):
    head_tbl()
    if (dataMhs.get(nim, "kosong") != "kosong"):
        print('| {0:^3}| {1:11} | {2:<17} | {3:7} | {4:4} | {5:3} | {6:6.2f} |'.format(
            1, nim, dataMhs[nim]["nama"], dataMhs[nim]["tugas"], dataMhs[nim]["uts"], dataMhs[nim]["uas"],
            dataMhs[nim]["akhir"]))
    else:
        print("|                 DATA MAHASISWA DENGAN NO NIM ",
              nim, "KOSONG / TIDAK ADA     |")
    print("=========================================================================")


def cariNama(nama):
    x, found = 0, 0
    head_tbl()
    for i, j in dataMhs.items():
        x += 1

        if ((dataMhs.get(i)).get('nama').startswith(nama)):
            found += 1
            print('| {0:^3}| {1:11} | {2:<17} | {3:7} | {4:4} | {5:3} | {6:6.2f} |'.format(
                1, i, dataMhs[i]["nama"], dataMhs[i]["tugas"], dataMhs[i]["uts"], dataMhs[i]["uas"],
                dataMhs[i]["akhir"]))
    if (found == 0):
        print("Data tidak ada")
    print("=========================================================================")


def UbahNim(nim):
    if (dataMhs.get(nim, "kosong") != "kosong"):
        nama = input("Masukan Nama         : ")
        if nama == "":
            nama = dataMhs[nim]['nama']
        tugas = input("Masukan Nilai Tugas  : ")
        if tugas == "":
            tugas = dataMhs[nim]['tugas']
        uts = input("Masukan Nilai UTS    : ")
        if uts == "":
            uts = dataMhs[nim]['uts']
        uas = input("Masukan Nilai UAS    : ")
        if uas == "":
            uas = dataMhs[nim]['uas']
        akhir = ((int(tugas) / 100 * 30) +
                 (int(uts) / 100 * 35) + (int(uas) / 100 * 35))
        dataMhs[nim] = {"nama": nama, "tugas": tugas,
                        "uts": uts, "uas": uas, "akhir": akhir}
        print("Berhasil Mengubah Data")
    else:
        print("Data tidak ditemukan.\nPastikan anda memasukan NIM yang benar ")


def Ubah(nama):
    found = 0
    for i, j in dataMhs.items():
        if ((dataMhs.get(i)).get('nama') == nama):
            found = i
    if (found == 0):
        print("Data tidak ada")
    else:
        nama = input("Masukan Nama         : ")
        if nama == "":
            nama = dataMhs[nim]['nama']
        tugas = input("Masukan Nilai Tugas  : ")
        if tugas == "":
            tugas = dataMhs[nim]['tugas']
        uts = input("Masukan Nilai UTS    : ")
        if uts == "":
            uts = dataMhs[nim]['uts']
        uas = input("Masukan Nilai UAS    : ")
        if uas == "":
            uas = dataMhs[nim]['uas']
        akhir = ((int(tugas) / 100 * 30) +
                 (int(uts) / 100 * 35) + (int(uas) / 100 * 35))
        dataMhs[found] = {"nama": nama, "tugas": tugas,
                          "uts": uts, "uas": uas, "akhir": akhir}
        print("Berhasil Mengubah Data")


def Hapus(nama):
    found = 0
    for i, j in dataMhs.items():
        if ((dataMhs.get(i)).get('nama') == nama):
            found = i
    if (found == 0):
        print("Data tidak ada")
    else:
        dataMhs.pop(i)


def HapusNim(nim):
    if (dataMhs.get(nim, "kosong") != "kosong"):
        dataMhs.pop(nim)
        print("Berhasil menghapus data mahasiswa")
    else:
        print("Data tidak ditemukan.\nPastikan anda memasukan NIM yang benar ")

print("=========================================================================")
print("|                         Program Data Nilai Mahasiswa                  |")
print("=========================================================================")
while True:
    menu = input("(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar : ")
    if menu.capitalize() == "T":
        Tambah()
    if menu.capitalize() == "L":
        Tampilkan()
    if menu.capitalize() == "U":
        print("Mengubah data Mahasiswa")
        SearchBy = input("Hapus data berdasarkan ( 1. ) NIM atau ( 2. ) Nama : ")
        if SearchBy == "1":
            nim = input("Masukan NIM :")
            UbahNim(nim)
        elif SearchBy == "2":
            nama = input("Masukan Nama : ")
            Ubah(nama)

    if menu.capitalize() == "H":
        print("Menghapus data Mahasiswa")
        SearchBy = input("Hapus data berdasarkan ( 1. ) NIM atau ( 2. ) Nama : ")
        if SearchBy == "1":
            nim = input("Masukan NIM :")
            HapusNim(nim)
        elif SearchBy == "2":
            nama = input("Masukan Nama : ")
            Hapus(nama)

    if menu.capitalize() == "C":
        print("Mencari Nilai Mahasiswa")
        SearchBy = input("Cari berdasarkan ( 1. ) NIM atau ( 2. ) Nama : ")
        if SearchBy == "1":
            nim = input("Masukan NIM :")
            cariNIM(nim)
        elif SearchBy == "2":
            nama = input("Masukan Nama : ")
            cariNama(nama)

    if menu.capitalize() == "K":
        print("Keluar dari program..")
        break

    elif menu.capitalize() not in ('L', 'T', 'U', 'H', 'C', 'K'):
        print("Format yang Anda Masukan Tidak Sesuai")
```
output:
\
Menu 'Tambah Data'
\
![tambah data](https://user-images.githubusercontent.com/116176746/206619736-3c162b1d-969f-4b04-b9b4-47d506b2b013.png)

Menu 'Ubah Data'
\
![ubah data](https://user-images.githubusercontent.com/116176746/206619743-ae1785eb-582a-490d-be84-4fc7fd95e21f.png)

Menu 'Lihat Data'
\
![lihat data](https://user-images.githubusercontent.com/116176746/206619744-fb2670be-3a93-4935-9885-432bc4248da8.png)

