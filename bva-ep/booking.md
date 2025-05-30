                               
# BOUNDARY VALUE ANALYSIS - Booking
---
| Field         | Validasi Panjang/Range | Nilai Valid                               | Nilai Invalid                    |
| ------------- | ---------------------- | ----------------------------------------------------- | ---------------------------------------------------- |
| **Join Trip** | Login        | Sudah Login                                | Belum Login
| **Add User**  | Login, Passport Aktif |   Login, Passport Aktif   | Belum Register, Passport Tidak Aktif     |
| **Join Trip Succes** | Selesai Payment  | Selesai Payment  | Belum Selesai Payment |
---

# TEST CASE REGISTER
---
| TC ID | Field     | Test Case Description                | Input              | Expected Result                            | Aktual |  Status |
| ----- | --------- | ------------------------------------ | ------------------ | ------------------------------------------ | ------ |----|
| TC01  | Join Trip | belum login            | join             | login     | pindah keform login    |✅|
| TC02  | Join Trip | Sudah login                  | join             | Berhasil                                   | Berhasil      |✅|
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

