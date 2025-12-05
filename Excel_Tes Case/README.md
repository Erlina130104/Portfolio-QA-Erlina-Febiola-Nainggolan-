# Test Case Documentation

Folder ini berisi file Excel lengkap dengan 127 test case yang dibuat untuk website e-commerce (practicesoftwaretesting.com).

## Daftar File

- `Test_Case_Website_Erlina Febiola Nainggolan.xlsx` - File lengkap dengan semua 127 test case

## Overview

Dokumentasi test case ini mencakup pengujian menyeluruh terhadap berbagai fitur website e-commerce, mulai dari registrasi pengguna, login, manajemen akun, katalog produk, hingga pengujian keamanan.

## Struktur Test Case

Setiap test case di-dokumentasikan dengan struktur berikut:

| Kolom | Deskripsi |
|-------|-----------|
| **TC ID** | Identitas unik untuk setiap test case (contoh: REG-001, LGN-002) |
| **Test Case Title** | Judul singkat yang mendeskripsikan test case |
| **Priority** | Tingkat kepentingan (High, Medium, Low) |
| **Type** | Jenis test (Functional, Validation, UI, Negative, dll) |
| **Pre-condition** | Kondisi awal yang harus terpenuhi sebelum test dijalankan |
| **Test Steps** | Langkah-langkah detail yang harus dilakukan |
| **Test Data** | Data spesifik yang digunakan untuk testing |
| **Expected Result** | Hasil yang diharapkan terjadi |
| **Actual Result** | Hasil aktual yang terjadi saat test dijalankan |
| **Status** | PASS atau FAIL |
| **Note** | Catatan tambahan atau penjelasan |
| **Severity** | Tingkat keparahan bug (jika ada: Critical, High, Medium, Low) |
| **Severity Impact** | Dampak dari bug terhadap sistem |
| **Link JIRA** | Link ke bug report di JIRA (jika ada) |

## Kategori Test Case

### Summary Test Case per Feature

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
| **Total** | | **86** | **41** | **127** |

### Detail Test Case per Feature

#### 1. Customer Registration (12 Test Cases)

Testing fitur registrasi pengguna baru meliputi:

**Positive Test Cases (3):**
- REG-001: Verifikasi tampilan halaman registrasi
- REG-002: Registrasi dengan semua field valid
- REG-003: Validasi indikator kekuatan password

**Negative Test Cases (9):**
- REG-004: Registrasi tanpa mengisi field wajib
- REG-005: Validasi format email salah
- REG-006: Validasi panjang password kurang dari 8 karakter
- REG-007: Validasi password tanpa huruf besar (FAILED)
- REG-008: Validasi password tanpa karakter spesial (FAILED)
- REG-009: Validasi indikator kekuatan password
- REG-010: Validasi format tanggal lahir salah
- REG-011: Validasi nomor telepon bukan angka
- REG-012: Validasi tombol "Register" nonaktif sebelum field diisi (FAILED)

#### 2. Login (14 Test Cases)
Testing fitur login dengan berbagai skenario kredensial valid dan invalid.

#### 3. My Account Page (12 Test Cases)
Testing fungsionalitas halaman akun pengguna mencakup navigasi menu, edit profile, view favorites, view invoices, dan view messages.

#### 4. Fitur Home - Product Catalog (11 Test Cases)
Testing katalog produk di halaman utama termasuk display produk, search functionality, filter dan sorting, serta pagination.

#### 5. Fitur Categories - Hand Tools (13 Test Cases)
Testing kategori Hand Tools dengan berbagai skenario browse dan filter.

#### 6. Fitur Categories - Power Tools (18 Test Cases)
Testing kategori Power Tools termasuk 1 negative test case.

#### 7. Fitur Categories - Special Tools (11 Test Cases)
Testing kategori Special Tools dengan 5 positive dan 6 negative test cases.

#### 8. Fitur Categories - Rentals (3 Test Cases)
Testing kategori Rentals untuk produk sewa.

#### 9. Product Detail Page - Rentals (10 Test Cases)
Testing halaman detail produk kategori Rentals termasuk product information display, add to cart functionality, product specifications, dan related products.

#### 10. Fitur Contact (11 Test Cases)
Testing form kontak dengan 5 positive dan 6 negative test cases.

#### 11. Security Negative Testing (12 Test Cases)
Testing keamanan aplikasi mencakup SQL Injection testing, XSS testing, authentication testing, authorization testing, dan input validation testing.

## Hasil Testing

| Metric | Jumlah | Persentase |
|--------|--------|------------|
| **Total Test Case** | 127 | 100% |
| **Status PASS** | 119 | 93.7% |
| **Status FAIL** | 8 | 6.3% |

Dari 127 test case yang dieksekusi, 119 test case berhasil dan 8 test case gagal karena ditemukan bug.

