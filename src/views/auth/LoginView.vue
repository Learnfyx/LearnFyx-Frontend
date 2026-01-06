<template>
    <HeaderMain />
    <div class="login-view">
        <BannerSection class="banner-section" />
        <FormSectionLogin class="form-section" />
    </div>
</template>

<script setup>
import { BannerSection, FormSectionLogin, HeaderMain } from '@/components';
</script>

<style scoped>
.login-view {
    display: grid;
    grid-template-columns: 1.3fr 1fr;
        height: 100vh;
}

.banner-section {
    position: sticky;
    top: 0;
}

.form-section {
    overflow-y: auto;
}

@media (max-width: 1024px) {
    .login-view {
        grid-template-columns: 1fr;
        overflow-y: auto;
    }

    .banner-section {
        position: relative;
        height: auto;
        min-height: 60vh;
    }
}
</style>