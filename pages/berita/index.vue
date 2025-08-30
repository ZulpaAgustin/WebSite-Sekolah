<script setup>
import { ref, onMounted } from 'vue'
import { useHead } from '#imports'

useHead({
  title: "Berita Utama - Website Sekolah"
})

const supabase = useSupabaseClient();

const berita = ref([])

onMounted(async () => {
  const { data, error } = await supabase
    .from('berita')
    .select('*')
    .order('tanggal', { ascending: false })

  if (error) {
    console.error(error)
  } else {
    berita.value = data
  }
})
</script>

<template>
  <div class="utama news-page">
    <h2 class="page-title text-center mb-4">Berita Sekolah</h2>
    <div class="row">
      <div v-for="item in berita" :key="item.id" class="col-md-4">
        <div class="card" style="width: 100%;">
          <img :src="item.gambar" class="card-img-top news-img" :alt="item.judul">
          <div class="card-body">
            <h5 class="card-title">{{ item.judul }}</h5>
            <p class="card-text">
              {{ item.isi.substring(0, 100) }}...
            </p>
            <NuxtLink :to="`/berita/${item.id}`">
              <button class="btn btn-ungu">Baca Selengkapnya</button>
            </NuxtLink>
          </div>
          <div class="card-footer text-muted">
            {{ new Date(item.tanggal).toLocaleDateString() }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.utama {
  margin-top: 90px;
  margin-bottom: 20px;
}

.card-title {
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande',
    'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

.page-title {
  font-size: 2.5rem;
  color: #9575CD;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande',
    'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

.news-img {
  height: 200px;
  object-fit: cover;
}

.card {
  margin-bottom: 20px;
}

button {
  border: none;
  background: none;
  outline: none;
  transition: 0.5s;
  cursor: pointer;
}

.btn-ungu {
  padding: 10px 20px;
  font-size: 1rem;
  line-height: 1;
  background: #6b5296;
  color: white;
  border-radius: 5px;
}

.btn-ungu:hover {
  background-color: #483765;
}
</style>
