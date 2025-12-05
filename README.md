# Portfolio QA Tester - Erlina Febiola Nainggolan

Halo, saya Erlina Febiola Nainggolan, seorang QA Tester dengan pengalaman dalam melakukan testing aplikasi web dan API. Di repository ini saya dokumentasikan semua pekerjaan testing yang sudah saya lakukan.

## Tentang Portfolio Ini

Portfolio ini berisi dokumentasi lengkap dari testing yang saya lakukan pada website e-commerce (practicesoftwaretesting.com). Testing mencakup manual testing, API testing, test automation, dan security testing.

Saya sudah membuat dan menjalankan 127 test case dengan hasil 93.7% pass dan 6.3% fail. Dari testing ini, saya menemukan 8 bug yang perlu diperbaiki, termasuk 3 security vulnerabilities dengan tingkat keparahan critical.

## Struktur Folder

### Excel_Test_Case
Folder ini berisi file Excel dengan 127 test case yang sudah saya dokumentasikan. Test case mencakup semua fitur utama website:
- Customer Registration (12 test case)
- User Login (14 test case)
- My Account Page (12 test case)
- Fitur Home - Product Catalog (11 test case)
- Fitur Categories - Hand Tools (13 test case)
- Fitur Categories - Power Tools (18 test case)
- Fitur Categories - Special Tools (11 test case)
- Fitur Categories - Rentals (3 test case)
- Sub-section: Product Detail Page - Rentals (10 test case)
- Fitur Contact (11 test case)
- Security Negative Testing (12 test case)

Setiap test case punya dokumentasi lengkap mulai dari TC ID, priority, type, pre-condition, test steps, test data, expected result, actual result, status (PASS/FAIL), catatan tambahan, severity, sampai link JIRA untuk bug tracking.

### Manual_Testing
Folder ini berisi dokumentasi dari test case yang sudah dijalankan secara manual. Di dalam folder ini ada screenshot hasil testing, bug report, dan temuan security vulnerability.

Strukturnya dibagi per fitur:
- Fitur Categories - Power Tools
- Fitur Categories - Rentals
- Fitur Categories - Special Tools
- Fitur Categories-Hand Tools
- Fitur Contact
- Fitur Cutomer Registration
- Fitur Home_Product Catalog
- Fitur Login
- My Account Page
- Security Negative Test

### Bug_Reports
Folder ini berisi bug report lengkap yang sudah saya buat di JIRA. Setiap bug didokumentasikan dengan format standar industri yang mencakup:
- Bug ID dan tracking number
- Title dan description yang jelas
- Priority/Severity level
- Steps to reproduce yang detail
- Expected vs Actual result
- Screenshot sebagai bukti
- Label dan kategori bug

Contoh bug report yang ada:
- KAN-9: Stored XSS vulnerability di Registration
- KAN-10: Reflected XSS di Search
- KAN-11: No Brute Force Protection di Login
- KAN-12: Password validation error message misleading
- KAN-13: Password special character validation issue
- KAN-14: Register button not disabled validation

### tes_api
Di folder ini saya dokumentasikan API testing yang dilakukan dengan Postman. Testing mencakup beberapa endpoint penting:
- Login endpoint (POST)
- Get Products endpoint (GET)
- Add to Cart endpoint (POST)
- User Profile endpoint (GET)
- Negative test cases

Dari hasil testing, semua endpoint berjalan sesuai ekspektasi. Namun ada beberapa vulnerability yang perlu diperbaiki dari sisi security.

### tes_automation
Folder ini berisi script test automation yang saya buat dengan Selenium. Ada 4 script automation yang sudah dibuat:
- Login automation
- Product search automation
- Product filtering automation
- Add to cart automation

## Hasil Testing

| Metric | Jumlah | Persentase |
|--------|--------|------------|
| Total Test Case | 127 | 100% |
| Status PASS | 119 | 93.7% |
| Status FAIL | 8 | 6.3% |

### Breakdown Test Case

| No | Feature | Positive | Negative | Total |
|----|---------|----------|----------|-------|
| 1 | Customer Registration | 3 | 9 | 12 |
| 2 | Login | 8 | 6 | 14 |
| 3 | My Account Page | 11 | 1 | 12 |
| 4 | Fitur Home - Product Catalog | 11 | - | 11 |
| 5 | Fitur Categories - Hand Tools | 13 | - | 13 |
| 6 | Fitur Categories - Power Tools | 17 | 1 | 18 |
| 7 | Fitur Categories - Special Tools | 5 | 6 | 11 |
| 8 | Fitur Categories - Rentals | 3 | - | 3 |
| 9 | Product Detail Page - Rentals | 10 | - | 10 |
| 10 | Fitur Contact | 5 | 6 | 11 |
| 11 | Security Negative Testing | - | 12 | 12 |

### Bug & Vulnerability yang Ditemukan

#### Customer Registration Bugs (Medium Severity)

