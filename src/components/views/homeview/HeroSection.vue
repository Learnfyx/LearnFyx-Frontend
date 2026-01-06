<template>
  <section class="hero">
    <div class="container">
      <div class="hero-grid">
        <div class="hero-content">
          <h1 class="hero-title">
            Domine novas <div class="text-primary">habilidades</div> hoje
          </h1>
          <p class="hero-description">
            Junte-se a milhares de alunos e aprenda com os melhores especialistas do mercado. 
            Acesso vitalício e certificados reconhecidos em todo o Brasil.
          </p>
          <div class="hero-buttons">
            <button class="btn-hero-primary" @click="$emit('start-now')">
              Começar Agora
            </button>
            <button class="btn-hero-secondary" @click="$emit('view-courses')">
              <Play class="play-icon" />
              Ver Cursos
            </button>
          </div>
          <div class="hero-stats">
            <div class="stat-item">
              <Check class="check-icon" />
              <span>+10k Alunos</span>
            </div>
            <div class="stat-item">
              <Check class="check-icon" />
              <span>Certificado Incluso</span>
            </div>
          </div>
        </div>
        <div class="hero-image">
          <div class="image-glow"></div>
          <div class="image-wrapper">
            <img 
              src="https://lh3.googleusercontent.com/aida-public/AB6AXuCgtmp6Sg-xQHx2i9z8pldhun8J9kg9OfBqmZOpQjN9OZe6ircAVX-Ta_UmzD9A2MrbR3KQNhgh-ao8aMnQLiGJV17jw6-Dnyi_9HeVs6gkVFCz-xdvYFUVeiUyYpjvQeIZ1b3w4gcmYShgygYEKdGlyaSwpyZkQOIw0aG_s5fNlt5XWMp7xQmYAzhfypfmr72DsOiUfycuJSsU0MYCp8Ft2qCKuYAaH9mx4AWE2nAv3lWo8Z1Ysqin0c6EKsmGsTxvS_UwdNvKTD9U"
              alt="Estudante sorrindo"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import Play from 'vue-material-design-icons/Play.vue'
import Check from 'vue-material-design-icons/Check.vue'

defineEmits(['start-now', 'view-courses'])
</script>

<style scoped>
.hero {
  padding: 4rem 0;
  overflow: hidden;
  width: 70%;
  margin: auto;
  
}

span{
    display: flex;
    align-items: center;
    justify-content: center;
}

.hero-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: center;
}

.hero-content {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 900;
  line-height: 1.1;
  color: #0f172a;
}

.text-primary {
  color: #0d7ff2;
}

.hero-description {
  font-size: 1.125rem;
  color: #64748b;
  line-height: 1.6;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.btn-hero-primary {
  padding: 0.75rem 2rem;
  background-color: #0d7ff2;
  color: white;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  font-weight: 700;
  cursor: pointer;
  transition: all 0.3s;
  box-shadow: 0 4px 16px rgba(13, 127, 242, 0.3);
}

.btn-hero-primary:hover {
  background-color: #0c6cd9;
  transform: translateY(-2px);
}

.btn-hero-secondary {
  padding: 0.75rem 2rem;
  background-color: white;
  color: #334155;
  border: 1px solid #e2e8f0;
  border-radius: 8px;
  font-size: 1rem;
  font-weight: 700;
  cursor: pointer;
  transition: all 0.3s;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.btn-hero-secondary:hover {
  background-color: #f8fafc;
  border-color: #cbd5e1;
}

.play-icon {
  color: #10b981;
  width: 16px;
  height: 16px;
}

.hero-stats {
  display: flex;
  gap: 1.5rem;
  color: #64748b;
  font-size: 0.875rem;
  font-weight: 500;
}

.stat-item {
  display: flex;
  align-items: center;
  gap: 0.25rem;
}

.check-icon {
  color: #10b981;
  width: 16px;
  height: 16px;
}

.hero-image {
  position: relative;
}

.image-glow {
  position: absolute;
  inset: -1rem;
  border-radius: 1rem;
  filter: blur(40px);
  opacity: 0.7;
}

.image-wrapper {
  position: relative;
  border-radius: 1rem;
  overflow: hidden;
}

.image-wrapper img {
  width: 100%;
  height: 500px;
  display: block;
}

@media (max-width: 1024px) {
  .hero-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .hero-title {
    font-size: 2.5rem;
  }
}

@media (max-width: 768px) {
  .hero-title {
    font-size: 2rem;
  }
  
  .hero-buttons {
    flex-direction: column;
  }
  
  .btn-hero-primary,
  .btn-hero-secondary {
    width: 100%;
    justify-content: center;
  }
}
</style>