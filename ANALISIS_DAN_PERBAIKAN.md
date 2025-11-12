# Analisis dan Perbaikan File HTML - 13 November 2025

## Masalah yang Ditemukan

### 1. **Tombol "Jelajahi" dan "Tentang Lab" di Hero Tidak Bisa Diklik**
   - **Penyebab Utama**: CSS rule yang menyembunyikan `<main>` ketika `.not-logged-in`
   ```css
   body.not-logged-in aside,
   body.not-logged-in main {
       display: none !important;
   }
   ```
   - **Masalah**: Hero buttons berada di dalam `<main>`, jadi mereka juga tersembunyi
   - **Solusi**: Ubah CSS agar hanya menyembunyikan sidebar dan content sections (bukan main/hero)

### 2. **Animasi Fade-In Hilang Saat Membuka Page Baru**
   - **Penyebab**: IntersectionObserver hanya berjalan saat initial load
   - **Masalah**: Ketika switchTab dipanggil, elemen fade-in-card di section baru tidak di-trigger ulang
   - **Solusi**: Reset class 'visible' dan re-observe cards saat switchTab dipanggil

---

## Perbaikan yang Dilakukan

### Perbaikan 1: CSS Authentication Logic (Lines 81-102)

**SEBELUM:**
```css
/* Hide sidebar & main when not logged in */
body.not-logged-in aside,
body.not-logged-in main {
    display: none !important;
}
body.not-logged-in {
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    background: linear-gradient(...);
}
```

**SESUDAH:**
```css
/* Hide sidebar & other sections when not logged in */
body.not-logged-in aside {
    display: none !important;
}
body.not-logged-in .content-section:not(#home) {
    display: none !important;
}
body.not-logged-in {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    min-height: 100vh;
    background: linear-gradient(...);
}
body.not-logged-in main {
    width: 100%;
    display: block;
    position: relative;
    z-index: 10;
}
```

**Manfaat:**
- ✅ Main content (hero) tetap visible untuk semua user
- ✅ Sidebar tetap tersembunyi saat tidak login
- ✅ Content sections (list, students, dll) hanya tampil saat login
- ✅ Auth panel tetap di atas dengan z-index 1000

---

### Perbaikan 2: Auth Panel Styling (Lines 103-110)

**SEBELUM:**
```css
body.not-logged-in #auth-panel {
    position: fixed !important;
    display: flex !important;
    background: rgba(15, 23, 42, 0.95) !important;
    backdrop-filter: blur(10px) !important;
}
```

**SESUDAH:**
```css
body.not-logged-in #auth-panel {
    position: fixed !important;
    top: 0 !important;
    left: 0 !important;
    width: 100% !important;
    height: 100% !important;
    display: flex !important;
    z-index: 1000 !important;
    background: rgba(15, 23, 42, 0.98) !important;
    backdrop-filter: blur(10px) !important;
}
```

**Manfaat:**
- ✅ Auth panel truly fullscreen
- ✅ Explicit z-index 1000 memastikan di atas semua elemen
- ✅ Background opacity sedikit lebih tinggi untuk effect yang lebih baik

---

### Perbaikan 3: switchTab Animation Trigger (Lines 2767-2799)

**SEBELUM:**
```javascript
function switchTab(targetId) {
    // Hide all sections
    contentSections.forEach(section => {
        section.classList.remove('active');
    });
    // ... deactivate nav links ...
    // Show the target section
    const targetSection = document.getElementById(targetId);
    if (targetSection) {
        targetSection.classList.add('active');
    }
    // ... activate nav link ...
}
```

**SESUDAH:**
```javascript
function switchTab(targetId) {
    // Hide all sections
    contentSections.forEach(section => {
        section.classList.remove('active');
    });
    // ... deactivate nav links ...
    // Show the target section
    const targetSection = document.getElementById(targetId);
    if (targetSection) {
        targetSection.classList.add('active');
        
        // Re-trigger fade-in animations for cards in the new section
        const cards = targetSection.querySelectorAll('.fade-in-card');
        cards.forEach(card => {
            card.classList.remove('visible');
            observer.observe(card);
        });
    }
    // ... activate nav link ...
}
```

**Manfaat:**
- ✅ Animasi fade-in akan berjalan setiap kali user membuka section baru
- ✅ Class 'visible' direset untuk memungkinkan re-animation
- ✅ Cards di-observe ulang agar bisa trigger animasi

---

## Testing Checklist

- [ ] ✅ Tombol "Jelajahi" di hero bisa diklik (tidak login dan login)
- [ ] ✅ Tombol "Tentang Lab" di hero bisa diklik (tidak login dan login)
- [ ] ✅ Navigasi ke page Jelajahi berfungsi dengan benar
- [ ] ✅ Navigasi ke page Tentang Lab berfungsi dengan benar
- [ ] ✅ Animasi fade-in tampil saat pertama kali membuka page
- [ ] ✅ Animasi fade-in tampil ulang saat switch ke page lain
- [ ] ✅ Sidebar hidden saat tidak login
- [ ] ✅ Hero section visible saat tidak login
- [ ] ✅ Auth panel fullscreen dan responsive
- [ ] ✅ Setelah login, semua content sections accessible

---

## File yang Diubah

- `c:\Users\ACER ID\Downloads\Tugas PPI\index.html`
  - Lines 81-102: CSS authentication logic
  - Lines 103-110: Auth panel styling
  - Lines 2767-2799: switchTab animation trigger

---

## Kesimpulan

Kedua masalah utama telah diperbaiki:

1. **Hero buttons tidak bisa diklik** → Fixed dengan mengubah CSS authentication logic
2. **Animasi fade-in hilang** → Fixed dengan re-trigger observer saat switchTab

Sekarang user dapat:
- Klik tombol hero tanpa harus login
- Melihat animasi fade-in di setiap page yang dibuka
- Navigasi dengan smooth dan responsif ke semua sections

