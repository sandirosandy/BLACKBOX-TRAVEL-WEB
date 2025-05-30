# Parameter Penilaian 
| Field     | Parameter Validasi                     | Jenis Pengujian | Alasan Valid/Invalid                              |
| --------- | -------------------------------------- | --------------- | ------------------------------------------------- |
| Name | Minimal 3 huruf                        | BVA & EP        | Valid: panjang = 3, huruf semua; Invalid: <3      |
| Username  | 1–15 karakter, huruf/angka             | BVA & EP        | Valid:3/15 karakter; Invalid: 4/16 karakter      |
| Email     | Format email                           | EP              | Valid: format lengkap; Invalid: tanpa '@', domain |
| Password  | Minimal 8 karakter, kombinasi karakter | BVA & EP        | Valid: ≥6, kombinasi huruf/angka/simbol           |
| Confirm Password | Sesuai dengan Password yang di input sebelumnya                    | BVA & EP        | Valid: Jika sesuai dengan Password yang di inputkan sebelumnya  |

# BOUNDARY VALUE ANALYSIS - REGISTER
---
| Field         | Validasi Panjang/Range | Nilai Valid                               | Nilai Invalid                    |
| ------------- | ---------------------- | ----------------------------------------------------- | ---------------------------------------------------- |
| **Name** | Minimal 3 huruf        | sa (2)                                | ""                                |Valid | failed|
| **Username**  | 1–15 karakter          | `8` → ✅ `"user1234"`<br>`15` → ✅ `"usernamelengkap"`     | ""    |
| **Email** | Format Email | kelompokjurnal@gmail.com | kelompok@.com |
| **Password**  | Minimal 8 karakter     | `8` → ✅ `"pass1234"`                                    | `5` → ❌ `"12345"`                  |
| **Confirm Password** | Sesuai dengan password yang diinput sebelumnya | sesuai dengan password yang diinput | Tidak sesuai dengan yang diinput |
---

# EQUIVALENCE PARTITIONING - REGISTER
---
| Field         | Kelas Valid                               | Kelas Invalid                                                               |
| ------------- | ----------------------------------------- | --------------------------------------------------------------------------- |
| **Name** | Huruf & spasi, ≥ 1 karakter                 | ""            |
| **Username**  | 1 karakter               | 1 karakter                        |
| **Email**     | Format email valid (`a@b.com`)            | Tanpa `@`, tanpa domain, kosong (`"abc"`, `"a@"`, `"@b.com"`, `""`)         |
| **Password**  | ≥8 karakter | <8 karakter, kosong       |
| **Confirm Password** | Sesuai dengan password yang diinput sebelumnya | Tidak sesuai dengan password yang diinput sebelumnya |

# contoh
|TC ID | Deskripsi | Input | Excpect | Aktual | Status |
|---|---|---|---|---|---|
|TC01 | Input nama > 3 karakter | `sa`,`sandirsndi`,`san@gmail.com`,`sandi123`,`sandi123`| Error:nama minimal 3| Berhasil| ❌Failed|
|TC02 | Input nama tepat minimal (1) | `s`,`sandirsndi`,`san@gmail.com`,`sandi123`,`sandi123` | Berhasil | Berhasil | ✅Passed|
|TC03 | Input Username > 5 Karakter | `s`,`sans`,`san@gmail.com`,`sandi123`,`sandi123` | Error: Username minimal 5 karakter | Berhasil | ❌Failed|
|TC 04 | Input username tepat minimal | 


# TEST CASE REGISTER
---
| TC ID | Field     | Test Case Description                | Input              | Expected Result                            | Aktual |  Status |
| ----- | --------- | ------------------------------------ | ------------------ | ------------------------------------------ | ------ |----|
| TC01  | Full Name | Input kurang dari 3 huruf            | `Sa`               | Gagal – Error: "Nama minimal 3 huruf"      | Muncul Pesan "Nama minimal 3 huruf"      |✅|
| TC02  | Full Name | Input tepat 3 huruf                  | `San`              | Berhasil                                   | Berhasil      |✅|
| TC03  | Username  | Input < 3 karakter                   | `us`              | Gagal – Error: "Username minimal 3"        | uncul Pesan "Nama minimal 3 karakter"      |✅|
| TC04  | Username  | Input 3 karakter (batas bawah valid) | `din`            | Berhasil                                   | Berhasil      |✅|
| TC05  | Username  | Input 15 karakter (batas atas valid) | `usernamelengkap`  | Berhasil                                   | Berhasil      |✅|
| TC06  | Username  | Input > 15 karakter                  | `usernamelengkapx` | Gagal – Error: "Max 15 karakter"           | MMuncul Error: "Max 15 karakter"      |✅|
| TC07  | Password  | Input < 6 karakter                   | `12345`            | Gagal – Error: "Password mminimal 6 karakter"   | muncul "password minimal 6 karakter | ✅|      |
| TC08  | Password  | Input = 6 karakter                   | `pass12`           | Berhasil                                   | Berhasil      |✅|
| TC09  | Email     | Format tidak valid (tanpa `@`)       | `abc.com`          | Gagal – Error: "Format email salah"        | Muncul " formal email salah " | ✅      |
| TC10  | Email     | Format valid                         | `user@mail.com`    | Berhasil                                   | Berhasil      |✅|
| TC11  | Phone     | Kurang dari 10 digit                 | `0812345677`       | Gagal – Error: "nomor hp minimal 11-13 angka"        | Muncul "nomor hp minimal 11-13 angka"      | ✅|
| TC12  | Phone     | Tepat 11 digit                       | `08123456789`      | Berhasil                                   | Berhasil      |✅|
| TC13  | Phone     | 14 digit (melebihi batas)            | `08123456789012`   | Gagal – Error: "nomor harus 11-13 angka"        | Muncul "nomor harus 11-13 angka"      |✅|
| TC14  | Phone     | Mengandung huruf                     | `08abc56789`       | Gagal – Error: "nomor harus 11-13 angka"        | Muncul "nomor harus 11-13 angka"     |✅|
| TC15  | Address   | <5 karakter                          | `Jln`              | Gagal – Error: "Alamat minimal 5 karakter" | mmuncul "Alamat minimal 5 karakter"       |✅|
| TC16  | Address   | Tepat 5 karakter                     | `J1.AB`            | Berhasil                                   | Berhasil      |✅|


