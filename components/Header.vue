<script>
export default {
  data() {
    return {
      isMenuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
  },
};
</script>

<template>
  <div class="body"> <!-- Elemen utama pembungkus halaman -->
    <nav class="navbar"> <!-- Elemen navigasi utama -->
      <div class="logo"> <!-- Bagian logo -->
        <img src="/assets/img/logopo.png" alt="Logo" /> <!-- Gambar logo -->
        <h5>SMKN 4 Tasikmalaya</h5> <!-- Nama sekolah -->
      </div>
      <button class="menu-toggle" @click="toggleMenu">
        <span></span>
        <span></span>
        <span></span>
      </button>
      <ul class="nav-links" :class="{ active: isMenuOpen }"> <!-- Daftar tautan navigasi -->
        <li><nuxt-link to="/">Beranda</nuxt-link></li> <!-- Tautan ke halaman beranda -->
        <li><nuxt-link to="/profile/">Tentang Kami</nuxt-link></li> <!-- Tautan ke halaman profil -->
        <li><nuxt-link to="/berita/">Berita</nuxt-link></li> <!-- Tautan ke halaman berita -->
        <li><nuxt-link to="/kegiatan/">Kegiatan</nuxt-link></li> <!-- Tautan ke halaman prestasi -->
        <li class="contact"><nuxt-link to="/kontak/"> <!-- Item khusus untuk kontak -->
          <button class="primary-btn">KONTAK KAMI</button></nuxt-link></li><!-- Tombol kontak kami -->
      </ul>
    </nav>
  </div>
</template>

<style scoped>
button {
  border: none; 
  /* Menghilangkan border tombol */
  background: none; 
  /* Menghilangkan latar belakang tombol */
  outline: none; 
  /* Menghilangkan outline tombol */
  transition: 0.5s; /* Efek transisi selama 0.5 detik */
  cursor: pointer; 
  /* Ubah kursor menjadi pointer */
}

.primary-btn {
  padding: 10px 20px; 
  /* Padding di dalam tombol */
  font-size: 1rem; 
  /* Ukuran teks tombol */
  line-height: 1; 
  /* Tinggi baris tombol */
  background: #6b5296; 
  /* Warna latar belakang biru tua */
  color: white; 
  /* Warna teks putih */
  border-radius: 5px; 
  /* Sudut tombol melengkung */
}

.contact {
  display: flex; 
  /* Elemen di dalamnya sejajar secara horizontal */
  align-items: center; 
  /* Posisi elemen sejajar secara vertikal */
  height: 100%; 
  /* Mengikuti tinggi navbar */
}

.primary-btn:hover {
  background-color: #483765; 
  /* Warna latar belakang saat hover */
}

/* Navbar */
.navbar {
  position: fixed; 
  /* Posisi tetap di atas layar */
  top: 0; 
  /* Jarak dari atas layar 0 */
  left: 0; 
  /* Jarak dari kiri layar 0 */
  z-index: 1000; 
  /* Urutan tumpukan elemen, berada di atas elemen lain */
  display: flex; 
  /* Elemen di dalam navbar sejajar secara horizontal */
  justify-content: space-between; 
  /* Elemen di dalam navbar tersebar rata */
  align-items: center; 
  /* Elemen sejajar secara vertikal */
  background-color: #9575CD; 
  /* Warna latar belakang biru */
  color: white; 
  /* Warna teks putih */
  width: 100%; 
  /* Lebar penuh layar */
  height: 70px; 
  /* Tinggi navbar */
  padding: 0; 
  /* Menghilangkan padding default */
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1); 
  /* Bayangan lembut di bawah navbar */
}

.nav-links a {
  color: white; /* Warna teks tautan putih */
  text-decoration: none; /* Menghilangkan garis bawah */
  font-size: 1rem; /* Ukuran teks tautan */
  transition: color 0.3s ease; /* Transisi warna teks saat hover */
}

/* Logo */
.logo {
  display: flex; 
  /* Elemen di dalam logo sejajar horizontal */
  align-items: center; 
  /* Elemen sejajar secara vertikal */
  gap: 1rem; 
  /* Jarak antar elemen */
  padding-left: 1rem; 
  /* Padding kiri */
}
.logo img {
  height: 50px; 
  /* Tinggi logo */
  width: 50px; 
  /* Lebar logo */
  object-fit: contain; 
  /* Sesuaikan ukuran gambar tanpa merusak rasio */
}
.logo h5 {
  margin: 0; 
  /* Menghilangkan margin default */
  font-size: 1.5rem; 
  /* Ukuran teks nama sekolah */
}

/* Tautan navigasi */
.nav-links {
  display: flex; 
  /* Elemen dalam daftar sejajar horizontal */
  list-style: none; 
  /* Menghilangkan gaya bullet default */
  gap: 1.5rem; 
  /* Jarak antar tautan */
  margin: 0; 
  /* Menghilangkan margin default */
  padding-right: 1rem; 
  /* Padding kanan */
}

.nav-links a:hover {
  color: #503f6c; /* Warna teks biru terang saat hover */
}

.nav-links li {
  display: flex; 
  /* Elemen dalam item daftar sejajar horizontal */
  align-items: center; 
  /* Elemen sejajar vertikal */
  height: 70px; 
  /* Sama dengan tinggi navbar */
}

/* Reset margin body */
.body {
  margin: 0; 
  /* Menghilangkan margin default body */
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

/* Menu Toggle Button */
.menu-toggle {
  display: none;
  flex-direction: column;
  gap: 0.4rem;
  cursor: pointer;
}

.menu-toggle span {
  width: 25px;
  height: 3px;
  background: white;
  transition: 0.3s;
}

/* Responsiveness */
@media (max-width: 768px) {
  .menu-toggle {
    display: flex;
  }

  .nav-links {
    display: none;
    flex-direction: column;
    gap: 0;
    position: absolute;
    top: 70px;
    right: 0;
    background-color: #9575CD;
    width: 100%;
    padding: 1rem;
  }

  .nav-links.active {
    display: flex;
  }

  .nav-links li {
    text-align: center;
    height: auto;
  }
}

</style>
