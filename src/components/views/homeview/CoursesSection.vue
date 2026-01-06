<template>
    <div class="main">
        <section class="courses">
            <div class="container">
                <div class="courses-header">
                    <h2 class="section-title">{{ title }}</h2>
                    <a href="#" class="view-all" @click.prevent="$emit('view-all')">
                        {{ viewAllText }}
                        <span>→</span>
                    </a>
                </div>
                <div class="courses-grid">
                    <div v-for="course in courses" :key="course.id" class="course-card"
                        @click="$emit('course-click', course)">
                        <div class="course-image">
                            <img :src="course.image" :alt="course.title" />
                            <div v-if="course.badge" class="course-badge"
                                :style="{ backgroundColor: course.badgeColor }">
                                {{ course.badge }}
                            </div>
                        </div>
                        <div class="course-content">
                            <div class="course-rating">
                                <div class="stars">
                                    <span v-for="i in 5" :key="i">
                                        {{ i <= Math.floor(course.rating) ? '★' : (i - 0.5 === course.rating ? '⯨' : '☆')
                                            }} </span>
                                </div>
                                <span class="rating-text">({{ course.rating }})</span>
                            </div>
                            <h3 class="course-title">{{ course.title }}</h3>
                            <p class="course-instructor">Por {{ course.instructor }}</p>
                            <div class="course-footer">
                                <span class="course-price">{{ course.price }}</span>
                                <button class="btn-details" @click.stop="$emit('details-click', course)">
                                    Detalhes
                                </button>
                            </div>
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
        default: 'Cursos em Destaque'
    },
    viewAllText: {
        type: String,
        default: 'Ver todos os cursos'
    },
    courses: {
        type: Array,
        default: () => [
            {
                id: 1,
                title: 'Desenvolvimento Web Fullstack',
                instructor: 'Carlos Silva',
                price: 'R$ 29,90',
                rating: 4.8,
                badge: 'Mais Vendido',
                badgeColor: '#10b981',
                image: 'https://lh3.googleusercontent.com/aida-public/AB6AXuDOwVqaoZHyfk8tAG8xD0Uq1LjHUJniU3Hz3eaoFx_R4rLBU4kD3vL-NzAbRVcsuWjoWw_qapVxlCxiJCzl7puCaGUumSRbqEArDxsBVksm9lGBWBmRM6P31HknyAnvGHXHxsLiJFVnAiDndEYrPrDsSBaACLCg30OvL8WumFbcrD3itbbgIWYL1tZv8C4Yar7KQLTNGmJA2b-GUccympAgqwwkMDU7uQcaxxEREwrSMmN-5Xi9pMi3fMH8Nam-vwFH1-9guBvHQ4Z5'
            },
            {
                id: 2,
                title: 'Marketing Digital 2.0',
                instructor: 'Ana Souza',
                price: 'R$ 19,90',
                rating: 4.0,
                badge: '',
                badgeColor: '',
                image: 'https://lh3.googleusercontent.com/aida-public/AB6AXuA9pQCW41XPfJ2Gi9zVF5fO3IG9Vms4S10xYOfvXdaEmdw3EV3PDIvfmVvULXd5t2WJM2yjSmW_TBBqPatC1VqAejmB4YBsaIM7cpZkQclzY7LWxyIItekwWNGH7-DREihuQMppYXmLxVI3_YjfzwSJ_SjFEzb0YgPCzAGcTB6VwmJADY5MoVFW6n8LJpvBv-17u1mrQyOnVMo73A4bEUNgc96_IaM4D7b1LmTF3cgaWDmA5j98UwBilobz99cphtKTs7HZhv3tr2w9'
            },
            {
                id: 3,
                title: 'UX/UI Design Masterclass',
                instructor: 'Roberto Lima',
                price: 'R$ 39,90',
                rating: 5.0,
                badge: 'Novo',
                badgeColor: '#3b82f6',
                image: 'https://lh3.googleusercontent.com/aida-public/AB6AXuCaZZSLTqIA2YbyG1pTC36lpBiI_fZPJYOmocLVHfqtyDX6gi2i4pjk1i4CuZIKJ9p003TaPp5z4WeLTlnXD6qguo8j8jMnK0gioF-3Ear4fSLaPL-kqrDmJHYu2eKwA4QvOKEwbWUGjZGSpMv1468BaeqjYQMk57Gn1Secs88V6BNhvd1kPg1t-MzC7VhwSrmLKjrl3y1W_X1XDJPQxzJkIW4ms4YW2rr0WhcORk9g5NCAfhaFgXAz48nVkve4e0iq6k_TUIV4lujS'
            },
            {
                id: 4,
                title: 'Data Science com Python',
                instructor: 'Julia Mendes',
                price: 'R$ 49,90',
                rating: 4.7,
                badge: '',
                badgeColor: '',
                image: 'https://lh3.googleusercontent.com/aida-public/AB6AXuANc5QDhDMBn3twtZetU0mVVlQr1WG77gknGocP6ERD_k2v0Jqft6B0mXjxrnwL8Ivs_2IJSOj3xCMc-VQKis9hdOyVqO-d_KNx4GAME7pTJC3uyV4NECWFHaSkxk9wVmu-8FsCFTO6bcDhar5JCmCAr866MJ1uCdPcnUBxK-0qTg-fFntBTtZ7_oDmS4dtlkjzPW9OT2OFMR2QGDEcaWi1cYVY6Q5hEpSNtJZNZq5Itw54ohLqGfHiPk2cHQcFXLwr2YqWCo9u4_rt'
            }
        ]
    }
})

