<script setup>
useHead({
  title: "Beranda - Website Sekolah"
})

import { ref, onMounted } from "vue";

const isVisible = ref(false);

onMounted(() => {
  setTimeout(() => {
    isVisible.value = true;
  }, 200); // delay biar animasi lebih smooth
});
</script>

<template>
  <div class="hal-utama">
    <div class="row">
      <div class="col">
       <!-- Welcome Section -->
        <div
        class="welcome"
        :class="{ 'show': isVisible }"
      >
        <img
          src="/assets/img/utama1.png"
          alt="School Image"
          class="welcome-image"
        />
        <div class="welcome-text">
          <h5 class="title-text">SEKOLAH PUSAT KEUNGGULAN</h5>
          <h1>SMKN 4 TASIKMALAYA</h1>
        </div>
      </div>
      </div>
    </div>

    <div class="row">
      <div class="col">
        <!-- Info Section -->
        <div class="info-section">
          <div class="info-box">
            <i class="fa-solid fa-chalkboard-user"></i>
            <p>Guru</p>
            <h2>82</h2>
          </div>
          <div class="info-box">
            <i class="fa-solid fa-person"></i>
            <p>Siswa</p>
            <h2>1500</h2>
          </div>
          <div class="info-box">
            <i class="fa-solid fa-star"></i>
            <p>Administrasi</p>
            <h2>10</h2>
          </div>
          <div class="info-box">
            <i class="fa-solid fa-chart-line"></i>
            <p>Ekstrakurikuler</p>
            <h2>18</h2>
          </div>
        </div>
      </div>
    </div>

    <div class="sambutan">
      <!-- Kolom Foto -->
      <div class="photo-section">
        <img src="/assets/img/kepsek.png" alt="Kepala Sekolah" class="photo" />
      </div>

      <!-- Kolom Sambutan -->
      <div class="welcome-section">
        <h2 class="welcome-title text-center">Sambutan Kepala Sekolah</h2>
        <h3>Assalamualaikum Warahmatullahi Wabarakatuh</h3>
        <p class="welcome-paragraph">
        Selamat datang di SMKN 4 Tasikmalaya. Segala puji dan syukur kita panjatkan kehadirat Allah SWT, semoga kita semua ada dalam lindungan-Nya. 
        Dan atas perkenan-Nya pula kami dapat menghadirkan website SMK Negeri 4 Tasikmalaya ini.
        Kami berharap dengan adanya website di SMK Negeri 4 Tasikmalaya ini para pengunjung dapat mengenal lebih jauh tentang sekolah kami
        sehingga dapat mempererat tali silaturrahmi antara sekolah dengan masyarakat demi kemajuan kita bersama.
        Tiada gading yang tak retak, website kami ini masih dalam proses pengembangan, masih banyak kekurangan yang harus kami perbaiki.
        Kritik dan sarannya yang membangun sangat kami harapkan untuk pengembangan ke depan.
        </p>
        <p class="welcome-paragraph">
        Akhirnya, saya mengucapkan terimakasih yang sebesar-besarnya kepada semua pihak yang tidak dapat disebutkan satu segala bantuan dan persatu atas fasilitasnya yang telah diberikan semoga semua yang kita lakukan bermanfaat bagi masyarakat. 
        Wassalamu'alaikum Warahmatullahi Wabarakatuh.
        </p>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <div class="kompetensi-section">
        <!-- Teks Tengah dengan Background -->
          <div class="kompetensi-header">
            <h1>Konsentrasi Keahlian</h1>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col">
          <!-- Cards Section -->
          <div class="cards-section">
            <!-- Card 1 -->
            <div class="card">
              <div class="card-image">
                <img src="/assets/img/10.png" alt="Teknik Informatika" />
              </div>
              <div class="card-text">
                <h2>Rekayasa Perangkat Lunak</h2>
                <p>Konsentrasi keahlian ini mempelajari cara merancang, mengembangkan, dan memelihara perangkat lunak, termasuk aplikasi berbasis desktop, web, dan mobile. Siswa juga diajarkan teknik pembuatan gim, seperti desain level, animasi, dan pemrograman gim, menggunakan teknologi dan perangkat lunak terkini.</p>
              </div>
            </div>
            <!-- Card 2 -->
            <div class="card">
              <div class="card-image">
                <img src="/assets/img/8.png" alt="Teknik Otomotif" />
              </div>
              <div class="card-text">
                <h2>Teknik Komputer & Jaringan Komputer</h2>
                <p>Konsentrasi keahlian ini fokus pada penguasaan konsep dan praktik dalam membangun, mengelola, dan mengamankan jaringan komputer. Siswa akan mempelajari teknologi jaringan, administrasi server, troubleshooting, serta konfigurasi perangkat jaringan seperti router dan switch.</p>
              </div>
            </div>
            <!-- Card 3 -->
            <div class="card">
              <div class="card-image">
                <img src="/assets/img/9.png" alt="Teknik Elektronika" />
              </div>
              <div class="card-text">
                <h2>Teknik & Bisnis Sepeda Motor</h2>
                <p>Konsentrasi keahlian ini mempelajari teknik perawatan, perbaikan, dan modifikasi sepeda motor, sekaligus menanamkan keterampilan kewirausahaan. Siswa diajarkan cara membuka dan mengelola bisnis bengkel, termasuk aspek pemasaran dan manajemen.</p>
              </div>
            </div>
            <!-- Card 4 -->
            <div class="card">
              <div class="card-image">
                <img src="/assets/img/7.png" alt="Teknik Otomotif" />
              </div>
              <div class="card-text">
                <h2>Desain Komunikasi Visual</h2>
                <p>Konsentrasi keahlian ini mengajarkan seni dan teknik dalam menciptakan desain visual yang komunikatif dan menarik. Materi meliputi desain grafis, fotografi, ilustrasi, dan media digital untuk kebutuhan branding, promosi, atau media publikasi.</p>
              </div>
            </div>
            <!-- Card 5 -->
            <div class="card">
              <div class="card-image">
                <img src="/assets/img/6.png" alt="Teknik Otomotif" />
              </div>
              <div class="card-text">
                <h2>Teknik Otomasi Industri</h2>
                <p>Konsentrasi keahlian ini berfokus pada teknologi otomotif yang diterapkan dalam skala industri. Siswa akan belajar tentang sistem mekanik kendaraan modern, produksi komponen otomotif, dan pengelolaan peralatan industri yang berkaitan dengan otomotif.</p>
              </div>
            </div>
            <!-- tutup -->
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<style scoped>
h1 {
  line-height: 3.7rem !important;
}