**Breakdown Hasil Testing:**
- Positive Test Cases: 86 test cases - memverifikasi fitur berjalan sesuai ekspektasi
- Negative Test Cases: 41 test cases - memverifikasi error handling dan validasi input

## Bug yang Ditemukan

Dari 127 test case yang dijalankan, ditemukan 8 bug. Berikut adalah 3 bug utama dari fitur Customer Registration:

### 1. REG-007: Password Validation - Missing Uppercase
- **Severity**: Medium
- **Issue**: Error message tidak akurat dan misleading
- **Expected**: "Password harus mengandung minimal 1 huruf besar"
- **Actual**: "Password can not include invalid characters"
- **Impact**: User experience buruk karena pesan error membingungkan
- **Link**: [KAN-12](https://erlina-qa-portfolio.atlassian.net/browse/KAN-12)

### 2. REG-008: Password Validation - Missing Special Character
- **Severity**: Medium
- **Issue**: Error message tidak informatif
- **Expected**: "Password harus mengandung minimal 1 karakter spesial"
- **Actual**: "Password can not include invalid characters"
- **Impact**: User tidak tahu apa yang salah dengan password mereka
- **Link**: [KAN-13](https://erlina-qa-portfolio.atlassian.net/browse/KAN-13)

### 3. REG-012: Register Button Not Disabled
- **Severity**: Medium
- **Issue**: Tombol Register bisa diklik sebelum field wajib diisi
- **Expected**: Tombol Register disabled sampai semua field wajib terisi
- **Actual**: Tombol bisa diklik dan muncul banyak error sekaligus
- **Impact**: User experience buruk, user bisa submit form kosong
- **Link**: [KAN-14](https://erlina-qa-portfolio.atlassian.net/browse/KAN-14)

Bug lainnya (nomor 4-8) tersimpan dalam file Excel dan folder Manual Testing.

## Testing Methodology

**Test Case Design**
- Berdasarkan requirements dan user stories
- Menggunakan teknik Equivalence Partitioning dan Boundary Value Analysis
- Mencakup positive dan negative scenarios

**Test Execution**
- Manual testing tanpa automation tools
- Testing dilakukan pada environment: https://practicesoftwaretesting.com
- Browser yang digunakan: Chrome/Firefox
- Dokumentasi dengan screenshot untuk setiap bug

**Bug Reporting**
- Setiap bug didokumentasikan di JIRA/Atlassian
- Include: reproduction steps, expected vs actual result, severity, screenshot
- Link bug report disertakan di kolom test case

## Severity Classification

| Level | Deskripsi | Contoh |
|-------|-----------|--------|
| **Critical** | Sistem crash, data loss, security breach | SQL Injection berhasil |
| **High** | Fitur utama tidak berfungsi | Login gagal dengan kredensial valid |
| **Medium** | Fitur berfungsi tapi ada issue pada UX/validasi | Error message tidak jelas |
| **Low** | Typo, alignment, warna tidak sesuai | Typo pada label |

## Cara Menggunakan File Ini

1. Buka file Excel: `Test_Case_Website_Erlina Febiola Nainggolan.xlsx`
2. Pilih sheet feature yang ingin ditest
3. Ikuti langkah-langkah di kolom "Test Steps"
4. Gunakan test data yang tertera di kolom "Test Data"
5. Dokumentasikan hasil:
   - Catat hasil di kolom "Actual Result"
   - Tandai PASS atau FAIL di kolom "Status"
   - Tambahkan screenshot jika menemukan bug
6. Report bug: Jika FAIL, dokumentasikan di JIRA dan tambahkan link

## Tools yang Digunakan

- Excel/Google Sheets untuk dokumentasi test case
- Browser DevTools untuk inspect element dan debugging
- JIRA/Atlassian untuk bug tracking dan project management
- Screenshot tools untuk dokumentasi visual bug
- Postman untuk API testing (jika diperlukan)

## Kesimpulan

Dari 127 test case yang dieksekusi, 93.7% test case berhasil dan 6.3% test case gagal. Mayoritas fitur berfungsi dengan baik, namun ditemukan 8 bug yang perlu diperbaiki, terutama terkait validasi dan error message yang kurang informatif.

## Rekomendasi

1. Perbaiki error messages agar lebih spesifik dan membantu user
2. Improve password validation dengan menampilkan requirement password secara jelas
3. Implementasi button state management untuk disable tombol submit sampai form valid
4. Enhance security testing dengan menambah test case untuk penetration testing
5. Pertimbangkan automation untuk regression testing di masa depan

---

**Created by**: Erlina Febiola Nainggolan  
**Testing Period**: December 2025  
**Last Updated**: December 4, 2025  
**Environment**: https://practicesoftwaretesting.com