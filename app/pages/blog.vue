<script setup>
const posts = [
    {
        title: 'Vue.js শেখার সেরা উপায়',
        excerpt: 'Vue.js দিয়ে আধুনিক ও দ্রুত ওয়েব অ্যাপ্লিকেশন তৈরি করার গাইড।',
        image: '/blog/01.jpg',
        category: 'ওয়েব ডেভেলপমেন্ট'
    },
    {
        title: 'ফ্রিল্যান্সিং শুরু করার আগে যা জানা জরুরি',
        excerpt: 'নতুনদের জন্য ফ্রিল্যান্সিং ক্যারিয়ার গড়ার গুরুত্বপূর্ণ টিপস।',
        image: '/blog/02.jpg',
        category: 'ক্যারিয়ার'
    },
    {
        title: 'গ্রাফিক ডিজাইনের ভবিষ্যৎ',
        excerpt: 'AI যুগে ডিজাইনারদের জন্য নতুন সুযোগ ও চ্যালেঞ্জ।',
        image: '/blog/03.jpg',
        category: 'ডিজাইন'
    }
]
</script>

<template>
    <main class="bg-slate-50">

        <section class="bg-gradient-to-r from-blue-600 to-indigo-500 text-white">
            <div class="container mx-auto px-6 lg:px-10 py-12">
                <h1 class="text-4xl font-bold">ব্লগ</h1>

                <nav class="mt-3 flex items-center gap-2 text-sm text-white/80">
                    <NuxtLink to="/">হোম</NuxtLink>
                    <UIcon name="i-lucide-chevron-right" class="size-4" />
                    <span>ব্লগ</span>
                </nav>
            </div>
        </section>

        <section class="container mx-auto px-6 lg:px-10 py-16">

            <div class="mb-10 flex items-center justify-between">
                <h2 class="text-3xl font-bold text-title">
                    সর্বশেষ প্রকাশিত ব্লগ
                </h2>

                <button class="rounded-xl border border-gray-200 px-4 py-2 text-sm font-medium hover:bg-white">
                    সব দেখুন
                </button>
            </div>

            <div class="grid gap-8 md:grid-cols-2 xl:grid-cols-3">

                <article v-for="(post, index) in posts" :key="index"
                    class="overflow-hidden rounded-2xl bg-white border border-gray-100 transition duration-300 hover:-translate-y-1">
                    <img :src="post.image" :alt="post.title" class="h-56 w-full object-cover">
                    <div class="p-6">
                        <span
                            class="inline-flex rounded-full bg-slate-100 px-3 py-1 text-xs font-medium text-slate-700">
                            {{ post.category }}
                        </span>
                        <h3 class="mt-4 line-clamp-2 text-xl font-bold text-title">
                            {{ post.title }}
                        </h3>
                        <p class="mt-3 line-clamp-2 text-sm text-gray-600">
                            {{ post.excerpt }}
                        </p>
                        <button class="mt-5 inline-flex items-center gap-2 font-medium text-primary">
                            আরও পড়ুন
                            <UIcon name="i-lucide-arrow-right" class="size-4" />
                        </button>
                    </div>
                </article>
            </div>
        </section>

    </main>
</template>