.hal-utama {
  margin-top: 60px;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande',
    'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

/* Welcome Section */
.welcome {
  opacity: 0;
  transform: translateY(30px);
  transition: all 1s ease;
  text-align: center;
}
.welcome.show {
  opacity: 1;
  transform: translateY(0);
}
.welcome-image {
  width: 100%;
  height: 500px;
  object-fit: cover;
  border-radius: 12px;
}
.welcome-text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: white;
  font-size: 2rem;
  text-align: center;
  padding: 1rem;
}
.title-text {
  font-size: 18px;
  font-weight: bold;
  color: #9575CD;
  letter-spacing: 1px;
}

/* Info Section */
.info-section {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  padding: 2rem;
  background-color: #f0f0f0;
}
.info-box {
  text-align: center;
  flex: 1 1 150px;
  margin: 1rem;
}

/* Sambutan */
.sambutan {
  display: flex;
  align-items: flex-start;
  gap: 2rem;
  padding: 2rem;
  flex-wrap: wrap;
}
.photo-section {
  flex: 1;
  display: flex;
  justify-content: center;
}
.photo {
  width: 100%;
  max-width: 400px;
  border-radius: 8px;
  object-fit: cover;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}
.welcome-section {
  flex: 2;
}
.welcome-title {
  font-size: 2rem;
  color: #9575CD;
  margin-bottom: 1rem;
}
.welcome-paragraph {
  font-size: 1rem;
  line-height: 1.6;
  color: #333;
}

/* Kompetensi */
.kompetensi-header {
  background-color: #9575CD;
  color: white;
  text-align: center;
  padding: 2rem 0;
  margin-bottom: 2rem;
}
.kompetensi-header h1 {
  margin: 0;
  font-size: 2.5rem;
  font-weight: bold;
}

/* Cards */
.cards-section {
  display: flex;
  flex-wrap: wrap;
  gap: 1.5rem;
  justify-content: center;
  padding: 0 1rem 2rem;
}
.card {
  display: flex;
  flex-direction: row;
  background-color: #f9f9f9;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  max-width: 700px;
  width: 100%;
}
.card-image img {
  width: 150px;
  height: auto;
  object-fit: cover;
}
.card-text {
  padding: 1rem;
}
.card-text h2 {
  margin: 0 0 0.5rem;
  color: #9575CD;
  font-size: 1.5rem;
}
.card-text p {
  margin: 0;
  color: #555;
  line-height: 1.5;
}

/* ================== Responsive ================== */
@media (max-width: 992px) {
  .sambutan {
    flex-direction: column;
    text-align: center;
  }
  .welcome-text {
    font-size: 1.5rem;
  }
  .card {
    flex-direction: column;
    text-align: center;
  }
  .card-image img {
    width: 100%;
    max-height: 200px;
  }
}

@media (max-width: 576px) {
  .welcome-image {
    height: 300px;
  }
  .welcome-text {
    font-size: 1.2rem;
    padding: 0.5rem;
  }
  .kompetensi-header h1 {
    font-size: 1.8rem;
  }
  .card-text h2 {
    font-size: 1.2rem;
  }
  .info-section {
    flex-direction: column;
    align-items: center;
  }
}
</style>
