# Panduan Fitur Multi-Bahasa 🌐

Sistem multi-bahasa website Anda sudah siap! Berikut penjelasannya:

## ✨ Fitur yang Ditambahkan

### 1. **Language Toggle di Header**
- Tombol bahasa di header sebelah dark mode toggle
- Klik untuk membuka menu pilihan bahasa
- Tersedia: **Bahasa Indonesia** (ID) dan **English** (EN)
- Pilihan bahasa tersimpan di localStorage

### 2. **Terjemahan Lengkap**
Semua teks di halaman telah diterjemahkan ke 2 bahasa:

#### **Bagian yang Sudah Diterjemahkan:**
- ✅ Header dan navigasi
- ✅ Home/Hero section
- ✅ Daftar Dosen (Faculty)
- ✅ Daftar Mahasiswa (Students)
- ✅ Sumber Belajar (Resources)
- ✅ Auth Modal (Login/Register)
- ✅ Tombol dan pesan error
- ✅ Footer

### 3. **Sistem Terjemahan yang Fleksibel**

File menggunakan sistem berbasis `data-i18n` attributes:

```html
<!-- Terjemahan untuk text content -->
<h2 data-i18n="header.welcome"></h2>

<!-- Terjemahan untuk placeholder -->
<input data-i18n-placeholder="auth.email" type="email" />

<!-- Terjemahan untuk title/tooltip -->
<button data-i18n-title="header.change-lang"></button>
```

### 4. **JavaScript Functions**

```javascript
// Dapatkan bahasa saat ini
getCurrentLanguage()  // Returns: 'id' atau 'en'

// Set bahasa baru
setLanguage('en')     // Ubah ke Inggris

// Dapatkan terjemahan
t('header.welcome')   // Return text sesuai bahasa aktif

// Update semua terjemahan di halaman
updateAllTranslations('id')
```

## 🎯 Cara Menggunakan

### **Bagi User:**
1. Klik tombol bahasa di header (sebelah dark mode toggle)
2. Pilih **Bahasa Indonesia** atau **English**
3. Seluruh halaman akan berubah bahasa secara instant
4. Pilihan bahasa akan tersimpan otomatis

### **Bagi Developer - Menambah Terjemahan Baru:**

1. Tambahkan key di object `translations`:
```javascript
translations = {
  id: {
    'your.key': 'Teks Bahasa Indonesia',
  },
  en: {
    'your.key': 'English Text',
  }
}
```

2. Gunakan di HTML:
```html
<span data-i18n="your.key"></span>
```

3. Atau via JavaScript:
```javascript
const text = t('your.key');  // Untuk bahasa saat ini
const text = t('your.key', 'en');  // Untuk bahasa spesifik
```

## 📋 Daftar Terjemahan

### **Header (header.***)**
- welcome: Welcome message
- loading-date: Date loading text
- guest: Guest name
- login: Login button
- logout: Logout button
- change-lang: Language tooltip
- change-theme: Theme tooltip

### **Navigation (nav.***)**
- home: Beranda / Home
- dosen: Dosen / Faculty
- mahasiswa: Mahasiswa / Students
- resources: Resources
- about: Tentang / About

### **Home Section (home.***)**
- hero-title: Lab title
- hero-subtitle: Lab description
- explore: Explore button
- about: About button

### **Dosen Table (dosen.***)**
- title: Table title
- no: Number column
- name: Faculty name column
- expertise: Expertise column
- email: Email column
- room: Room column

### **Mahasiswa Table (mahasiswa.***)**
- title: Table title
- no: Number column
- name: Student name column
- nim: Student ID column
- research: Research topic column
- advisor: Advisor column

### **Resources (resources.***)**
- title: Section title
- library: National Digital Library
- library-desc: Description
- scholar: Google Scholar
- scholar-desc: Description
- portal: Campus Academic Portal
- portal-desc: Description
- ejornal: E-Journal Directory
- ejornal-desc: Description

### **Auth Modal (auth.***)**
- title: Modal title
- email: Email placeholder
- password: Password placeholder
- login: Login button
- register: Register button
- close: Close button
- success-login: Success message
- success-register: Register success message
- error-email: Email already registered
- error-login: Email/password incorrect
- error-empty: Empty field error

### **Footer (footer.***)**
- copyright: Copyright text

## 💾 Penyimpanan Preferensi

Bahasa yang dipilih user disimpan di localStorage dengan key: `site-language`

```javascript
// Ambil bahasa tersimpan
localStorage.getItem('site-language')  // Returns: 'id' atau 'en'

// Set bahasa baru
localStorage.setItem('site-language', 'en')
```

## 🔄 Auto-Initialize

Sistem bahasa secara otomatis:
1. ✅ Memuat preferensi bahasa saat halaman load
2. ✅ Menerapkan terjemahan ke semua elemen
3. ✅ Update atribut `lang` pada `<html>` element
4. ✅ Siap untuk toggle bahasa kapan saja

## 📝 Catatan Penting

- **Default bahasa**: **English (EN)** ⭐
- **Fallback bahasa**: Jika key tidak ditemukan, menggunakan terjemahan Bahasa Indonesia
- **Case sensitive**: Key terjemahan bersifat case-sensitive
- **Real-time update**: Semua perubahan bahasa langsung terlihat di UI
- **Simpan kedua bahasa**: Semua konten tersedia dalam Bahasa Indonesia dan English

## 🎯 Behavior Awal

Saat user pertama kali membuka website:
- ✅ Bahasa default: **ENGLISH (EN)** 
- ✅ User TIDAK perlu mentranslate konten manual
- ✅ User tetap bisa switch ke Bahasa Indonesia via language toggle
- ✅ Pilihan user akan disimpan & digunakan lagi di kunjungan berikutnya

## ✅ Testing Checklist

- [x] Language toggle muncul di header
- [x] Semua terjemahan dalam object translations
- [x] Semua elemen HTML punya data-i18n attributes
- [x] localStorage menyimpan preferensi bahasa
- [x] Perubahan bahasa instantly update UI
- [x] Pesan auth berubah sesuai bahasa
- [x] Placeholder input berubah sesuai bahasa
- [x] Tidak ada JavaScript errors

Selamat! Website Anda sekarang fully multi-language! 🎉
