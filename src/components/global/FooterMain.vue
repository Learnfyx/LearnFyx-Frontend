<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-grid">
        <div class="footer-brand">
          <div class="logo">
            <div class="logo-icon">
              <School class="icon" />
            </div>
            <h2 class="logo-text">{{ brandName }}</h2>
          </div>
          <p class="footer-description">{{ brandDescription }}</p>
        </div>
        
        <div 
          v-for="(linkGroup, index) in linkGroups" 
          :key="index" 
          class="footer-links"
        >
          <h3 class="footer-heading">{{ linkGroup.title }}</h3>
          <ul>
            <li v-for="link in linkGroup.links" :key="link.id">
              <a :href="link.url">{{ link.text }}</a>
            </li>
          </ul>
        </div>
        
        <div class="footer-social">
          <h3 class="footer-heading">{{ socialTitle }}</h3>
          <div class="social-links">
            <a 
              v-for="social in socialLinks" 
              :key="social.id" 
              :href="social.url"
              :title="social.name"
              class="social-link"
            >
              <component :is="social.icon" class="social-icon" />
            </a>
          </div>
        </div>
      </div>
      <div class="footer-bottom">
        <p>{{ copyrightText }}</p>
      </div>
    </div>
  </footer>
</template>

<script setup>
import School from 'vue-material-design-icons/School.vue'
import Instagram from 'vue-material-design-icons/Instagram.vue'
import Twitter from 'vue-material-design-icons/Twitter.vue'
import Facebook from 'vue-material-design-icons/Facebook.vue'
import Linkedin from 'vue-material-design-icons/Linkedin.vue'
import Youtube from 'vue-material-design-icons/Youtube.vue'

// eslint-disable-next-line no-unused-vars
const props = defineProps({
  brandName: {
    type: String,
    default: 'Learnfyx'
  },
  brandDescription: {
    type: String,
    default: 'A melhor plataforma para impulsionar sua carreira com cursos práticos e acessíveis.'
  },
  linkGroups: {
    type: Array,
    default: () => [
      {
        title: 'Produto',
        links: [
          { id: 1, text: 'Cursos', url: '#' },
          { id: 2, text: 'Preços', url: '#' },
        ]
      },
      {
        title: 'Suporte',
        links: [
          { id: 4, text: 'Central de Ajuda', url: '#' },
          { id: 5, text: 'Termos de Uso', url: '#' },
          { id: 6, text: 'Privacidade', url: '#' }
        ]
      }
    ]
  },
  socialTitle: {
    type: String,
    default: 'Social'
  },
  socialLinks: {
    type: Array,
    default: () => [
      { 
        id: 1, 
        name: 'Instagram', 
        icon: Instagram, 
        url: '#' 
      },
      { 
        id: 2, 
        name: 'Twitter', 
        icon: Twitter, 
        url: '#' 
      },
      { 
        id: 3, 
        name: 'Facebook', 
        icon: Facebook, 
        url: '#' 
      },
      { 
        id: 4, 
        name: 'LinkedIn', 
        icon: Linkedin, 
        url: '#' 
      },
      { 
        id: 5, 
        name: 'YouTube', 
        icon: Youtube, 
        url: '#' 
      }
    ]
  },
  copyrightText: {
    type: String,
    default: '© 2024 Learnfyx. Todos os direitos reservados.'
  }
})
</script>

<style scoped>
.footer {
  background-color: white;
  border-top: 1px solid #e2e8f0;
  padding: 3rem 0;
}

.container {
  max-width: 1280px;
  margin: 0 auto;
  padding: 0 2rem;
}

span{
    display: flex;
    align-items: center;
    justify-content: center;
}

.footer-grid {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 1fr;
  gap: 3rem;
  margin-bottom: 3rem;
}

.footer-brand {
  max-width: 320px;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

.logo-icon {
  width: 32px;
  height: 32px;
  background-color: #0d7ff2;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.logo-icon .icon {
  color: white;
  width: 20px;
  height: 20px;
}

.logo-text {
  font-size: 1.25rem;
  font-weight: 700;
  color: #0f172a;
}

.footer-description {
  font-size: 0.875rem;
  color: #64748b;
  line-height: 1.6;
}

.footer-links h3,
.footer-social h3 {
  font-size: 0.875rem;
  font-weight: 600;
  color: #0f172a;
  margin-bottom: 1rem;
}

.footer-links ul {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.footer-links a {
  text-decoration: none;
  color: #64748b;
  font-size: 0.875rem;
  transition: color 0.3s;
}

.footer-links a:hover {
  color: #0d7ff2;
}

.social-links {
  display: flex;
  gap: 0.75rem;
  flex-wrap: wrap;
}

.social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 36px;
  height: 36px;
  border-radius: 6px;
  background-color: #f1f5f9;
  color: #64748b;
  transition: all 0.3s ease;
  text-decoration: none;
}

.social-link:hover {
  background-color: #0d7ff2;
  color: white;
  transform: translateY(-2px);
}

.social-icon {
  width: 18px;
  height: 18px;
}

.footer-bottom {
  border-top: 1px solid #e2e8f0;
  padding-top: 2rem;
  text-align: center;
}

.footer-bottom p {
  font-size: 0.875rem;
  color: #64748b;
}

/* Responsive Design */
@media (max-width: 1024px) {
  .footer-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .footer-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .footer-brand {
    max-width: 100%;
  }
  
  .container {
    padding: 0 1rem;
  }
  
  .social-links {
    justify-content: flex-start;
  }
}
</style>