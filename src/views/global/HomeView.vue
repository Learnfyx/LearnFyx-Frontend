<template>
  <div class="app">
    <HeaderMain />
    
    <main>
      <HeroSection 
        @start-now="handleStartNow"
        @view-courses="handleViewCourses"
      />

      <StatsBar />
      <FeaturesSection />

      <CoursesSection 
        @view-all="handleViewAllCourses"
        @course-click="handleCourseClick"
        @details-click="handleCourseDetails"
      />

      <TestimonialsSection />
      <NewsletterSection @subscribe="handleNewsletterSubscribe" />
    </main>

    <FooterMain />
  </div>
</template>

<script setup>
import { 
  HeaderMain, 
  HeroSection, 
  StatsBar, 
  FeaturesSection,
  CoursesSection,
  TestimonialsSection,
  NewsletterSection,
  FooterMain 
} from '@/components';

const handleStartNow = () => {
  alert('Redirecionando para a página de cadastro...');
};

const handleViewCourses = () => {
  alert('Redirecionando para a lista de cursos...');
};

const handleViewAllCourses = () => {
  alert('Redirecionando para todos os cursos...');
};

const handleCourseClick = (course) => {
  alert(`Clicou no curso: ${course.title}`);
};

const handleCourseDetails = (course) => {
  alert(`Detalhes do curso: ${course.title}`);
};

const handleNewsletterSubscribe = (email) => {
  alert(`Email cadastrado na newsletter: ${email}`);
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f5f7f8;
  color: #0d141c;
  min-height: 100vh;
}

.container {
  max-width: 1280px;
  margin: 0 auto;
  padding: 0 2rem;
}

@media (max-width: 768px) {
  .container {
    padding: 0 1rem;
  }
}
</style>