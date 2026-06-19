<script setup>
const course = {
    id: 1,
    slug: 'master-laravel-nuxt-4-development',

    title: 'Master Laravel & Nuxt 4 Development',

    subtitle:
        'Become a job-ready full-stack developer by mastering Laravel 12 backend and Nuxt 4 frontend through real-world production projects.',

    description: `
This comprehensive course is designed to take you from beginner to advanced full-stack developer using modern technologies like Laravel 12 and Nuxt 4.

You will learn how to build scalable, secure, and production-ready web applications with a strong focus on real-world architecture, API design, authentication systems, and modern frontend development.

Instead of just theory, this course is fully project-based. You will build multiple real-world applications including a complete SaaS-style platform with authentication, payments, dashboard, and deployment.

By the end of this course, you will have the confidence and practical skills to build and deploy professional-grade web applications on your own or in a team environment.
  `.trim(),

    cover_url: '/courses/cover.webp',

    price: 2500,
    oldPrice: 5000,
    discount: 50,

    rating: 4.9,
    reviews: 1250,
    students: 8450,

    language: 'Bangla',
    updatedAt: 'June 2026',

    modules: 25,
    lectures: 180,
    hours: 35,
    quizzes: 12,
    assignments: 8,

    instructor: {
        name: 'Ashik Ahmed',
        title: 'Senior Full Stack Developer',
        avatar:
            'https://images.unsplash.com/photo-1500648767791-00dcc994a43e',
        bio: `
Ashik Ahmed is a Senior Full Stack Developer with over 8 years of experience building scalable web applications using Laravel, Vue.js, Nuxt, and modern cloud technologies.

He specializes in teaching practical, industry-focused development with real production workflows, CI/CD, and clean architecture principles. Thousands of students have learned full-stack development from his hands-on training approach.
    `.trim(),

        students: 8450,
        courses: 12,
        rating: 4.9,
    },

    learnings: [
        'Build REST APIs with Laravel 12 (Production Grade)',
        'Secure Authentication (JWT / Sanctum)',
        'Role-based Authorization System',
        'Nuxt 4 SSR & SPA Architecture',
        'Payment Gateway Integration (Stripe / Local)',
        'Database Design & Optimization Techniques',
        'File Upload, Storage & Media Handling',
        'Advanced Eloquent & Query Optimization',
        'Deploy Laravel + Nuxt to Production Server',
    ],
}

const curriculum = [
    {
        label: 'Module 1: Introduction',
        content: 'Welcome to the Course • Setup Development Environment',
    },
    {
        label: 'Module 2: Laravel 12 Basics',
        content: 'Routing • Controllers • Blade • Middleware',
    },
    {
        label: 'Module 3: Laravel Authentication',
        content: 'Laravel Breeze • Sanctum • Permissions',
    },
    {
        label: 'Module 4: Laravel API Development',
        content: 'Resources • Validation • API Design',
    },
    {
        label: 'Module 5: Nuxt 4 Fundamentals',
        content: 'Pages • Layouts • Components • SEO',
    },
]

const reviews = [
    {
        name: 'Rashidul Islam',
        rating: 5,
        comment:
            'Excellent course! Very well structured and easy to follow.',
    },
    {
        name: 'Mehedi Hasan',
        rating: 5,
        comment:
            'Best Laravel and Nuxt course in Bangla.',
    },
]

const faqs = [
    {
        label: 'Will I get lifetime access?',
        content:
            'Yes, you will get lifetime access after purchasing.',
    },
    {
        label: 'Do I get a certificate?',
        content:
            'Yes, certificate will be provided after completion.',
    },
    {
        label: 'Can I watch on mobile?',
        content:
            'Yes, course is available on mobile, tablet and desktop.',
    },
]

const related = [
    {
        title: 'Vue 3 & Laravel Full Stack',
        price: 2200,
        rating: 4.8,
    },
    {
        title: 'Complete React Developer',
        price: 2300,
        rating: 4.7,
    },
    {
        title: 'Node.js & Express Guide',
        price: 2000,
        rating: 4.6,
    },
]
</script>

<template>

    <main class="max-w-7xl mx-auto px-4 py-6">
        <div class="grid grid-cols-1 gap-8 lg:grid-cols-12">
            <div class="lg:col-span-8 space-y-8">
                <CourseHero :course="course" />
                <CourseStats :course="course" />
                <CourseLearnings :learnings="course.learnings" />

                <CourseTabs :curriculum="curriculum" :instructor="course.instructor" :reviews="reviews" :faqs="faqs">
                    <template #overview>
                        <CourseOverview :description="course.description" />
                    </template>
                </CourseTabs>

                <CourseRelated :courses="related" />
            </div>

            <aside class="lg:col-span-4">
                <div class="lg:sticky lg:top-24 space-y-4">
                    <CoursePurchaseCard :course="course" />
                </div>
            </aside>
        </div>
    </main>
</template>
