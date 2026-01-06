<template>
  <div class="form-container">
    <div class="form-wrapper">
      <div class="form-header">
        <h2 class="form-title">Bem-vindo a Learnfyx!</h2>
        <p class="form-subtitle">Faça login ou crie sua conta para começar.</p>
      </div>

      <form @submit.prevent="handleSubmit" class="form">
        <div class="form-group">
          <label for="email" class="label">Email</label>
          <div class="input-wrapper">
            <span class="input-icon">✉️</span>
            <input
              id="email"
              v-model="email"
              type="email"
              placeholder="seu@email.com"
              class="input"
              required
            />
          </div>
        </div>

        <div class="form-group">
          <label for="password" class="label">Senha</label>
          <div class="input-wrapper">
            <span class="input-icon">🔒</span>
            <input
              id="password"
              v-model="password"
              :type="showPassword ? 'text' : 'password'"
              placeholder="••••••••"
              class="input"
              required
            />
            <button
              type="button"
              @click="showPassword = !showPassword"
              class="toggle-password"
            >
              {{ showPassword ? '👁️' : '👁️‍🗨️' }}
            </button>
          </div>
        </div>

        <div class="form-actions">
          <label class="checkbox-wrapper">
            <input type="checkbox" v-model="rememberMe" />
            <span class="checkbox-label">Lembrar de mim</span>
          </label>
          <a href="#" class="forgot-link">Esqueci a senha</a>
        </div>

        <button type="submit" class="submit-btn">
          Acessar Plataforma
          <span class="arrow">→</span>
        </button>
      </form>

      <div class="divider">
        <span>OU ACESSE COM</span>
      </div>

      <div class="social-buttons">
        <button type="button" class="social-btn google" @click="loginWithGoogle">
          <svg viewBox="0 0 24 24" width="20" height="20">
            <path fill="#4285F4" d="M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92c-.26 1.37-1.04 2.53-2.21 3.31v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.09z"/>
            <path fill="#34A853" d="M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z"/>
            <path fill="#FBBC05" d="M5.84 14.09c-.22-.66-.35-1.36-.35-2.09s.13-1.43.35-2.09V7.07H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.93l2.85-2.22.81-.62z"/>
            <path fill="#EA4335" d="M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.07l3.66 2.84c.87-2.6 3.3-4.53 6.16-4.53z"/>
          </svg>
          Google
        </button>
        
        <button type="button" class="social-btn facebook" @click="loginWithFacebook">
          <svg viewBox="0 0 24 24" width="20" height="20" fill="#1877F2">
            <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
          </svg>
          Facebook
        </button>
      </div>

      <p class="terms">
        Ao continuar, você confirma que leu e concordou com nossos
        <a href="#">Termos de Uso</a> e <a href="#">Privacidade</a>.
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const activeTab = ref('login');
const email = ref('');
const password = ref('');
const showPassword = ref(false);
const rememberMe = ref(false);

const handleSubmit = () => {
  console.log('Login:', { email: email.value, password: password.value });
  alert(`${activeTab.value === 'login' ? 'Login' : 'Cadastro'} realizado com sucesso!`);
};

const loginWithGoogle = () => {
  console.log('Login com Google');
  alert('Login com Google');
};

const loginWithFacebook = () => {
  console.log('Login com Facebook');
  alert('Login com Facebook');
};
</script>

<style scoped>
.form-container {
  background-color: #f5f5f5;
  height: auto;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem;
}

.form-wrapper {
  border-radius: 12px;
  padding: 3rem;
  width: 80%;
}

.form-header {
  margin-bottom: 2rem;
}

.form-title {
  font-size: 2rem;
  font-weight: 900;
  color: #1f2937;
  margin-bottom: 0.5rem;
}

.form-subtitle {
  color: #6b7280;
  font-size: 0.938rem;
}

