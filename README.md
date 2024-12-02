# labpy06
# BIODATA 
# NAMA : ZAKI FAUZAN AKHBARI
# NIM : 312410348
# KELAS : TI.24.A4
# MATKUL : BAHASA PEMROGRAMAN

## Latihan 1
# ![Screenshot from 2024-11-26 14-22-32](https://github.com/user-attachments/assets/d02966bc-9672-4de1-92f7-06289097943b)
## Latihan1.py
```Python
import math

a = lambda x: x**2
b = lambda x, y: math.sqrt(x**2 + y**2)
c = lambda *args: sum(args)/len(args) if args else 0
d = lambda s: "".join(set(s))

print("lambda a(5):", a(5))
print("lambda b(3, 4):", b(3, 4))
print("lambda c(1, 2, 3, 4, 5):", c(1, 2, 3, 4, 5))
print("lambda d('hello Zaki'):", d("Zaki"))
````
### Code Program Tersebut :
# ![latihan1](https://github.com/user-attachments/assets/da267cc8-0fbe-4e08-b347-8264e1fcc93d)
### Hasil Dari Program Tersebut :
# ![Screenshot 2024-12-02 232915](https://github.com/user-attachments/assets/205f0bdf-6206-4ee4-8c73-ff09bf55dbde)
# Tugas Pratikum 
# ![Screenshot from 2024-11-26 14-40-14](https://github.com/user-attachments/assets/596e5453-a8c5-4dd4-b326-bb3fe8aa5ffa)
### Tugas Pratikum.py / Labpy06.py
```Python
def tambah():
    """Menambahkan data mahasiswa baru ke dalam daftar."""
    nama = input("Masukkan nama mahasiswa: ")
    if not nama.strip():
        print("Nama tidak boleh kosong.")
        return
    try:
        nilai = int(input("Masukkan nilai mahasiswa: "))
    except ValueError:
        print("Nilai harus berupa angka.")
        return
    daftar_mahasiswa[nama] = nilai
    print("Data mahasiswa berhasil ditambahkan.")

def tampilkan():
    """Menampilkan semua data mahasiswa."""
    if not daftar_mahasiswa:
        print("Daftar mahasiswa kosong.")
    else:
        print("Daftar Mahasiswa:")
        for nama, nilai in daftar_mahasiswa.items():
            print(f"{nama}: {nilai}")

def hapus(nama):
    """Menghapus data mahasiswa berdasarkan nama."""
    if nama in daftar_mahasiswa:
        del daftar_mahasiswa[nama]
        print(f"Data mahasiswa {nama} berhasil dihapus.")
    else:
        print(f"Data mahasiswa {nama} tidak ditemukan.")

def ubah(nama):
    """Mengubah data mahasiswa berdasarkan nama."""
    if nama in daftar_mahasiswa:
        try:
            nilai_baru = int(input(f"Masukkan nilai baru untuk {nama}: "))
            daftar_mahasiswa[nama] = nilai_baru
            print(f"Data mahasiswa {nama} berhasil diubah.")
        except ValueError:
            print("Nilai harus berupa angka.")
    else:
        print(f"Data mahasiswa {nama} tidak ditemukan.")

daftar_mahasiswa = {}

if __name__ == "__main__":
    while True:
        print("\nMenu:")
        print("1. Tambah data")
        print("2. Tampilkan data")
        print("3. Hapus data")
        print("4. Ubah data")
        print("5. Keluar")

        pilihan = input("Pilih menu (1-5): ")

        if pilihan == '1':
            tambah()
        elif pilihan == '2':
            tampilkan()
        elif pilihan == '3':
            nama = input("Masukkan nama mahasiswa yang ingin dihapus: ")
            hapus(nama)
        elif pilihan == '4':
            nama = input("Masukkan nama mahasiswa yang ingin diubah: ")
            ubah(nama)
        elif pilihan == '5':
            print("Terima kasih!")
            break
        else:
            print("Pilihan tidak valid.")
````
## Penjelasan Kode 
```Python
"""Menambahkan data mahasiswa baru ke dalam daftar."""
    nama = input("Masukkan nama mahasiswa: ")
    if not nama.strip():
        print("Nama tidak boleh kosong.")
        return
    try:
        nilai = int(input("Masukkan nilai mahasiswa: "))
    except ValueError:
        print("Nilai harus berupa angka.")
        return
    daftar_mahasiswa[nama] = nilai
    print("Data mahasiswa berhasil ditambahkan.")
````
Meminta pengguna untuk memasukkan nama mahasiswa. Jika nama kosong (hanya spasi), program akan mencetak pesan kesalahan dan keluar dari fungsi, menggunakan try-except untuk mencoba mengonversi nilai yang dimasukkan menjadi integer. Jika gagal, program mencetak pesan kesalahan, jika semua input valid, data mahasiswa (nama dan nilai) ditambahkan ke dalam dictionary daftar_mahasiswa, dan program mencetak pesan konfirmasi.
```Python
def tampilkan():
    """Menampilkan semua data mahasiswa."""
    if not daftar_mahasiswa:
        print("Daftar mahasiswa kosong.")
    else:
        print("Daftar Mahasiswa:")
        for nama, nilai in daftar_mahasiswa.items():
            print(f"{nama}: {nilai}")
