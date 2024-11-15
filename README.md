Nama: ANDREAN PUTRA ARYA

Kelas: TI.24.A4

NIM: 312410341

Matkul: Bahasa Pemrograman

# Latihan 1

![gambar](https://github.com/andreanbadeh/Praktikum-6/blob/ed3dcf195fd99cd0d2628e3c6d371979831d041b/Image/Screenshot%202024-11-15%20102908.png)

# daftar kontak.py

```python
kontak = {
    "Ari": "081267888",
    "Dina": "087677776"
}

print(f"Kontak Ari: {kontak['Ari']}")

kontak["Riko"] = "087654544"

kontak["Dina"] = "088999776"

print("Semua Nama:")
for nama in kontak:
    print(nama)

print("Semua Nomor:")
for nomor in kontak.values():
    print(nomor)

print("Daftar Nama dan Nomor:")
for nama, nomor in kontak.items():
    print(f"{nama}: {nomor}")

del kontak["Dina"]

print("Daftar Kontak setelah menghapus Dina:")
for nama, nomor in kontak.items():
    print(f"{nama}: {nomor}")
```

Code Program Tersebut:

![gambar](https://github.com/andreanbadeh/Praktikum-6/blob/ba663d79556ed69b8e9cfe1f8930f9b06acb8c3a/Image/code.png)

Hasil Program Tersebut:

![gambar](https://github.com/andreanbadeh/Praktikum-6/blob/d29b778dcc226aa7413e57cd1645937e9b99e605/Image/Screenshot%202024-11-15%20104406.png)

# Input Nilai.py
```python
# Program Input Nilai
data_nilai = []

def lihat_data():
    if not data_nilai:
        print("Daftar Nilai")
        print("=" * 50)
        print("| NO |    NIM    |    NAMA    | TUGAS | UTS | UAS | AKHIR |")
        print("=" * 50)
        print("|                 TIDAK ADA DATA                   |")
        print("=" * 50)
    else:
        print("Daftar Nilai")
        print("=" * 50)
        print("| NO |    NIM    |    NAMA    | TUGAS | UTS | UAS | AKHIR |")
        print("=" * 50)
        for idx, data in enumerate(data_nilai, start=1):
            print(f"| {idx:2} | {data['nim']:8} | {data['nama']:10} | {data['tugas']:5} | {data['uts']:3} | {data['uas']:3} | {data['akhir']:5.2f} |")
        print("=" * 50)

def tambah_data():
    nim = input("NIM         : ")
    nama = input("Nama        : ")
    tugas = int(input("Nilai Tugas : "))
    uts = int(input("Nilai UTS   : "))
    uas = int(input("Nilai UAS   : "))
    akhir = (tugas + uts + uas) / 3
    data_nilai.append({"nim": nim, "nama": nama, "tugas": tugas, "uts": uts, "uas": uas, "akhir": akhir})

def ubah_data():
    nim = input("Masukkan NIM mahasiswa yang akan diubah: ")
    for data in data_nilai:
        if data['nim'] == nim:
            print("Data ditemukan. Silakan masukkan data baru.")
            data['nama'] = input("Nama        : ")
            data['tugas'] = int(input("Nilai Tugas : "))
            data['uts'] = int(input("Nilai UTS   : "))
            data['uas'] = int(input("Nilai UAS   : "))
            data['akhir'] = (data['tugas'] + data['uts'] + data['uas']) / 3
            print("Data berhasil diubah.")
            return
    print("Data tidak ditemukan.")

def hapus_data():
    nim = input("Masukkan NIM mahasiswa yang akan dihapus: ")
    for i, data in enumerate(data_nilai):
        if data['nim'] == nim:
            del data_nilai[i]
            print("Data berhasil dihapus.")
            return
    print("Data tidak ditemukan.")

def cari_data():
    nim = input("Masukkan NIM mahasiswa yang dicari: ")
    for data in data_nilai:
        if data['nim'] == nim:
            print("Data ditemukan:")
            print(f"NIM       : {data['nim']}")
            print(f"Nama      : {data['nama']}")
            print(f"Nilai Tugas : {data['tugas']}")
            print(f"Nilai UTS   : {data['uts']}")
            print(f"Nilai UAS   : {data['uas']}")
            print(f"Nilai Akhir : {data['akhir']:.2f}")
            return
    print("Data tidak ditemukan.")

while True:
    print("\nProgram Input Nilai")
    print("===================")
    print("(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar")
    pilihan = input("Pilih menu: ").lower()

    if pilihan == 'l':
        lihat_data()
    elif pilihan == 't':
        tambah_data()
    elif pilihan == 'u':
        ubah_data()
    elif pilihan == 'h':
        hapus_data()
    elif pilihan == 'c':
        cari_data()
    elif pilihan == 'k':
        print("Keluar dari program.")
        break
    else:
        print("Pilihan tidak valid. Silakan coba lagi.")
```

# Penjelasan code
```python
data_nilai = []
```
Sebuah list kosong yang akan digunakan untuk menyimpan data mahasiswa yang terdiri dari NIM, nama, nilai tugas, UTS, UAS, dan nilai akhir.

```python
def lihat_data():
    if not data_nilai:
        print("Daftar Nilai")
        print("=" * 50)
        print("| NO |    NIM    |    NAMA    | TUGAS | UTS | UAS | AKHIR |")
        print("=" * 50)
        print("|                 TIDAK ADA DATA                   |")
        print("=" * 50)
    else:
        print("Daftar Nilai")
        print("=" * 50)
        print("| NO |    NIM    |    NAMA    | TUGAS | UTS | UAS | AKHIR |")
        print("=" * 50)
        for idx, data in enumerate(data_nilai, start=1):
            print(f"| {idx:2} | {data['nim']:8} | {data['nama']:10} | {data['tugas']:5} | {data['uts']:3} | {data['uas']:3} | {data['akhir']:5.2f} |")
        print("=" * 50)
```
Jika list kosong (tidak ada data), maka akan ditampilkan pesan `TIDAK ADA DATA`. Jika ada `data`, maka program akan menampilkan daftar mahasiswa dalam format tabel dengan nomor urut, NIM, nama, nilai tugas, UTS, UAS, dan nilai akhir.

```python
def tambah_data():
    nim = input("NIM         : ")
    nama = input("Nama        : ")
    tugas = int(input("Nilai Tugas : "))
    uts = int(input("Nilai UTS   : "))
    uas = int(input("Nilai UAS   : "))
    akhir = (tugas + uts + uas) / 3
    data_nilai.append({"nim": nim, "nama": nama, "tugas": tugas, "uts": uts, "uas": uas, "akhir": akhir})
```
Pengguna diminta untuk memasukkan NIM, nama, dan nilai untuk tugas, UTS, dan UAS. Setelah itu, nilai akhir dihitung sebagai rata-rata dari ketiga nilai tersebut dan data mahasiswa tersebut disimpan dalam list `data_nilai` dalam bentuk dictionary.

```python
def ubah_data():
    nim = input("Masukkan NIM mahasiswa yang akan diubah: ")
    for data in data_nilai:
        if data['nim'] == nim:
            print("Data ditemukan. Silakan masukkan data baru.")
            data['nama'] = input("Nama        : ")
            data['tugas'] = int(input("Nilai Tugas : "))
            data['uts'] = int(input("Nilai UTS   : "))
            data['uas'] = int(input("Nilai UAS   : "))
            data['akhir'] = (data['tugas'] + data['uts'] + data['uas']) / 3
            print("Data berhasil diubah.")
            return
    print("Data tidak ditemukan.")
```
Pengguna dapat memasukkan data baru (nama, nilai tugas, UTS, UAS), dan nilai akhir dihitung ulang. Jika NIM tidak ditemukan, akan ditampilkan pesan bahwa data tidak ditemukan.

```python
def hapus_data():
    nim = input("Masukkan NIM mahasiswa yang akan dihapus: ")
    for i, data in enumerate(data_nilai):
        if data['nim'] == nim:
            del data_nilai[i]
            print("Data berhasil dihapus.")
            return
    print("Data tidak ditemukan.")
```
Jika NIM ditemukan, data mahasiswa tersebut akan dihapus dari list `data_nilai`. Jika NIM tidak ditemukan, maka akan ditampilkan pesan bahwa data tidak ditemukan.

```python
def cari_data():
    nim = input("Masukkan NIM mahasiswa yang dicari: ")
    for data in data_nilai:
        if data['nim'] == nim:
            print("Data ditemukan:")
            print(f"NIM       : {data['nim']}")
            print(f"Nama      : {data['nama']}")
            print(f"Nilai Tugas : {data['tugas']}")
            print(f"Nilai UTS   : {data['uts']}")
            print(f"Nilai UAS   : {data['uas']}")
            print(f"Nilai Akhir : {data['akhir']:.2f}")
            return
    print("Data tidak ditemukan.")
```
Program akan menampilkan data mahasiswa (NIM, nama, nilai tugas, UTS, UAS, nilai akhir). Jika NIM tidak ditemukan, maka akan ditampilkan pesan bahwa data tidak ditemukan.

```python
while True:
    print("\nProgram Input Nilai")
    print("===================")
    print("(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar")
    pilihan = input("Pilih menu: ").lower()

    if pilihan == 'l':
        lihat_data()
    elif pilihan == 't':
        tambah_data()
    elif pilihan == 'u':
        ubah_data()
    elif pilihan == 'h':
        hapus_data()
    elif pilihan == 'c':
        cari_data()
    elif pilihan == 'k':
        print("Keluar dari program.")
        break
    else:
        print("Pilihan tidak valid. Silakan coba lagi.")
```
Untuk bagian utama dari program, yang menyediakan menu interaktif untuk memilih tindakan yang ingin dilakukan : `(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar`

Code Program Tersebut:

![gambar](https://github.com/andreanbadeh/Praktikum-6/blob/5f5a6fba20ef4240594ce28ab696dbf6e181c74d/Image/input%20nilai.png)

Hasil Program Tersebut:

![gambar](https://github.com/andreanbadeh/Praktikum-6/blob/5f5a6fba20ef4240594ce28ab696dbf6e181c74d/Image/Screenshot%202024-11-16%20055659.png)
