<script setup>
useHead({
  title: "Profil - Website Sekolah"
})
</script>

<template>
  <div class="container-fluid">
    <div class="profile-page">
    <!-- Judul Halaman -->
      <div class="page-title">
        <h2 class="judul">Profil SMK Negeri 4 Tasikmalaya</h2>
      </div>
      <div class="row">
        <div class="col">
       <!-- Welcome Section -->
          <div class="welcome-section">
            <img src="/assets/img/brsma.jpg" alt="School Image" class="welcome-image" />
          </div>
        </div>
      </div>

    <!-- Sejarah Sekolah -->
    <section class="section" id="sejarah">
      <h2 class="section-title">Sejarah Sekolah</h2>
      <p class="section-content">
        Sejalan dengan Program Pemerintah dibidang pendidikan Menengah Kejuruan pada saat itu yakni pemerataan akses ditambah pula dengan banyaknya keinginan masyarakat yang mengharapkan adanya SMK Negeri di daerah Kecamatan Purbaratu Kota  Tasikmalaya, 
        terutama untuk menampung tamatan dari SLTP yang ingin melanjutkan ke SMK maka beberapa tokoh masyarakat, unsur pejabat pemerintah di Kecamatan Purbaratu Kota Tasikmalaya mengusulkan kepada pemerintah Kota Tasikmalaya dan Pemerintah Provinsi Jawa Barat, agar berdirinya SMK Negeri di Kecamatan Purbaratu Kota Tasikmalaya.
        Setelah melalui perjuangan yang sangat panjang dari berbagai pihak khususnya Disdik Kota Tasikmalaya dan pihak-pihak terkait lainnya sesuai prosedur dan ketentuan yang berlaku pada waktu itu dengan mengucapkan syukur Alhamdulillah akhirnya pada tahun pelajaran 2010/2011 SMK Negeri 4 Tasikmalaya mulai berdiri, pada awalnya membuka Kompetensi Keahlian Teknik Komputer dan Jaringan dengan pendaftar peserta Didik Baru pada waktu itu berjumlah 44 orang. Pada awalnya tempat belajar menumpang di SMP Negeri 17 Kota Tasikmalaya, dan sekolah induknya adalah SMK Negeri 2 Kota Tasikmalaya, Untuk Tenaga pendidik dan Tenaga Kependidikan masih dibantu sepenuhnya oleh kedua sekolah tersebut.
        Pada tahun 2012 keluarlah surat Izin Pendirian berdasarkan keputusan kepala Badan Pelayanan Perizinan Terpadu Kota Tasikmalaya No. 420/9/SK-BPPT/2012 Tanggal 06 Februari 2012.
      </p>
    </section>

    <!-- Visi dan Misi -->
    <section class="section" id="visi-misi">
      <h2 class="section-title">Visi dan Misi</h2>
      <div class="visi-misi">
        <div class="visi">
          <h3>Visi</h3>
          <h4>
            "TERWUJUDNYA LULUSAN YANG CERDAS, AKTIF, KOMPETITIF, ADAPTIF DAN PRODUKTIF, BERLANDASKAN IMAN DAN TAKWA" <br>
            "(CAKAP BERIMTAK)"
          </h4>
        </div>
        <div class="misi">
          <h3>Misi</h3>
          <ul>
            <li>Menyiapkan Sumber Daya Manusia yang cerdas dan kompeten baik hardskill maupun softskill.</li>
            <li>Meningkatkan dan mengembangkan aktifitas serta kreatifitas seluruh warga sekolah dalam berbagai kegiatan positif.</li>
            <li>Mewujudkan manajemen pengelolaan yang efektif, efesien, transparan, akuntabel dan layanan prima.</li>
            <li>Menumbuhkan dan mengembangkan potensi dan kemampuan Sumber Daya Manusia yang berdaya saing tinggi melalui berbagai kegiatan akademik maupun non akademik.</li>
            <li>Menyelenggarakan berbagai program kegiatan dalam upaya meningkatkan Sumber Daya Manusia yang mampu menyesuaikan dengan perkembangan.</li>
            <li>Mengembangkan sarana prasarana dan lingkungan sekolah yang menyenangkan sebagai wadah menumbuhkembangkan daya kreasi dan inovasi untuk menghasilkan produk teknologi tepat guna.</li>
            <li>Membangun jiwa wirausaha yang handal melalui pembelajaran Teaching Factory (TEFA) dan Kelas Industri.</li>
            <li>Menjalin dan mengembangkan kemitraan dengan Industri dan Dunia Kerja (IDUKA) serta lembaga lainnya yang relevan.</li>
            <li>Menanamkan dan membudayakan sikap dan perilaku yang baik pada aktivitas di sekolah maupun dalam kehidupan sehari-hari.</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- Identitas Sekolah -->
    <section class="section" id="identitas">
      <h2 class="section-title">Identitas Sekolah</h2>
      <div class="identitas-content">
        <div class="identitas-item">
          <h3>Nama Sekolah</h3>
          <p>SMK Negeri 4 Tasikmalaya</p>
        </div>
        <div class="identitas-item">
          <h3>NPSN</h3>
          <p>20276063</p>
        </div>
        <div class="identitas-item">
          <h3>Nomor Statistik Sekolah</h3>
          <p>401327810004</p>
        </div>
        <div class="identitas-item">
          <h3>Alamat</h3>
          <p>Jalan Depok RT 02 RW 05</p>
        </div>
      </div>
    </section>
  </div>
</div>
</template>

<style scoped>
.container-fluid {
  margin-top: 60px;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

.welcome-section {
  position: relative;
  text-align: center;
}
.welcome-image {
  width: 100%;
  height: 500px;
  object-fit: cover; 
}

.profile-page {
  margin-top: 90px;
}

.judul {
  font-size: 2.5rem;
  color: #9575CD;
}

.page-title {
  text-align: center;
  margin-bottom: 2rem;
}

.page-title h1 {
  font-size: 2.5rem;
  color: #9575CD;
}

.section {
  margin: 2rem 0;
  padding: 1rem;
  background-color: #f9f9f9;
  border-radius: 8px;
}

.section-title {
  font-size: 2rem;
  color: #9575CD;
  margin-bottom: 1rem;
  text-align: center;
}

.section-content {
  font-size: 1rem;
  color: #333;
  line-height: 1.6;
}

.visi-misi {
  display: flex;
  gap: 2rem;
  justify-content: space-between;
}

.visi,
.misi {
  flex: 1;
}

.misi ul {
  padding-left: 20px;
}

.identitas-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

.identitas-item {
  background-color: #fff;
  padding: 1rem;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.identitas-item h3 {
  color: #9575CD;
  font-size: 1.1rem;
}
</style>
