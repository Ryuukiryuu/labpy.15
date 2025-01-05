LATIHAN PERTEMUAN 15
BAHASA PEMROGRAMAN

LATIHAN 1

txt = 'Hello World'

# 1. Hitung jumlah karakter
jumlah_karakter = len(txt)

# 2. Ambil karakter terakhir
karakter_terakhir = txt[-1]

# 3. Ambil karakter index ke-2 sampai index ke-4
karakter_subset = txt[2:5]

# 4. Hilangkan spasi pada teks
tanpa_spasi = txt.replace(" ", "")

# 5. Ubah teks menjadi huruf besar
huruf_besar = txt.upper()

# 6. Ubah teks menjadi huruf kecil
huruf_kecil = txt.lower()

# 7. Ganti karakter H dengan karakter J
ganti_h_j = txt.replace("H", "J")

print(f"Jumlah karakter: {jumlah_karakter}")
print(f"Karakter terakhir: {karakter_terakhir}")
print(f"Karakter index ke-2 sampai index ke-4: {karakter_subset}")
print(f"Teks tanpa spasi: {tanpa_spasi}")
print(f"Teks dalam huruf besar: {huruf_besar}")
print(f"Teks dalam huruf kecil: {huruf_kecil}")
print(f"Teks setelah mengganti H dengan J: {ganti_h_j}")

# LATIHAN 2

umur = 24
txt = 'Hello, nama saya John, dan umur saya adalah {} tahun'

print(txt.format(umur))

# LATIHAN 3

import re

def validasi_nama(nama):
    if nama.isalpha():
        return True, ""
    return False, "Nama lengkap harus hanya berisi huruf."

def validasi_nomor_telepon(telepon):
    
    if telepon.isdigit():
        return True, ""
    return False, "Nomor telepon harus hanya berisi angka."

def validasi_email(email):
    if "@" in email and "." in email.split("@")[-1]:
        return True, ""
    return False, "Email harus mengandung karakter '@' dan '.'."

def validasi_pendaftaran(nama, telepon, email):
    valid = True
    pesan_error = []

    # Validasi nama
    valid_nama, pesan_nama = validasi_nama(nama)
    if not valid_nama:
        valid = False
        pesan_error.append(pesan_nama)

    # Validasi nomor telepon
    valid_telepon, pesan_telepon = validasi_nomor_telepon(telepon)
    if not valid_telepon:
        valid = False
        pesan_error.append(pesan_telepon)

    # Validasi email
    valid_email, pesan_email = validasi_email(email)
    if not valid_email:
        valid = False
        pesan_error.append(pesan_email)

    if valid:
        return "Data pendaftaran valid."
    else:
        return "\n".join(pesan_error)

# Input data
nama = input("Masukkan nama lengkap: ")
telepon = input("Masukkan nomor telepon: ")
email = input("Masukkan email: ")

# Validasi dan output
hasil = validasi_pendaftaran(nama, telepon, email)
print(hasil)
