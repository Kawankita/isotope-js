# **Created by rizky**

```markdown
# Isotope JS Documentation

Isotope JS adalah sebuah perpustakaan JavaScript yang digunakan untuk memfilter dan menyortir elemen-elemen pada halaman web. Isotope membantu dalam membuat tata letak grid dinamis dan interaktif, seperti galeri gambar, daftar produk, atau konten lainnya.

## Fitur

- **Penyortiran Dinamis:** Elemen dapat disusun ulang secara dinamis berdasarkan kategori atau atribut tertentu.
- **Filter Konten:** Pengguna dapat menyaring konten yang ingin ditampilkan berdasarkan kategori yang diinginkan.
- **Layout Grid Responsif:** Menyediakan tata letak grid yang responsif untuk mendukung berbagai ukuran layar.
- **Animasi yang Halus:** Pergerakan elemen yang diatur secara halus untuk pengalaman pengguna yang lebih baik.

## Instalasi

Untuk menginstal Isotope JS dalam proyek Anda, tambahkan tautan berikut ke dalam file HTML Anda:

```html
<!-- Sertakan Isotope JS -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.0.0/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery.isotope/3.0.6/isotope.pkgd.min.js"></script>
```

## Penggunaan

Berikut adalah contoh penggunaan dasar dari Isotope JS:

1. **Markup HTML**

   Pastikan Anda memiliki elemen kontainer yang membungkus elemen-elemen yang ingin difilter dan disortir:

   ```html
   <div class="grid">
      <div class="element-item category1">Item 1</div>
      <div class="element-item category2">Item 2</div>
      <div class="element-item category1">Item 3</div>
      <!-- Tambahkan lebih banyak item -->
   </div>
   ```

2. **Inisialisasi dengan JavaScript**

   Gunakan JavaScript untuk menginisialisasi Isotope pada kontainer yang Anda buat:

   ```js
   var iso = new Isotope('.grid', {
     // opsi
     itemSelector: '.element-item',
     layoutMode: 'fitRows'
   });
   ```

3. **Menyaring Item**

   Anda dapat membuat tombol untuk memfilter elemen sesuai dengan kategori:

   ```html
   <button data-filter="*">Tampilkan Semua</button>
   <button data-filter=".category1">Kategori 1</button>
   <button data-filter=".category2">Kategori 2</button>
   ```

   Tambahkan event listener untuk mengaktifkan filter saat tombol diklik:

   ```js
   var filterBtns = document.querySelectorAll('button[data-filter]');

   filterBtns.forEach(function (btn) {
     btn.addEventListener('click', function () {
       var filterValue = btn.getAttribute('data-filter');
       iso.arrange({ filter: filterValue });
     });
   });
   ```
