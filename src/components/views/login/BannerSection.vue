<template>
  <div class="banner">
    <div class="badges">
      <span class="badge">NOVO</span>
      <span class="badge">ONLINE</span>
    </div>
    
    <div class="banner-content">
      <h1 class="banner-title">
        O conhecimento que <span class="highlight">transforma sua carreira.</span>
      </h1>
      
      <p class="banner-description">
        Tenha acesso ilimitado a mais de 3.000 cursos práticos.<br>
        Aprenda com os melhores especialistas do mercado em<br>
        tecnologia, design e negócios.
      </p>
      
      <div class="stats">
        <div class="stat-item">
          <div class="stat-number">15k+</div>
          <div class="stat-label">Alunos Ativos</div>
        </div>
        
        <div class="stat-divider"></div>
        
        <div class="stat-item">
          <div class="stat-rating">
            <span class="rating-number">4.8</span>
            <div class="stars">
              <span v-for="i in 5" :key="i" class="star">★</span>
            </div>
          </div>
          <div class="stat-label">Avaliação Média</div>
        </div>
      </div>
    </div>
    
    <div class="banner-overlay"></div>
  </div>
</template>

<script setup>
</script>

<style scoped>
.banner {
  position: relative;
  background: linear-gradient(135deg, #0f4c75 0%, #1b6ca8 50%, #2d8f6f 100%);
  height: auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 3rem;
  overflow: hidden;
}

.banner::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: url('data:image/svg+xml,<svg width="100" height="100" xmlns="http://www.w3.org/2000/svg"><circle cx="50" cy="50" r="2" fill="rgba(255,255,255,0.1)"/></svg>');
  background-size: 50px 50px;
  opacity: 0.3;
}

.banner-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 40%;
  background: linear-gradient(to top, rgba(0, 0, 0, 0.3), transparent);
}

.badges {
  position: relative;
  z-index: 2;
  display: flex;
  gap: 0.75rem;
  margin-bottom: 4rem;
}

.badge {
  padding: 0.5rem 1rem;
  background-color: rgba(255, 255, 255, 0.15);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 20px;
  color: white;
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 0.5px;
}

.banner-content {
  position: relative;
  z-index: 2;
  max-width: 600px;
}

.banner-title {
  font-size: 3rem;
  font-weight: 900;
  color: white;
  line-height: 1.2;
  margin-bottom: 1.5rem;
}

.highlight {
  color: #4ade80;
  display: block;
}

.banner-description {
  font-size: 1.125rem;
  color: rgba(255, 255, 255, 0.9);
  line-height: 1.8;
  margin-bottom: 3rem;
}

.stats {
  display: flex;
  align-items: center;
  gap: 2rem;
  padding: 1.5rem 0;
}

.stat-item {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 900;
  color: white;
}

.stat-label {
  font-size: 0.875rem;
  color: rgba(255, 255, 255, 0.8);
  font-weight: 500;
}

.stat-divider {
  width: 1px;
  height: 60px;
  background-color: rgba(255, 255, 255, 0.2);
}

.stat-rating {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.rating-number {
  font-size: 2.5rem;
  font-weight: 900;
  color: white;
}

.stars {
  display: flex;
  gap: 0.125rem;
}

.star {
  color: #fbbf24;
  font-size: 0.875rem;
}

@media (max-width: 768px) {
  .banner {
    min-height: auto;
    padding: 2rem 1.5rem;
  }

  .banner-title {
    font-size: 2rem;
  }

  .banner-description {
    font-size: 1rem;
  }

  .stats {
    flex-direction: column;
    align-items: flex-start;
    gap: 1.5rem;
  }

  .stat-divider {
    display: none;
  }
}
</style>