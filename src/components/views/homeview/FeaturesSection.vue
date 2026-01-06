<template>
  <section class="features">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">{{ title }}</h2>
        <p class="section-description">{{ description }}</p>
      </div>
      <div class="features-grid">
        <div 
          v-for="feature in features" 
          :key="feature.id" 
          class="feature-card"
        >
          <div class="feature-icon" :style="{ backgroundColor: feature.color }">
            <component :is="feature.icon" class="feature-icon-svg" />
          </div>
          <div class="feature-content">
            <h3 class="feature-title">{{ feature.title }}</h3>
            <p class="feature-text">{{ feature.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import School from 'vue-material-design-icons/School.vue'
import CheckCircle from 'vue-material-design-icons/CheckCircle.vue'

// eslint-disable-next-line no-unused-vars
const props = defineProps({
  title: {
    type: String,
    default: 'Por que escolher a nossa plataforma?'
  },
  description: {
    type: String,
    default: 'Oferecemos a melhor experiência de aprendizado online com recursos exclusivos pensados para o seu crescimento profissional.'
  },
  features: {
    type: Array,
    default: () => [
      {
        id: 1,
        icon: School,
        title: 'Instrutores Experts',
        description: 'Aprenda com profissionais que atuam nas maiores empresas do mundo e tragam experiência real de mercado.',
        color: 'rgba(13, 127, 242, 0.1)'
      },
      {
        id: 2,
        icon: CheckCircle,
        title: 'Certificado Incluso',
        description: 'Receba um certificado digital verificado ao concluir cada curso para turbinar seu currículo e LinkedIn.',
        color: 'rgba(16, 185, 129, 0.1)'
      },
      {
        id: 3,
        icon: Infinity,
        title: 'Acesso Vitalício',
        description: 'Pague uma vez e tenha acesso ao conteúdo para sempre, incluindo todas as futuras atualizações do curso.',
        color: 'rgba(99, 102, 241, 0.1)'
      },
    ]
  }
})
</script>

<style scoped>
.features {
  padding: 4rem 0;
  width: 70%;
  margin: auto;
}

span{
    display: flex;
    align-items: center;
    justify-content: center;
}

.container {
  max-width: 1280px;
  margin: 0 auto;
  padding: 0 2rem;
}

.section-header {
  text-align: center;
  max-width: 768px;
  margin: 0 auto 3rem;
}

.section-title {
  font-size: 2.25rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 1rem;
}

.section-description {
  font-size: 1.125rem;
  color: #64748b;
  line-height: 1.6;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
}

.feature-card {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  padding: 2rem;
  background-color: white;
  border: 1px solid #e2e8f0;
  border-radius: 1rem;
  transition: all 0.3s ease;
}

.feature-card:hover {
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.1);
  transform: translateY(-5px);
}

.feature-icon {
  width: 56px;
  height: 56px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.3s ease;
}

.feature-card:hover .feature-icon {
  transform: scale(1.1);
}

.feature-icon-svg {
  width: 28px;
  height: 28px;
  color: #0d7ff2;
}

.feature-content {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.feature-title {
  font-size: 1.25rem;
  font-weight: 700;
  color: #0f172a;
  line-height: 1.3;
}

.feature-text {
  color: #64748b;
  line-height: 1.6;
  font-size: 0.9375rem;
}

/* Responsive Design */
@media (max-width: 1200px) {
  .features {
    width: 85%;
  }
}

@media (max-width: 1024px) {
  .features {
    width: 90%;
  }
  
  .features-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .features {
    width: 100%;
    padding: 3rem 0;
  }
  
  .container {
    padding: 0 1.5rem;
  }
  
  .features-grid {
    grid-template-columns: 1fr;
  }

  .section-title {
    font-size: 1.75rem;
  }
  
  .section-description {
    font-size: 1rem;
  }
  
  .feature-card {
    padding: 1.5rem;
  }
  
  .feature-icon {
    width: 48px;
    height: 48px;
  }
  
  .feature-icon-svg {
    width: 24px;
    height: 24px;
  }
}

@media (max-width: 480px) {
  .features {
    padding: 2rem 0;
  }
  
  .container {
    padding: 0 1rem;
  }
  
  .section-header {
    margin-bottom: 2rem;
  }
  
  .feature-card {
    padding: 1.25rem;
    gap: 1rem;
  }
}
</style>