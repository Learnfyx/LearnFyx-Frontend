<template>
  <header class="header">
    <div class="header-container">
      <div class="header-left">
        <div class="logo">
          <div class="logo-icon">
            <School class="icon" />
          </div>
          <h2 class="logo-text">Learnfyx</h2>
        </div>
        <nav class="nav-desktop">
          <a href="#" class="nav-link">Cursos</a>
          <a href="#" class="nav-link">Categorias</a>
          <a href="#" class="nav-link">Certificado</a>
          <a href="#" class="nav-link">Quem Somos</a>
          <a href="#" class="nav-link">Blog</a>
          <a href="#" class="nav-link">Central de Ajuda</a>
        </nav>
      </div>
      <div class="header-right">
        <div class="search-box">
          <Magnify class="search-icon" />
          <input type="text" placeholder="Buscar cursos..." class="search-input" />
        </div>
        <div class="header-actions">
          <button class="btn-secondary">Entrar</button>
          <button class="btn-primary">Cadastrar</button>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import School from 'vue-material-design-icons/School.vue'
import Magnify from 'vue-material-design-icons/Magnify.vue'
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

span{
    display: flex;
    align-items: center;
    justify-content: center;
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

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
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
  font-size: 20px;
}

.logo-text {
  font-size: 1.25rem;
  font-weight: 700;
  color: #0f172a;
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
}

.nav-link:hover {
  color: #0d7ff2;
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
}

.search-icon {
  color: #94a3b8;
  font-size: 20px;
}

.search-input {
  border: none;
  background: transparent;
  outline: none;
  width: 200px;
  font-size: 0.875rem;
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
  transition: background-color 0.3s;
}

.btn-secondary:hover {
  background-color: #f1f5f9;
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
  transition: all 0.3s;
  box-shadow: 0 2px 8px rgba(13, 127, 242, 0.3);
}

.btn-primary:hover {
  background-color: #0c6cd9;
  transform: translateY(-1px);
}

/* Responsive */
@media (max-width: 1024px) {
  .nav-desktop {
    display: none;
  }
}

@media (max-width: 768px) {
  .search-box {
    display: none;
  }
  
  .header-container {
    padding: 1rem;
  }
}
</style>