<template>
  <div class="about-container">
    <h2>Tentang Saya</h2>
    <p>Hai! Saya adalah seseorang yang sangat menyukai alam dan petualangan. Saat tidak sibuk, 
      saya suka menjelajahi hutan, mendaki gunung, atau hanya menikmati keindahan alam. 
      Aplikasi Todo ini saya buat sebagai alat bantu untuk mengatur tugas-tugas saya sehari-hari 
      agar bisa lebih banyak waktu untuk menikmati alam.</p>
    <p>Jelajahi aplikasi ini dan semoga membantu Anda mengatur aktivitas sehari-hari dengan lebih efisien, 
      sehingga Anda juga bisa punya lebih banyak waktu untuk menikmati hal-hal yang Anda sukai.</p>

    <div class="social-media-icons">
      <a href="https://twitter.com/yourusername" target="_blank" class="social-icon" aria-label="Twitter">
        <svg viewBox="0 0 24 24" width="30" height="30">
          <path d="M24 4.557a9.83 9.83 0 01-2.828.775 4.932 4.932 0 002.165-2.724 9.864 9.864 0 01-3.127 1.195 4.916 4.916 0 00-8.384 4.482A13.94 13.94 0 011.671 3.149 4.917 4.917 0 003.195 9.723a4.902 4.902 0 01-2.228-.616v.061a4.917 4.917 0 003.946 4.827 4.936 4.936 0 01-2.224.085 4.923 4.923 0 004.598 3.417A9.867 9.867 0 010 21.543a13.933 13.933 0 007.548 2.212c9.057 0 14.01-7.514 14.01-14.01 0-.213-.005-.425-.014-.636A10.012 10.012 0 0024 4.557z"/>
        </svg>
      </a>&nbsp;
      <a href="https://linkedin.com/in/yourusername" target="_blank" class="social-icon" aria-label="LinkedIn">
        <svg viewBox="0 0 24 24" width="30" height="30">
          <path d="M22.23 0H1.77C.79 0 0 .774 0 1.725v20.549C0 23.226.79 24 1.77 24h20.46C23.21 24 24 23.226 24 22.274V1.725C24 .774 23.21 0 22.23 0zM7.08 20.452H3.56V9.031h3.52v11.421zM5.32 7.573c-1.127 0-2.046-.919-2.046-2.045 0-1.127.919-2.046 2.046-2.046s2.045.919 2.045 2.046c0 1.126-.918 2.045-2.045 2.045zM20.45 20.452h-3.52v-5.978c0-1.427-.03-3.265-1.99-3.265-1.99 0-2.297 1.555-2.297 3.16v6.084H9.12V9.031h3.38v1.556h.048c.471-.89 1.625-1.827 3.346-1.827 3.58 0 4.24 2.357 4.24 5.428v6.264h-.004z"/>
        </svg>
      </a>&nbsp;
      <a href="https://github.com/yourusername" target="_blank" class="social-icon" aria-label="GitHub">
        <svg viewBox="0 0 24 24" width="30" height="30">
          <path d="M12 .296C5.373.296 0 5.67 0 12.29c0 5.302 3.438 9.8 8.207 11.388.6.11.82-.261.82-.58 0-.287-.01-1.046-.015-2.054-3.337.728-4.042-1.613-4.042-1.613-.546-1.387-1.334-1.758-1.334-1.758-1.09-.745.084-.73.084-.73 1.204.084 1.838 1.238 1.838 1.238 1.07 1.833 2.809 1.303 3.495.997.108-.775.418-1.304.762-1.604-2.665-.305-5.467-1.333-5.467-5.93 0-1.31.465-2.382 1.236-3.222-.124-.304-.536-1.527.117-3.183 0 0 1.008-.322 3.301 1.23.957-.266 1.98-.399 3.002-.404 1.02.005 2.045.138 3.002.404 2.292-1.552 3.297-1.23 3.297-1.23.654 1.656.243 2.879.119 3.183.772.84 1.235 1.912 1.235 3.222 0 4.61-2.806 5.62-5.478 5.918.43.37.815 1.102.815 2.22 0 1.606-.015 2.897-.015 3.293 0 .321.216.694.825.577C20.565 22.085 24 17.589 24 12.29 24 5.67 18.627.296 12 .296z"/>
        </svg>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'About'
};
</script>

<style scoped>
.about-container {
  padding: 20px;
  background-color: rgba(255, 255, 255, 0);
  border: 1px solid #ccc;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  max-width: 600px;
  margin: 20px auto;
  text-align: center;
}

h2 {
  font-size: 24px;
  margin-bottom: 10px;
  color: black;
}

p {
  font-size: 16px;
  line-height: 1.5;
  color: black;
  margin-bottom: 20px;
}

.social-media-icons {
  display: flex;
  justify-content: center;
  gap: 15px;
  margin-top: 20px;
}

.social-icon svg {
  width: 24px;
  height: 24px;
  fill: black;
  transition: fill 0.3s ease;
}

.social-icon:hover svg {
  fill: #007bff;
}
</style>