// eslint-disable-next-line no-unused-vars
const emit = defineEmits(['view-all', 'course-click', 'details-click'])
</script>

<style scoped>
.main {
    background-color: white;
    width: 100%;
}

.courses {
    padding: 4rem 0;
    width: 70%;
    margin: auto;
}

.courses-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 2.5rem;
}

.view-all {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    color: #0d7ff2;
    text-decoration: none;
    font-weight: 600;
    font-size: 0.875rem;
    transition: gap 0.3s;
    cursor: pointer;
}

.view-all:hover {
    gap: 0.75rem;
}

.courses-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1.5rem;
}

.course-card {
    background-color: white;
    border: 1px solid #e2e8f0;
    border-radius: 1rem;
    overflow: hidden;
    transition: all 0.3s;
    display: flex;
    flex-direction: column;
    cursor: pointer;
}

.course-card:hover {
    box-shadow: 0 10px 40px rgba(0, 0, 0, 0.15);
    transform: translateY(-4px);
}

.course-image {
    position: relative;
    width: 100%;
    aspect-ratio: 16 / 9;
    overflow: hidden;
    background-color: #f1f5f9;
}

.course-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.5s;
}

.course-card:hover .course-image img {
    transform: scale(1.05);
}

.course-badge {
    position: absolute;
    top: 0.5rem;
    left: 0.5rem;
    padding: 0.25rem 0.75rem;
    border-radius: 6px;
    color: white;
    font-size: 0.75rem;
    font-weight: 700;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
}

.course-content {
    padding: 1rem;
    display: flex;
    flex-direction: column;
    flex: 1;
}

.course-rating {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    margin-bottom: 0.5rem;
}

.stars {
    display: flex;
    color: #fbbf24;
    font-size: 1rem;
}

.rating-text {
    font-size: 0.75rem;
    color: #64748b;
    font-weight: 500;
}

.course-title {
    font-size: 1.125rem;
    font-weight: 700;
    color: #0f172a;
    margin-bottom: 0.25rem;
    line-height: 1.3;
}

.course-instructor {
    font-size: 0.875rem;
    color: #64748b;
    margin-bottom: 1rem;
}

.course-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: auto;
}

.course-price {
    font-size: 1.125rem;
    font-weight: 700;
    color: #10b981;
}

.btn-details {
    padding: 0.375rem 0.75rem;
    background-color: rgba(13, 127, 242, 0.1);
    color: #0d7ff2;
    border: none;
    border-radius: 6px;
    font-size: 0.875rem;
    font-weight: 700;
    cursor: pointer;
    transition: all 0.3s;
}

.btn-details:hover {
    background-color: #0d7ff2;
    color: white;
}

/* Responsive Design */
@media (max-width: 1024px) {
    .courses-grid {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 768px) {
    .courses-grid {
        grid-template-columns: 1fr;
    }

    .courses-header {
        flex-direction: column;
        align-items: flex-start;
        gap: 1rem;
    }

    .section-title {
        font-size: 1.75rem;
    }
}
</style>