.tabs {
  display: flex;
  gap: 0.5rem;
  margin-bottom: 2rem;
  background-color: #f9fafb;
  padding: 0.25rem;
  border-radius: 8px;
}

.tab {
  flex: 1;
  padding: 0.75rem;
  border: none;
  background: transparent;
  color: #6b7280;
  font-weight: 600;
  font-size: 0.938rem;
  border-radius: 6px;
  cursor: pointer;
  transition: all 0.3s;
}

.tab.active {
  background-color: white;
  color: #1f2937;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.form {
  margin-bottom: 1.5rem;
}

.form-group {
  margin-bottom: 1.5rem;
}

.label {
  display: block;
  font-size: 0.875rem;
  font-weight: 600;
  color: #374151;
  margin-bottom: 0.5rem;
}

.input-wrapper {
  position: relative;
  display: flex;
  align-items: center;
}

.input-icon {
  position: absolute;
  left: 1rem;
  font-size: 1.125rem;
  opacity: 0.5;
}

.input {
  width: 100%;
  padding: 0.875rem 1rem 0.875rem 3rem;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  font-size: 0.938rem;
  transition: all 0.3s;
  outline: none;
}

.input:focus {
  border-color: #3b82f6;
  box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.1);
}

.toggle-password {
  position: absolute;
  right: 1rem;
  background: none;
  border: none;
  cursor: pointer;
  font-size: 1.125rem;
  opacity: 0.6;
  transition: opacity 0.3s;
}

.toggle-password:hover {
  opacity: 1;
}

.form-actions {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1.5rem;
}

.checkbox-wrapper {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  cursor: pointer;
}

.checkbox-wrapper input[type="checkbox"] {
  width: 16px;
  height: 16px;
  cursor: pointer;
}

.checkbox-label {
  font-size: 0.875rem;
  color: #6b7280;
}

.forgot-link {
  color: #3b82f6;
  text-decoration: none;
  font-size: 0.875rem;
  font-weight: 600;
  transition: color 0.3s;
}

.forgot-link:hover {
  color: #2563eb;
}

.submit-btn {
  width: 100%;
  padding: 1rem;
  background: linear-gradient(135deg, #3b82f6 0%, #2563eb 100%);
  color: white;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  font-weight: 700;
  cursor: pointer;
  transition: all 0.3s;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  box-shadow: 0 4px 12px rgba(59, 130, 246, 0.3);
}

.submit-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(59, 130, 246, 0.4);
}

.arrow {
  font-size: 1.25rem;
  transition: transform 0.3s;
}

.submit-btn:hover .arrow {
  transform: translateX(4px);
}

.divider {
  text-align: center;
  margin: 2rem 0;
  position: relative;
}

.divider::before,
.divider::after {
  content: '';
  position: absolute;
  top: 50%;
  width: 40%;
  height: 1px;
  background-color: #e5e7eb;
}

.divider::before {
  left: 0;
}

.divider::after {
  right: 0;
}

.divider span {
  padding: 0 1rem;
  color: #9ca3af;
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 0.5px;
}

.social-buttons {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
  margin-bottom: 2rem;
}

.social-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  padding: 0.875rem;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  background-color: white;
  font-size: 0.875rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s;
}

.social-btn:hover {
  background-color: #f9fafb;
  border-color: #d1d5db;
  transform: translateY(-1px);
}

.social-btn.google {
  color: #1f2937;
}

.social-btn.facebook {
  color: #1877F2;
}

.terms {
  text-align: center;
  font-size: 0.75rem;
  color: #9ca3af;
  line-height: 1.6;
}

.terms a {
  color: #3b82f6;
  text-decoration: none;
  font-weight: 600;
}

.terms a:hover {
  text-decoration: underline;
}

@media (max-width: 768px) {
  .form-wrapper {
    padding: 2rem 1.5rem;
  }

  .form-title {
    font-size: 1.5rem;
  }

  .social-buttons {
    grid-template-columns: 1fr;
  }
}
</style>