# BOUNDARY VALUE ANALYSIS - REGISTER
---
| Field                | Validasi Panjang/Range     | Nilai Valid                                   | Nilai Invalid                           |
| -------------------- | -------------------------- | --------------------------------------------- | --------------------------------------- |
| *Name*             | Minimal 3 karakter         | "asi" (3) ✅                                   | "As" (2), "" ❌                          |
| *Username*         | 3–15 karakter              | "abc" (3), "abcdefghijklmno" (15) ✅           | "ab" (2), "abcdefghijklmnop" (16), "" ❌ |
| *Email*            | Format email valid         | "[mail@domain.com](mailto:mail@domain.com)" ✅ | "mail@", "@domain", "mail.com" ❌        |
| *Password*         | Minimal 8 karakter         | "pass1234" (8) ✅                              | "1234567" (7), "" ❌                     |
| *Confirm Password* | Harus sama dengan password | Sama: "pass1234" ✅                            | Berbeda: "pass123", "" ❌                |---

# EQUIVALENCE PARTITIONING - REGISTER
---
| Field                | Kelas Valid                                      | Kelas Invalid                                                                    |
| -------------------- | ------------------------------------------------ | -------------------------------------------------------------------------------- |
| *Name*             | ≥3 huruf, hanya huruf/spasi ("John", "Ali Raza") | <3 karakter, kosong, ada angka/simbol ("Jo", "", "Jo3n", "An@")                  |
| *Username*         | 3–15 karakter, huruf dan angka saja              | <3 atau >15 karakter, ada simbol/spasi ("us", "toolongusernameee", "user\_name") |
| *Email*            | Format lengkap: a@b.com                        | Tanpa '@', tanpa domain, kosong ("abc", "a@", "@b.com", "")                      |
| *Password*         | ≥8 karakter, kombinasi huruf/angka/simbol        | <8 karakter, hanya huruf/angka, kosong ("pass12", "1234567", "")                 |
| *Confirm Password* | Sesuai dengan password                             | Tidak sesuai dengan password, kosong                                               |
---
# Test Case
|TC ID | Deskripsi | Input | Excpect | Aktual | Status |
|---|---|---|---|---|---|
|TC01 | Input nama > 3 karakter | `sa`,`sandirsndi`,`san@gmail.com`,`sandi123`,`sandi123`| Error:nama minimal 3| Valid| ❌Failed|
|TC02 | Input nama tepat minimal (1) | `s`,`sandirsndi`,`san@gmail.com`,`sandi123`,`sandi123` | Valid | Valid | ✅Passed|
|TC03 | Input Username > 5 Karakter | `s`,`sans`,`san@gmail.com`,`sandi123`,`sandi123` | Error: Username minimal 5 karakter | Valid | ❌Failed|
|TC04 | Input username tepat minimal (1) | `s`,`sans`,`san@gmail.com`,`sandi123`,`sandi123`| Valid | Valid | ✅Passed |
|TC05 | Input Email tanpa @ | `zasgmail.com` | Error:format email missing an @ | Pesan error berhasil ditampilkan | ✅Passed |
|TC06 | Input password non kombinasi | `12345` | Error:password harus mengandung angka dan huruf | Valid |  ❌Failed |
|TC07 | Input kombinasi password | `zas12345` | Valid | Valid | ✅Passed |
|TC08 | Input Confirm password | Sama: `zas1234` | valid | valid | ✅Passed |
|TC09 | Input Confirm password berbeda | berbeda : `12345` | Error:password harus sesuai | Invalid | ❌Failed |




