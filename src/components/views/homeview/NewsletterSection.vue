<template>
    <section class="newsletter">
        <div class="container">
            <div class="newsletter-grid">
                <div class="newsletter-content">
                    <h2 class="newsletter-title">{{ title }}</h2>
                    <p class="newsletter-description">{{ description }}</p>
                    <form class="newsletter-form" @submit.prevent="handleSubmit">
                        <div class="input-wrapper">
                            <EmailOutline class="input-icon" />
                            <input type="email" v-model="email" :placeholder="placeholder" class="newsletter-input"
                                required />
                        </div>
                        <button type="submit" class="btn-subscribe">
                            <Send class="btn-icon" />
                            {{ buttonText }}
                        </button>
                    </form>
                </div>
                <div class="newsletter-features">
                    <div v-for="feature in features" :key="feature.id" class="newsletter-feature">
                        <div class="feature-icon-small">
                            <component :is="feature.icon" class="feature-icon" />
                        </div>
                        <h4 class="feature-small-title">{{ feature.title }}</h4>
                        <p class="feature-small-text">{{ feature.text }}</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'
import EmailOutline from 'vue-material-design-icons/EmailOutline.vue'
import Send from 'vue-material-design-icons/Send.vue'
import CalendarMonth from 'vue-material-design-icons/CalendarMonth.vue'
import AccountGroup from 'vue-material-design-icons/AccountGroup.vue'

// eslint-disable-next-line no-unused-vars
const props = defineProps({
    title: {
        type: String,
        default: 'Receba ofertas exclusivas.'
    },
    description: {
        type: String,
        default: 'Cadastre seu email e receba semanalmente dicas de carreira e cupons de desconto para novos cursos.'
    },
    placeholder: {
        type: String,
        default: 'Digite seu email'
    },
    buttonText: {
        type: String,
        default: 'Inscrever-se'
    },
    features: {
        type: Array,
        default: () => [
            {
                id: 1,
                icon: CalendarMonth,
                title: 'Novos Cursos Semanais',
                text: 'Conteúdo sempre atualizado com as últimas tendências do mercado de tecnologia.'
            },
            {
                id: 2,
                icon: AccountGroup,
                title: 'Comunidade Ativa',
                text: 'Troque experiências com outros alunos e instrutores em nosso fórum exclusivo.'
            }
        ]
    }
})

const emit = defineEmits(['subscribe'])

const email = ref('')

const handleSubmit = () => {
    emit('subscribe', email.value)
    email.value = ''
}
</script>

<style scoped>
.newsletter {
    padding: 4rem 0;
    background-color: #1e293b;
    color: white;
}

span {
    display: flex;
    align-items: center;
    justify-content: center;
}

.container {
    width: 70%;
    margin: 0 auto;
    padding: 0 2rem;
}

.newsletter-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: start;
}

.newsletter-content {
    max-width: 512px;
}

.newsletter-title {
    font-size: 2.25rem;
    font-weight: 700;
    margin-bottom: 1rem;
}

.newsletter-description {
    font-size: 1.125rem;
    color: #cbd5e1;
    margin-bottom: 1.5rem;
    line-height: 1.6;
}

.newsletter-form {
    display: flex;
    gap: 1rem;
    max-width: 448px;
}

.input-wrapper {
    flex: 1;
    position: relative;
    display: flex;
    align-items: center;
}

.input-icon {
    position: absolute;
    left: 12px;
    color: rgba(255, 255, 255, 0.4);
    width: 20px;
    height: 20px;
}

.newsletter-input {
    width: 100%;
    padding: 0.625rem 1rem 0.625rem 40px;
    background-color: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 6px;
    color: white;
    font-size: 0.875rem;
    outline: none;
    transition: all 0.3s;
}

.newsletter-input:focus {
    background-color: rgba(255, 255, 255, 0.08);
    border-color: #0d7ff2;
}

.newsletter-input::placeholder {
    color: rgba(255, 255, 255, 0.4);
}

.btn-subscribe {
    padding: 0.625rem 1.5rem;
    background-color: #0d7ff2;
    color: white;
    border: none;
    border-radius: 6px;
    font-size: 0.875rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s;
    white-space: nowrap;
    display: flex;
    align-items: center;
    gap: 0.5rem;
}

.btn-subscribe:hover {
    background-color: #0c6cd9;
    transform: translateY(-1px);
}

.btn-icon {
    width: 16px;
    height: 16px;
}

.newsletter-features {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
}

.newsletter-feature {
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

.feature-icon-small {
    width: 48px;
    height: 48px;
    background-color: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.feature-icon {
    color: #0d7ff2;
    width: 24px;
    height: 24px;
}

.feature-small-title {
    font-weight: 600;
    color: white;
    font-size: 1rem;
}

.feature-small-text {
    color: #94a3b8;
    font-size: 0.875rem;
    line-height: 1.6;
}

/* Responsive Design */
@media (max-width: 1024px) {
    .newsletter-grid {
        grid-template-columns: 1fr;
        gap: 2rem;
    }
}

@media (max-width: 768px) {
    .newsletter-features {
        grid-template-columns: 1fr;
    }

    .newsletter-title {
        font-size: 1.75rem;
    }

    .newsletter-form {
        flex-direction: column;
    }

    .newsletter-input,
    .btn-subscribe {
        width: 100%;
    }

    .btn-subscribe {
        justify-content: center;
    }

    .container {
        padding: 0 1rem;
    }
}
</style>