**1. REG-007: Password Validation - Missing Uppercase**
- **Severity**: Medium
- **Issue**: Error message tidak akurat dan misleading
- **Expected**: "Password harus mengandung minimal 1 huruf besar"
- **Actual**: "Password can not include invalid characters"
- **Impact**: User experience buruk karena pesan error membingungkan
- **Bug Report**: [KAN-12](https://erlina-qa-portfolio.atlassian.net/browse/KAN-12) - Documented in JIRA

**2. REG-008: Password Validation - Missing Special Character**
- **Severity**: Medium
- **Issue**: Error message tidak informatif
- **Expected**: "Password harus mengandung minimal 1 karakter spesial"
- **Actual**: "Password can not include invalid characters"
- **Impact**: User tidak tahu apa yang salah dengan password mereka
- **Bug Report**: [KAN-13](https://erlina-qa-portfolio.atlassian.net/browse/KAN-13) - Documented in JIRA

**3. REG-012: Register Button Not Disabled**
- **Severity**: Medium
- **Issue**: Tombol Register bisa diklik sebelum field wajib diisi
- **Expected**: Tombol Register disabled sampai semua field wajib terisi
- **Actual**: Tombol bisa diklik dan muncul banyak error sekaligus
- **Impact**: User experience buruk, user bisa submit form kosong
- **Bug Report**: [KAN-14](https://erlina-qa-portfolio.atlassian.net/browse/KAN-14) - Documented in JIRA

#### Contact Form Bug (Medium Severity)

**4. CNT-001: Misleading Error Message**
- **Severity**: Medium
- **Issue**: Error message "Currently we only allow empty files" muncul meskipun tidak ada file yang di-upload
- **Expected**: Pesan terkirim atau error spesifik jika ada masalah
- **Actual**: Muncul error yang tidak relevan
- **Impact**: User confusion dan tidak bisa mengirim pesan

#### Security Vulnerabilities (Critical Severity)

**5. SEC-004: Stored XSS di Registration Form**
- **Severity**: Critical
- **Type**: Stored XSS
- **Location**: First Name field di halaman registrasi
- **Reproduction**: Input `<script>alert('XSS')</script>` di field First Name
- **Impact**: Script tersimpan di database dan dapat dieksekusi, risiko pencurian session dan injeksi script berbahaya
- **Bug Report**: [KAN-9](https://erlina-qa-portfolio.atlassian.net/browse/KAN-9) - Documented in JIRA with complete steps to reproduce, expected vs actual result, and screenshot evidence

**6. SEC-006: Reflected XSS di Search**
- **Severity**: Critical
- **Type**: Reflected XSS
- **Location**: Search bar di halaman Home
- **Reproduction**: Search dengan input `<script>alert('Hacked')</script>`
- **Impact**: Script berhasil dijalankan (alert muncul), dapat dipakai untuk phishing dan mencuri cookie
- **Bug Report**: [KAN-10](https://erlina-qa-portfolio.atlassian.net/browse/KAN-10) - Documented in JIRA

**7. SEC-007: No Brute Force Protection**
- **Severity**: Critical
- **Type**: Authentication Security
- **Location**: Login page
- **Issue**: Tidak ada pembatasan percobaan login
- **Impact**: Password dapat ditebak dengan ribuan percobaan (brute force attack)
- **Bug Report**: [KAN-11](https://erlina-qa-portfolio.atlassian.net/browse/KAN-11) - Documented in JIRA

**8. Bug lainnya dari testing lain** (detail ada di dokumentasi manual testing dan file Excel)

## Testing Methodology

**Test Case Design**
- Dibuat berdasarkan requirements dan user stories
- Menggunakan teknik Equivalence Partitioning dan Boundary Value Analysis
- Mencakup skenario positive dan negative

**Test Execution**
- Manual testing untuk functional dan UI testing
- Automation testing menggunakan Selenium
- API testing dengan Postman
- Security testing untuk menemukan vulnerability

**Bug Reporting**
- Bug didokumentasikan di JIRA/Atlassian dengan format standar industri
- Dokumentasi lengkap: Bug ID, title, description, priority/severity
- Steps to reproduce yang detail dan bisa diikuti
- Expected vs Actual result yang jelas
- Screenshot dan bukti visual
- Label dan kategori bug (functional, security, UI, etc)
- Setiap bug dilengkapi dengan link JIRA untuk tracking

## Tools yang Digunakan

- **Postman** - API testing dan dokumentasi
- **Selenium** - Test automation
- **Browser DevTools** - Debugging dan inspection
- **Excel/Google Sheets** - Dokumentasi test case
- **JIRA/Atlassian** - Bug tracking, project management, dan issue documentation
- **Screenshot Tools** - Dokumentasi visual bug

## Keahlian yang Ditunjukkan

### Manual Testing
- Functional Testing
- UI/UX Testing
- Negative Testing
- Validation Testing

### Automation Testing
- Selenium WebDriver
- Test Script Development
- Page Object Model

### API Testing
- REST API Testing
- Postman Collection
- Request/Response Validation
- Negative API Testing

### Security Testing
- XSS (Cross-Site Scripting)
- SQL Injection
- CSRF Protection
- Authentication Testing
- Brute Force Testing

### Documentation
- Test Case Documentation
- Bug Reporting dengan JIRA
- Test Summary Report
- Severity Classification

## Severity Classification

| Level | Deskripsi | Contoh |
|-------|-----------|--------|
| Critical | Sistem crash, data loss, security breach | XSS, SQL Injection, No brute force protection |
| High | Fitur utama tidak berfungsi | Login gagal dengan kredensial valid |
| Medium | Fitur berfungsi tapi ada issue pada UX/validasi | Error message tidak jelas |
| Low | Typo, alignment, warna tidak sesuai | Typo pada label |

## Website yang Ditest

**URL**: https://practicesoftwaretesting.com  
**Type**: E-commerce Website  
**Testing Period**: December 2025

## Kontak

**Email**: erlinanainggolan130104@gmail.com  
**LinkedIn**: https://www.linkedin.com/in/erlina-febiola-nainggolan-293b11368/?trk=opento_sprofile_details  
**GitHub**: github.com/Erlina130104  
**Portfolio JIRA**: https://erlina-qa-portfolio.atlassian.net

---

Terima kasih sudah melihat portfolio saya. Dokumentasi ini dibuat untuk menunjukkan kemampuan saya di bidang Quality Assurance dan Testing.