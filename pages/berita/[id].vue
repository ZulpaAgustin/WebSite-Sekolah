<script setup>
import { ref, onMounted } from 'vue'
import { useRoute } from 'vue-router'
import { useHead } from '#imports'

const supabase = useSupabaseClient();

const route = useRoute()
const beritaId = route.params.id

// State
const berita = ref(null)
const beritaLain = ref([])

onMounted(async () => {
  // Ambil berita sesuai id
  const { data: current, error } = await supabase
    .from('berita')
    .select('*')
    .eq('id', beritaId)
    .single()

  if (!error) {
    berita.value = current
    useHead({
      title: `${current.judul} - Website Sekolah`
    })
  }

  // Ambil berita lain (kecuali yang dibuka)
  const { data: others } = await supabase
    .from('berita')
    .select('id, judul, gambar')
    .neq('id', beritaId)
    .limit(3)

  beritaLain.value = others || []
})
</script>

<template>
  <div class="utama" v-if="berita">
    <div class="row">
      <!-- Konten Utama Berita -->
      <div class="col-lg-8">
        <div class="main-news">
          <img
            :src="berita.gambar"
            :alt="berita.judul"
            class="main-news-image"
          />
          <p class="text-muted">
            Di Posting Tanggal {{ new Date(berita.tanggal).toLocaleDateString() }}
          </p>
          <h2 class="main-news-title">{{ berita.judul }}</h2>
          <p class="main-news-content">{{ berita.isi }}</p>
        </div>
      </div>

      <!-- Berita Lainnya -->
      <div class="col-lg-4">
        <div class="other-news">
          <h3 class="other-news-title">Berita Lainnya</h3>
          <div
            v-for="item in beritaLain"
            :key="item.id"
            class="other-news-item"
          >
            <img
              :src="item.gambar"
              :alt="item.judul"
              class="other-news-image"
            />
            <div>
              <h5 class="other-news-heading">{{ item.judul }}</h5>
              <NuxtLink :to="`/berita/${item.id}`" class="other-news-link">
                Baca Selengkapnya
              </NuxtLink>
            </div>
          </div>
        </div>

        <!-- Carousel (opsional, bisa diisi dari Supabase juga kalau mau) -->
        <br />
        <div class="other-news">
          <div
            id="carouselExampleControls"
            class="carousel slide"
            data-bs-ride="carousel"
          >
            <div class="carousel-inner">
              <div class="carousel-item active">
                <img src="/assets/img/c.jpg" class="d-block w-100" alt="..." />
              </div>
              <div class="carousel-item">
                <img src="/assets/img/z.jpg" class="d-block w-100" alt="..." />
              </div>
              <div class="carousel-item">
                <img src="/assets/img/i.jpg" class="d-block w-100" alt="..." />
              </div>
            </div>
            <button
              class="carousel-control-prev"
              type="button"
              data-bs-target="#carouselExampleControls"
              data-bs-slide="prev"
            >
              <span
                class="carousel-control-prev-icon"
                aria-hidden="true"
              ></span>
              <span class="visually-hidden">Previous</span>
            </button>
            <button
              class="carousel-control-next"
              type="button"
              data-bs-target="#carouselExampleControls"
              data-bs-slide="next"
            >
              <span
                class="carousel-control-next-icon"
                aria-hidden="true"
              ></span>
              <span class="visually-hidden">Next</span>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.utama {
  margin-top: 90px;
}

/* Konten Utama Berita */
.main-news {
  padding: 20px;
}
.main-news-image {
  width: 100%;
  height: auto;
  border-radius: 8px;
  margin-bottom: 15px;
}
.main-news-title {
  font-size: 2rem;
  color: #004080;
  margin-bottom: 10px;
}
.main-news-content {
  font-size: 1.1rem;
  color: #333;
  line-height: 1.6;
}

/* Berita Lainnya */
.other-news {
  padding: 20px;
  background-color: #f9f9f9;
  border-radius: 8px;
}
.other-news-title {
  font-size: 1.5rem;
  color: #004080;
  margin-bottom: 20px;
}
.other-news-item {
  display: flex;
  align-items: flex-start;
  margin-bottom: 15px;
}
.other-news-item > div {
  display: flex;
  flex-direction: column;
}
.other-news-image {
  width: 80px;
  height: 80px;
  object-fit: cover;
  border-radius: 8px;
  margin-right: 10px;
}
.other-news-heading {
  font-size: 1rem;
  color: #333;
  margin: 0 0 5px 0;
}
.other-news-link {
  display: block;
  font-size: 0.9rem;
  color: #004080;
  text-decoration: none;
  margin-top: 5px;
}
.other-news-link:hover {
  text-decoration: underline;
}
</style>
