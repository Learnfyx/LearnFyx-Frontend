<template>
  <header class="header">
    <div class="header-container">
      <div class="header-left">
        <!-- Logo clicável -->
        <router-link to="/" class="logo-link">
          <div class="logo">
            <div class="logo-icon">
              <img src="../../assets/images/Learnfyx-Logo.png" alt="Learnfyx Logo">
            </div>
            <h2 class="logo-text">Learnfyx</h2>
          </div>
        </router-link>
        
        <nav class="nav-desktop">
          <router-link to="/cursos" class="nav-link">Cursos</router-link>
          <router-link to="/categorias" class="nav-link">Categorias</router-link>
          <router-link to="/certificado" class="nav-link">Certificado</router-link>
          <router-link to="/sobre" class="nav-link">Quem Somos</router-link>
          <router-link to="/blog" class="nav-link">Blog</router-link>
          <router-link to="/ajuda" class="nav-link">Central de Ajuda</router-link>
        </nav>
      </div>
      <div class="header-right">
        <div class="search-box">
          <Magnify class="search-icon" />
          <input type="text" placeholder="Buscar cursos..." class="search-input" />
        </div>
        <div class="header-actions">
          <button class="btn-secondary" @click="goToLogin">Entrar</button>
          <button class="btn-primary" @click="goToRegister">Cadastrar</button>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import { useRouter } from 'vue-router'
import Magnify from 'vue-material-design-icons/Magnify.vue'

const router = useRouter()

const goToLogin = () => {
  router.push('/login')
}

const goToRegister = () => {
  router.push('/cadastro')
}
</script>

<style scoped>
.header {
  position: sticky;
  top: 0;
  z-index: 1000;
  background-color: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid #e5e7eb;
}

.header-container {
  width: 70%;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 0;
  height: 64px;
}

.header-left {
  display: flex;
  align-items: center;
  gap: 2rem;
}

/* Link da logo */
.logo-link {
  text-decoration: none;
  display: flex;
  align-items: center;
  cursor: pointer;
}

.logo-link:hover .logo-text {
  color: #0d7ff2;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.logo-icon {
  width: 50px;
  height: 50px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  transition: transform 0.3s ease;
}

.logo-link:hover .logo-icon {
  transform: scale(1.05);
}

.logo-icon img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.logo-text {
  font-size: 1.25rem;
  font-weight: 700;
  color: #0f172a;
  transition: color 0.3s ease;
}

.nav-desktop {
  display: flex;
  gap: 1.5rem;
}

.nav-link {
  text-decoration: none;
  color: #64748b;
  font-size: 0.875rem;
  font-weight: 500;
  transition: color 0.3s;
  white-space: nowrap;
  position: relative;
}

.nav-link:hover {
  color: #0d7ff2;
}

.nav-link.router-link-active {
  color: #0d7ff2;
  font-weight: 600;
}

.nav-link.router-link-active::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 100%;
  height: 2px;
  background-color: #0d7ff2;
  border-radius: 1px;
}

.header-right {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.search-box {
  display: flex;
  align-items: center;
  background-color: #f1f5f9;
  padding: 0.5rem 1rem;
  border-radius: 8px;
  gap: 0.5rem;
  transition: all 0.3s ease;
}

.search-box:focus-within {
  background-color: white;
  box-shadow: 0 0 0 2px rgba(13, 127, 242, 0.1);
}

.search-icon {
  color: #94a3b8;
  width: 20px;
  height: 20px;
}

.search-input {
  border: none;
  background: transparent;
  outline: none;
  width: 200px;
  font-size: 0.875rem;
  color: #334155;
}

.search-input::placeholder {
  color: #94a3b8;
}

.header-actions {
  display: flex;
  gap: 0.5rem;
}

.btn-secondary {
  padding: 0.5rem 1rem;
  border: none;
  background: transparent;
  color: #334155;
  font-weight: 600;
  font-size: 0.875rem;
  border-radius: 8px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn-secondary:hover {
  background-color: #f1f5f9;
  transform: translateY(-1px);
}

.btn-primary {
  padding: 0.5rem 1rem;
  border: none;
  background-color: #0d7ff2;
  color: white;
  font-weight: 600;
  font-size: 0.875rem;
  border-radius: 8px;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 2px 8px rgba(13, 127, 242, 0.3);
}

.btn-primary:hover {
  background-color: #0c6cd9;
  transform: translateY(-1px);
  box-shadow: 0 4px 12px rgba(13, 127, 242, 0.4);
}

/* Responsive */
@media (max-width: 1200px) {
  .header-container {
    width: 85%;
  }
}

@media (max-width: 1024px) {
  .header-container {
    width: 90%;
  }
  
  .nav-desktop {
    display: none;
  }
}

@media (max-width: 768px) {
  .header-container {
    width: 100%;
    padding: 1rem;
  }
  
  .search-box {
    display: none;
  }
  
  .logo-text {
    font-size: 1.125rem;
  }
  
  .logo-icon {
    width: 40px;
    height: 40px;
  }
}

@media (max-width: 480px) {
  .header-container {
    padding: 0.75rem;
  }
  
  .header-actions {
    gap: 0.25rem;
  }
  
  .btn-secondary,
  .btn-primary {
    padding: 0.5rem 0.75rem;
    font-size: 0.8125rem;
  }
  
  .logo-text {
    display: none;
  }
}
</style>