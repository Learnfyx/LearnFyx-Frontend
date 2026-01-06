<template>
  <section class="stats-bar">
    <div class="container">
      <div class="stats-grid">
        <div class="stat-box" v-for="stat in stats" :key="stat.id">
          <span class="stat-number">{{ stat.number }}</span>
          <span class="stat-label">{{ stat.label }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const stats = [
  {
    id: 1,
    number: '500+',
    label: 'Cursos Online'
  },
  {
    id: 2,
    number: '120+',
    label: 'Instrutores'
  },
  {
    id: 3,
    number: '15k',
    label: 'Avaliações 5★'
  },
  {
    id: 4,
    number: '24h',
    label: 'Suporte'
  }
]
</script>

<style scoped>
.stats-bar {
  background-color: white;
  border-top: 1px solid #f1f5f9;
  border-bottom: 1px solid #f1f5f9;
  padding: 2.5rem 0;
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2rem;
  text-align: center;
}

.stat-box {
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
}

.stat-number {
  font-size: 2rem;
  font-weight: 900;
  color: #0f172a;
}

.stat-label {
  font-size: 0.875rem;
  color: #64748b;
  font-weight: 500;
}

/* Responsive Design */
@media (max-width: 768px) {
  .stats-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 480px) {
  .stats-grid {
    grid-template-columns: 1fr;
  }
  
  .stat-number {
    font-size: 1.75rem;
  }
}
</style>