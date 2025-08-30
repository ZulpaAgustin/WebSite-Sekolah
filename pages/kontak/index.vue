<script setup>
import { ref } from "vue";
import { useHead } from "#imports"; 

useHead({
  title: "Kontak - Website Sekolah"
});

const supabase = useSupabaseClient();

// form state
const name = ref("");
const email = ref("");
const message = ref("");
const loading = ref(false);
const success = ref("");
const error = ref("");

// function submit form
const handleSubmit = async (e) => {
  e.preventDefault();
  loading.value = true;
  success.value = "";
  error.value = "";

  // simple validation
  if (!name.value || !email.value || !message.value) {
    error.value = "Semua field wajib diisi!";
    loading.value = false;
    return;
  }

  // insert ke Supabase
  const { data, error: insertError } = await supabase
    .from("kontak")
    .insert([{ nama: name.value, email: email.value, pesan: message.value }]);

  if (insertError) {
    error.value = "Gagal mengirim pesan: " + insertError.message;
  } else {
    success.value = "Pesan berhasil dikirim!";
    name.value = "";
    email.value = "";
    message.value = "";
  }
  loading.value = false;
};
</script>

<template>
  <div class="utama">
    <div class="contact-container">
      <!-- Bagian kiri: Formulir Kontak -->
      <div class="form-section">
        <h2>Kontak Kami</h2>
        <form @submit="handleSubmit">
          <div class="form-group">
            <label for="name">Nama</label>
            <input
              type="text"
              id="name"
              v-model="name"
              placeholder="Masukkan nama Anda"
            />
          </div>
          <div class="form-group">
            <label for="email">Email</label>
            <input
              type="email"
              id="email"
              v-model="email"
              placeholder="Masukkan email Anda"
            />
          </div>
          <div class="form-group">
            <label for="message">Pesan</label>
            <textarea
              id="message"
              v-model="message"
              rows="5"
              placeholder="Tulis pesan Anda di sini"
            ></textarea>
          </div>
          <button type="submit" class="primary-btn" :disabled="loading">
            {{ loading ? "Mengirim..." : "Kirim Pesan" }}
          </button>
        </form>

        <!-- feedback -->
        <p v-if="success" style="color: green; margin-top: 1rem;">{{ success }}</p>
        <p v-if="error" style="color: red; margin-top: 1rem;">{{ error }}</p>
      </div>

      <!-- Bagian kanan: Gambar -->
      <div class="image-section">
        <img src="/assets/img/main.jpg" alt="Kontak Kami" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.utama {
  margin-top: 90px;
}

.contact-container {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  padding: 2rem;
  background-color: #f8f9fa;
}

.form-section {
  flex: 1;
  max-width: 500px;
  padding: 1rem;
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.form-section h2 {
  margin-bottom: 1rem;
  color: #9575cd;
  font-size: 1.8rem;
  text-align: center;
}

.form-group {
  margin-bottom: 1rem;
}

.form-group label {
  display: block;
  font-weight: bold;
  margin-bottom: 0.5rem;
  color: #333;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 0.8rem;
  border: 1px solid #ddd;
  border-radius: 5px;
  font-size: 1rem;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #9575cd;
}

.primary-btn {
  display: block;
  width: 100%;
  padding: 0.8rem;
  background-color: #9575cd;
  color: #fff;
  border: none;
  border-radius: 5px;
  font-size: 1.2rem;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.primary-btn:hover {
  background-color: #644e8b;
}

.image-section {
  flex: 1;
  max-width: 500px;
  text-align: center;
  padding: 1rem;
}

.image-section img {
  max-width: 100%;
  height: auto;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}
</style>
