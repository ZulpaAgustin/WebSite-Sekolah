<script setup>
import { ref, onMounted } from 'vue'
import { useHead } from '#imports'

const supabase = useSupabaseClient()
const kegiatan = ref([])

useHead({
  title: "Kegiatan Sekolah"
})

onMounted(async () => {
  const { data, error } = await supabase
    .from('kegiatan')
    .select('*')
    .order('tanggal', { ascending: false })

  if (error) {
    console.error(error)
  } else {
    kegiatan.value = data
  }
})
</script>

<template>
  <div class="awal">
    <div class="container my-5">
      <h2 class="title text-center mb-4">Kegiatan Sekolah</h2>

      <div class="row">
        <div class="col-md-4 mb-4" v-for="item in kegiatan" :key="item.id">
          <div class="card h-100 shadow-sm">
            <img :src="item.gambar" class="card-img-top" alt="Kegiatan" />
            <div class="card-body">
              <h5 class="card-title">{{ item.judul }}</h5>
              <p class="card-text">{{ item.deskripsi }}</p>
            </div>
            <div class="card-footer text-muted">
              <small>
                <i class="bi bi-calendar-event"></i>
                {{ new Date(item.tanggal).toLocaleDateString() }}
              </small>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.card-title {
  font-weight: 600;
}

.awal {
  margin-top: 90px;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande',
    'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

.title {
  color: #9575CD;
}
</style>
