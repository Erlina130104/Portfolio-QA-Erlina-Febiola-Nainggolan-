# Manual Testing Documentation

Folder ini berisi dokumentasi lengkap dari manual testing yang dilakukan terhadap website e-commerce (practicesoftwaretesting.com).

## Overview

Saya telah melakukan manual testing komprehensif terhadap aplikasi web e-commerce dengan fokus pada:
- Functional testing
- UI/UX testing
- Negative testing
- Security testing

## Test Case Summary

| No | Feature | Positive Test Case | Negative Test Case | Total |
|----|---------|-------------------|-------------------|-------|
| 1 | Customer Registration | 3 | 9 | 12 |
| 2 | Login | 8 | 6 | 14 |
| 3 | My Account Page | 11 | 1 | 12 |
| 4 | Fitur Home - Product Catalog | 11 | - | 11 |
| 5 | Fitur Categories - Hand Tools | 13 | - | 13 |
| 6 | Fitur Categories - Power Tools | 17 | 1 | 18 |
| 7 | Fitur Categories - Special Tools | 5 | 6 | 11 |
| 8 | Fitur Categories - Rentals | 3 | - | 3 |
| 9 | Sub-section: Product Detail Page (PDP) - Rentals | 10 | - | 10 |
| 10 | Fitur Contact | 5 | 6 | 11 |
| 11 | Security Negative Testing | - | 12 | 12 |
| **Total** | | | | **127** |

## Struktur Folder

Berdasarkan struktur di File Explorer, dokumentasi testing dibagi menjadi:

1. **Fitur Categories - Power Tools** - Testing kategori Power Tools
2. **Fitur Categories - Rentals** - Testing kategori Rentals
3. **Fitur Categories - Special Tools** - Testing kategori Special Tools
4. **Fitur Categories-Hand Tools** - Testing kategori Hand Tools
5. **Fitur Contact** - Testing halaman Contact
6. **Fitur Cutomer Registration** - Testing fitur registrasi pengguna
7. **Fitur Home_Product Catalog** - Testing katalog produk
8. **Fitur Login** - Testing fitur login
9. **My Account Page** - Testing halaman akun pengguna
10. **Security Negative Test** - Testing keamanan aplikasi

## Detail Testing per Feature

### 1. Customer Registration (12 Test Cases)
Testing fitur registrasi dengan berbagai skenario:
- Registrasi dengan data valid (3 positive cases)
- Registrasi dengan field kosong (9 negative cases)
- Validasi format email
- Validasi kekuatan password
- Pesan error yang sesuai

### 2. Login (14 Test Cases)
Testing fitur login dengan:
- Login berhasil dengan kredensial valid (8 positive cases)
- Login gagal dengan berbagai skenario error (6 negative cases)
- Format email invalid
- Password salah
- Field kosong

### 3. My Account Page (12 Test Cases)
Testing fitur di halaman My Account:
- Navigasi menu (11 positive cases)
- Edit profile
- View favorites
- View invoices
- View messages
- Skenario error (1 negative case)

### 4. Product Catalog & Categories (66 Test Cases)
Testing fitur produk meliputi:

**Fitur Home - Product Catalog (11 cases)**
- Search produk
- Filter dan sort
- Pagination

**Kategori Hand Tools (13 cases)**
- Browse produk hand tools
- Filter spesifik kategori

**Kategori Power Tools (18 cases)**
- Browse produk power tools
- Filter dan pencarian
- 1 negative case

**Kategori Special Tools (11 cases)**
- Browse special tools
- 5 positive dan 6 negative cases

**Kategori Rentals (3 cases)**
- Browse produk rental

**Product Detail Page - Rentals (10 cases)**
- Detail produk rental
- Add to cart
- Product information

### 5. Contact (11 Test Cases)
Testing halaman contact:
- Submit contact form (5 positive cases)
- Validasi form (6 negative cases)
- Error messages

### 6. Security Negative Testing (12 Test Cases)
Testing keamanan aplikasi:
- SQL Injection
- XSS (Cross-Site Scripting)
- CSRF protection
- Session management
- Input validation
- Authentication bypass attempts

## Tools yang Digunakan

- **Browser**: Chrome/Firefox untuk manual testing
- **Browser DevTools**: Untuk inspect element dan debugging
- **Postman**: Untuk API testing
- **Screenshot Tools**: Untuk dokumentasi bukti testing

## Metodologi Testing

1. **Test Case Design**: Merancang test cases berdasarkan requirements
2. **Test Execution**: Menjalankan test cases secara manual
3. **Bug Reporting**: Mendokumentasikan bugs yang ditemukan
4. **Test Documentation**: Screenshot dan deskripsi hasil testing

## Bug Severity Classification

- **Critical**: Bug yang membuat aplikasi crash atau data loss
- **High**: Bug yang mempengaruhi fitur utama atau keamanan
- **Medium**: Bug yang mempengaruhi fungsionalitas tetapi ada workaround
- **Low**: Bug kosmetik atau typo yang tidak mempengaruhi fungsionalitas

## Hasil Testing

Dari **127 total test cases** yang dijalankan:
- **Positive Test Cases**: Memverifikasi fitur berjalan sesuai ekspektasi
- **Negative Test Cases**: Memverifikasi error handling dan validasi

Detail hasil testing (Pass/Fail) dapat dilihat di masing-masing folder dokumentasi per feature.

## Catatan Penting

1. Semua testing dilakukan secara **manual** tanpa automation framework
2. Testing dilakukan pada environment: practicesoftwaretesting.com
3. Setiap test case dilengkapi dengan:
   - Test steps
   - Expected result
   - Actual result
   - Screenshot (bila perlu)
   - Status (Pass/Fail)

4. Bug yang ditemukan didokumentasikan dengan:
   - Bug ID
   - Severity level
   - Reproduction steps
   - Expected vs Actual behavior
   - Screenshot/video bukti

## Rekomendasi

Berdasarkan hasil testing, beberapa area yang perlu perhatian khusus:
- **Security**: Perlu penguatan pada input validation dan authentication
- **Error Handling**: Beberapa error message perlu lebih informatif
- **UI/UX**: Beberapa flow bisa diperbaiki untuk user experience yang lebih baik

---

**Tested by**: Erlina Febiola Nainggolan 
**Testing Period**: December 2025  
**Last Updated**: December 4, 2025