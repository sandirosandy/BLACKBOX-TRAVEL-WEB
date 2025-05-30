                               
# BOUNDARY VALUE ANALYSIS - Booking
---
| Field         | Validasi Panjang/Range | Nilai Valid                               | Nilai Invalid                    |
| ------------- | ---------------------- | ----------------------------------------------------- | ---------------------------------------------------- |
| **Join Trip** | Login        | Sudah Login                                | Belum Login
| **Add User**  | Register, Passport Aktif |   Register, Passport Aktif   | Belum Register, Passport Tidak Aktif     |
| **Join Trip Succes** | Selesai Payment  | Selesai Payment  | Belum Selesai Payment |
---

# TEST CASE REGISTER
---
| TC ID | Field     | Test Case Description                | Input              | Expected Result                            | Aktual |  Status |
| ----- | --------- | ------------------------------------ | ------------------ | ------------------------------------------ | ------ |----|
| TC01  | Join Trip | belum login            | join             | login     | pindah keform login    |✅|
| TC02  | Join Trip | Sudah login                  | join             | Berhasil                                   | Berhasil      |✅|
| TC03  | Add User  | belum terdaftar                 | add           | Gagal        | gagal      |✅|
| TC04  | Add User  | terdaftar           | add                                | Berhasil      |berhasil ditambahkan|✅|
| TC05  | Add User  | Passport aktif | add  | berhasil ditambahkan                                   | User berhasil ditambahkan      |✅|
| TC06  | Add User  | Passport tidak aktif                  | add | gagal         | user berhasil ditambahkan     |❌|
| TC06  | Join trip success  | belum pembayaran                 | pending | pending         | pending    |✅|
| TC06  | Join trip success  | selesai pembayaran                | success | payment success         | success     |✅|
