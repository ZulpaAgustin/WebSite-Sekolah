<template>
  <div class="footer">
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 100"><path fill="#9575CD" fill-opacity="1" d="M0,128L1440,0L1440,320L0,320Z"></path></svg>
    <div class="footer-text">
      <p>Copyright <i class="fa-regular fa-copyright"></i> SMKN 4 Tasikmalaya 2025 - {{ year }}</p>
      <div>Made with ❤️ by Zulpa</div>
    </div>
  </div>
</template>

<script setup>
let year = new Date().getFullYear()
</script>

<style scoped>
.footer-text {
  background-color: #9575CD;
}
.footer {
  /*background-color: #2d2d2d;  Warna abu-abu */
  color: white; /* Warna teks putih */
  text-align: center; /* Teks di tengah */
  padding: 0.5rem 0; /* Padding lebih kecil */
  position: relative; /* Footer berada setelah konten */
  width: 100%; /* Memastikan footer selebar layar */
  font-size: 0.9rem; /* Ukuran font lebih kecil */
  margin-top: 20px; /* Jarak dengan konten atas */
}
</style>