````
Fungsi ini menampilkan semua data mahasiswa yang ada dalam daftar_mahasiswa kosong, Jika tidak kosong, mencetak "Daftar Mahasiswa:" dan menggunakan loop untuk mencetak setiap nama mahasiswa dan nilai mereka dalam format nama: nilai.
```Python
def hapus(nama):
    """Menghapus data mahasiswa berdasarkan nama."""
    if nama in daftar_mahasiswa:
        del daftar_mahasiswa[nama]
        print(f"Data mahasiswa {nama} berhasil dihapus.")
    else:
        print(f"Data mahasiswa {nama} tidak ditemukan.")
````
Memeriksa apakah nama mahasiswa yang ingin dihapus ada dalam daftar_mahasiswa. Jika ada, data mahasiswa dihapus menggunakan del, dan mencetak pesan konfirmasi bahwa data berhasil dihapus. Jika tidak ada, mencetak pesan bahwa mahasiswa tersebut tidak ditemukan.
```Python
def ubah(nama):
    """Mengubah data mahasiswa berdasarkan nama."""
    if nama in daftar_mahasiswa:
        try:
            nilai_baru = int(input(f"Masukkan nilai baru untuk {nama}: "))
            daftar_mahasiswa[nama] = nilai_baru
            print(f"Data mahasiswa {nama} berhasil diubah.")
        except ValueError:
            print("Nilai harus berupa angka.")
    else:
        print(f"Data mahasiswa {nama} tidak ditemukan.")
````
Mengubah nilai mahasiswa berdasarkan nama yang diberikan, Memeriksa apakah nama mahasiswa ada dalam daftar_mahasiswa. Jika ada, meminta pengguna untuk memasukkan nilai baru dan mencoba mengonversinya menjadi integer. Jika konversi berhasil, nilai mahasiswa diperbarui dalam dictionary, dan mencetak pesan konfirmasi, Jika konversi gagal, mencetak pesan kesalahan. Jika nama tidak ditemukan, mencetak pesan bahwa mahasiswa tersebut tidak ditemukan.
```Python
daftar_mahasiswa = {}
````
daftar_mahasiswa adalah dictionary kosong yang akan digunakan untuk menyimpan data mahasiswa, dengan nama sebagai kunci dan nilai sebagai nilai.
```Python
if __name__ == "__main__":
    while True:
````
if _name_ == "_main_" memastikan bahwa kode di dalam blok ini hanya dijalankan jika file ini dieksekusi langsung, bukan ketika diimpor sebagai modul oleh program lain. while True loop tak terbatas yang akan terus berjalan sampai perintah break dijalankan.
```Python
print("\nMenu:")
print("1. Tambah data")
print("2. Tampilkan data")
print("3. Hapus data")
print("4. Ubah data")
print("5. Keluar")
```
Program mencetak menu dengan lima opsi yang dapat dipilih pengguna tersebut:

1. Tambah data: untuk menambahkan data mahasiswa baru
2. Tampilkan data: untuk menampilkan semua data mahasiswa yang telah dimasukkan
3. Hapus data: Menghapus data mahasiswa berdasarkan nama
4. Ubah data: Mengubah nilai mahasiswa berdasarkan nama
5. Keluar: Keluar dari program
```Python
pilihan = input("Pilih menu (1-5): ")

Program meminta input dari pengguna untuk memilih salah satu menu (1-5).
Python
if pilihan == '1':
    tambah()
elif pilihan == '2':
    tampilkan()
````
Jika pengguna memilih 1, maka fungsi akan tambah(), Jika pengguna memilih 2, maka fungsi akan tampilkan() untuk menampilkan semua data mahasiswa yang ada dalam daftar_mahasiswa
```Python
elif pilihan == '3':
    nama = input("Masukkan nama mahasiswa yang ingin dihapus: ")
    hapus(nama)
elif pilihan == '4':
    nama = input("Masukkan nama mahasiswa yang ingin diubah: ")
    ubah(nama)
````
Jika pengguna memilih 3, program akan meminta input nama mahasiswa yang ingin dihapus, Jika pengguna memilih 4, program akan meminta input nama mahasiswa yang ingin diubah.
```Python
elif pilihan == '5':
    print("Terima kasih!")
    break
```
Jika pengguna memilih 5, program akan mencetak pesan "Terima kasih!" dan keluar dari loop utama dengan menggunakan break.

```Python
else:
    print("Pilihan tidak valid.")
````
Jika pengguna memasukkan pilihan selain angka 1 hingga 5, program akan menampilkan pesan "Pilihan tidak valid." dan kembali menampilkan menu.
### CODE PROGRAM TERSEBUT DI VISUALCODE :
# ![tugas](https://github.com/user-attachments/assets/04a7de22-b696-4faa-a76f-c6e53ee7f1f5)
### Berikut Adalah Hasil Dari Code Di Atas :
#![Screenshot 2024-12-02 233435](https://github.com/user-attachments/assets/4c6fa349-9dfd-44ac-9d1c-5a73c7acb608)
### DI BAWAH INI ADALAH FLOWCHARTNYA : 
# ![flowchart_mahasiswa](https://github.com/user-attachments/assets/35fa66d2-09b1-4d58-950c-c4daba6959df)
