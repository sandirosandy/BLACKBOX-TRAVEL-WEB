# Parameter Penilaian 
| Field     | Parameter Validasi                     | Jenis Pengujian | Alasan Valid/Invalid                              |
| --------- | -------------------------------------- | --------------- | ------------------------------------------------- |
| Full Name | Minimal 3 huruf                        | BVA & EP        | Valid: panjang = 3, huruf semua; Invalid: <3      |
| Username  | 3–15 karakter, huruf/angka             | BVA & EP        | Valid:3/15 karakter; Invalid: 4/16 karakter      |
| Email     | Format email                           | EP              | Valid: format lengkap; Invalid: tanpa '@', domain |
| Password  | Minimal 8 karakter, kombinasi karakter | BVA & EP        | Valid: ≥6, kombinasi huruf/angka/simbol           |
| Confirm Password | Sesuai dengan Password yang di inputkan sebelumnya                    | BVA & EP        | Valid: Jika sesuai dengan Password yang di inputkan sebelumnya  |

# BOUNDARY VALUE ANALYSIS - REGISTER
---
| Field         | Validasi Panjang/Range | Nilai Valid                               | Nilai Invalid                    |
| ------------- | ---------------------- | ----------------------------------------------------- | ---------------------------------------------------- |
| **Name** | Minimal 3 huruf        | sa (2)                                | Invalid                                |Valid | failed|
| **Username**  | 8–15 karakter          | `8` → ✅ `"user1"`<br>`15` → ✅ `"usernamelengkap"`     | `4` → ❌ `"usr"`<br>`16` → ❌ `"usernamelengkapx"`     |
| **Email** | Format Email | 
| **Password**  | Minimal 8 karakter     | `6` → ✅ `"pass12"`                                    | `5` → ❌ `"12345"`                  |
| **Confirn Password** | Sesuai dengan password yang diinput sebelumnya |
---

# EQUIVALENCE PARTITIONING - REGISTER
---
| Field         | Kelas Valid                               | Kelas Invalid                                                               |
| ------------- | ----------------------------------------- | --------------------------------------------------------------------------- |
| **Full Name** | Huruf & spasi, ≥ 3 huruf                  | Kosong, <3 huruf             |
| **Username**  | 5–15 karakter, huruf/angka                | <5 atau >15 karakter                        |
| **Password**  | ≥6 karakter, kombinasi huruf/angka/simbol | <6 karakteR        |
| **Email**     | Format email valid (`a@b.com`)            | Tanpa `@`, tanpa domain, kosong (`"abc"`, `"a@"`, `"@b.com"`, `""`)         |
| **Phone**     | 11–13 digit angka                         | <10 atau >13 digit, mengandung huruf/simbol (`"08abc56789"`, `"0812-3456"`) |
| **Address**   | ≥5 karakter, huruf/angka/simbol umum      | Kosong atau <5 karakter (`"RT2"`, `""`)                                     |

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


