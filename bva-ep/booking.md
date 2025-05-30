# Parameter Penilaian 
| Field     | Parameter Validasi                     | Jenis Pengujian | Alasan Valid/Invalid                              |
| --------- | -------------------------------------- | --------------- | ------------------------------------------------- |
| Join Trip | Login / Register                       | BVA        | Valid: Login / Register, Invalid : Belum Login / Register |
| Add User | User yang sudah registrasi, Passport Aktif                       | BVA        | Valid: Sudah Register,Passport Aktif, Invalid : Belum Register, Passport Tidak Aktif |
| Join Trip Succes | Selesai Payment                       | BVA        | Valid: Selesai Payment, Invalid : Belum Selesai Payment |
                                                                          
# BOUNDARY VALUE ANALYSIS - Booking
---
| Field         | Validasi Panjang/Range | Nilai Valid                               | Nilai Invalid                    |
| ------------- | ---------------------- | ----------------------------------------------------- | ---------------------------------------------------- |
| **Join Trip** | Login        | Sudah Login                                | Belum Login
| **Add User**  | Login, Passport Aktif |   Login, Passport Aktif   | Belum Register, Passport Tidak Aktif     |
| **Join Trip Succes** | Selesai Payment  | Selesai Payment  | Belum Selesai Payment |
---

