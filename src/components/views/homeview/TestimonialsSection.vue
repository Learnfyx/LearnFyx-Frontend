<template>
    <div class="main">
        
  <section class="testimonials">
    <div class="container">
      <h2 class="section-title center">{{ title }}</h2>
      <div class="testimonials-grid">
        <div 
          v-for="testimonial in testimonials" 
          :key="testimonial.id" 
          class="testimonial-card"
        >
          <div class="testimonial-header">
            <img :src="testimonial.avatar" :alt="testimonial.name" class="avatar" />
            <div>
              <h4 class="testimonial-name">{{ testimonial.name }}</h4>
              <p class="testimonial-role">{{ testimonial.role }}</p>
            </div>
          </div>
          <p class="testimonial-text">{{ testimonial.text }}</p>
          <div class="testimonial-rating">
            <span v-for="i in testimonial.rating || 5" :key="i">★</span>
          </div>
        </div>
      </div>
    </div>
  </section>
  
    </div>
</template>

<script setup>
// eslint-disable-next-line no-unused-vars
const props = defineProps({
  title: {
    type: String,
    default: 'O que nossos alunos dizem'
  },
  testimonials: {
    type: Array,
    default: () => [
      {
        id: 1,
        name: 'Lucas Martins',
        role: 'Dev Web Fullstack',
        text: 'A plataforma mudou minha carreira. Os cursos são diretos ao ponto e os projetos práticos ajudam muito na fixação do conteúdo.',
        rating: 5,
        avatar: 'https://lh3.googleusercontent.com/aida-public/AB6AXuCr1nx4BpK4W8wKyGpEg_mXqBZJPfl5tXJKgd-FN5DH1bYAkXVdqdec_aamVs_apFs9HCKjVJ5fKdqSRre9wJzGeFqOO4EjoAZIQDjPD6TRWyitcjVY7PhcuxfzWix6A89tsd3F6o6sX6Tv_zYZb-ks2wgm1rwiQL44uQ-LVKhhVMm_s86OTl5DM_27HDlGPObhd0v9X-i40pCowP4ZmFR7pQXblJS0d5hvQWqQ8qiZrf3AkPqBK9oz2c90pb0GLx-GFuM0Yabiulny'
      },
      {
        id: 2,
        name: 'Marina Silva',
        role: 'UX Designer',
        text: 'Didática excelente e suporte muito rápido. O certificado me ajudou a conseguir meu primeiro emprego na área de design.',
        rating: 5,
        avatar: 'https://lh3.googleusercontent.com/aida-public/AB6AXuAd1F_TsI7zYRXShBbOH1sCWZ1KKlzJmB6qfnEBkOpICBNody5hD_jQ3_AohadUEDH5X913PKpUOD7r8CJCVI1ykbQreVsj3HpQ7clNmTnFOSgY6SJ34j4gI92v1lfj4jrNUCLPucASO8KmWRvDHzD0zQ2GYvYT2z8yONNQpkFGXjKmzzaL34yxIx_uiAJC8fzzJwu3uvrkl96L-Lu_7qmZ-6lHF8Cu0xbdqWygRdNsKFPA_71_j2BJAH4QKMIJ0Vohv1U-PoFQ-4Od'
      },
      {
        id: 3,
        name: 'Pedro Santos',
        role: 'Analista de Dados',
        text: 'O melhor custo benefício do mercado. Acesso vitalício é um diferencial enorme para quem precisa rever o conteúdo.',
        rating: 5,
        avatar: 'https://lh3.googleusercontent.com/aida-public/AB6AXuB6u0nC7sS3DDUK9JGIWOu6Lpso5_86kpjy1K3P2xon-VRTpIfD31ryVnpTH3N7dHsgaI2c78BrCADqdg-x1z2iLcHdcMRGatdb1SWOyc1jnOjoHmHUUtSXi4WdsC5QzqsqY75MDbD8fWa8R5X0Yt9a6LgtHnXmr0r1mXaTMd9tOuWI_Wd3C9U-vPffcS5DECZ4iM9LDXw7JRzP0qtPrl1RX4i8c-vij1U_Kf2jN-KR83GNUN6MLeOvWxAuy5fNI4op0AutoldDhUvh'
      }
    ]
  }
})
</script>

<style scoped>
.main{
    background-color: rgba(13, 127, 242, 0.05);

}

.testimonials {
  padding: 4rem 0;
  width: 70%;
  margin: auto;
}

.section-title.center {
  text-align: center;
  margin-bottom: 1rem;
}

.testimonials-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
}

.testimonial-card {
  background-color: white;
  padding: 1.5rem;
  border-radius: 1rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease;
}

.testimonial-card:hover {
  transform: translateY(-5px);
}

.testimonial-header {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1rem;
}

.avatar {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  object-fit: cover;
  background-color: #f1f5f9;
}

.testimonial-name {
  font-weight: 700;
  color: #0f172a;
  font-size: 1rem;
}

.testimonial-role {
  font-size: 0.875rem;
  color: #64748b;
}

.testimonial-text {
  color: #64748b;
  line-height: 1.6;
  margin-bottom: 1rem;
}

.testimonial-rating {
  display: flex;
  color: #fbbf24;
  font-size: 0.875rem;
}

/* Responsive Design */
@media (max-width: 1024px) {
  .testimonials-grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 768px) {
  .section-title {
    font-size: 1.75rem;
  }
  
  .testimonial-card {
    padding: 1.25rem;
  }
}
</style>