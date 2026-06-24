<script setup>
const categories = [
    "সকল কোর্স",
    "ওয়েব ডেভেলপমেন্ট",
    "অ্যাপ ডেভেলপমেন্ট",
    "ডিজিটাল মার্কেটিং",
    "গ্রাফিক ডিজাইন",
    "UI/UX ডিজাইন",
]

const courses = [
    {
        id: 1,
        title: "Complete Laravel Development",
        instructor: "রাকিবুল ইসলাম",
        image: "https://images.unsplash.com/photo-1516321318423-f06f85e504b3?w=1200",
        price: "৳১,৯৯৯",
        rating: 4.9,
        students: "২.৫k+",
    },
    {
        id: 2,
        title: "Modern Vue.js & Nuxt 4",
        instructor: "সাবরিনা আক্তার",
        image: "https://images.unsplash.com/photo-1498050108023-c5249f4df085?w=1200",
        price: "৳২,৪৯৯",
        rating: 4.8,
        students: "১.৮k+",
    },
    {
        id: 3,
        title: "Digital Marketing Masterclass",
        instructor: "মেহেদী হাসান",
        image: "https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=1200",
        price: "৳১,৪৯৯",
        rating: 4.7,
        students: "৩k+",
    },
    {
        id: 4,
        title: "UI/UX Design From Scratch",
        instructor: "তানজিনা রহমান",
        image: "https://images.unsplash.com/photo-1559028012-481c04fa702d?w=1200",
        price: "৳১,৭৯৯",
        rating: 4.9,
        students: "১.২k+",
    },
]
</script>

<template>
    <div class="bg-slate-50">
        <section class="relative overflow-hidden bg-slate-950 py-24">
            <div class="absolute inset-0">
                <div class="absolute -top-40 -left-40 h-96 w-96 rounded-full bg-blue-600/30 blur-3xl"></div>
                <div class="absolute top-20 -right-40 h-96 w-96 rounded-full bg-cyan-500/20 blur-3xl"></div>
            </div>

            <div class="relative container mx-auto px-6 lg:px-10">
                <div class="max-w-3xl">

                    <span
                        class="inline-flex items-center gap-2 rounded-full border border-white/10 bg-white/5 px-4 py-2 text-sm text-blue-200 backdrop-blur">
                        🚀 ১,০০০+ প্রিমিয়াম কোর্স
                    </span>

                    <h1 class="mt-6 text-3xl font-extrabold leading-tight text-white lg:text-5xl">
                        আপনার পছন্দের
                        <span
                            class="bg-gradient-to-r from-cyan-400 via-blue-400 to-indigo-400 bg-clip-text text-transparent">
                            সেরা কোর্স
                        </span>
                        খুঁজে নিন
                    </h1>

                    <p class="mt-6 text-lg leading-relaxed text-slate-300">
                        ইন্ডাস্ট্রি এক্সপার্টদের কাছ থেকে প্র্যাকটিক্যাল স্কিল শিখুন এবং
                        আপনার ক্যারিয়ারকে নতুন উচ্চতায় নিয়ে যান।
                    </p>

                    <div class="mt-10">
                        <div
                            class="flex items-center gap-2 rounded-2xl border border-white/10 bg-white/5 p-2 backdrop-blur-lg shadow-lg">

                            <UIcon name="i-lucide-search" class="ml-3 size-5 text-slate-400" />

                            <input type="text" placeholder="আপনি কোন কোর্স খুঁজছেন?"
                                class="w-full bg-transparent px-2 py-3 text-white placeholder:text-slate-400 outline-none" />

                            <button
                                class="rounded-xl bg-gradient-to-r from-cyan-500 to-blue-600 px-6 py-3 font-semibold text-white hover:opacity-90 transition">
                                খুঁজুন
                            </button>

                        </div>

                        <div class="mt-4 flex flex-wrap gap-2">
                            <button
                                class="rounded-full border border-white/10 bg-white/5 px-3 py-1 text-xs text-slate-300 hover:bg-white/10">
                                প্রোগ্রামিং
                            </button>

                            <button
                                class="rounded-full border border-white/10 bg-white/5 px-3 py-1 text-xs text-slate-300 hover:bg-white/10">
                                গণিত
                            </button>

                            <button
                                class="rounded-full border border-white/10 bg-white/5 px-3 py-1 text-xs text-slate-300 hover:bg-white/10">
                                ইংরেজি
                            </button>
                        </div>

                    </div>
                </div>
            </div>
        </section>

        <section class="container mx-auto px-6 lg:px-10 py-10">
            <div class="flex gap-3 overflow-x-auto pb-2">
                <button v-for="category in categories" :key="category"
                    class="whitespace-nowrap rounded-full border border-slate-200 bg-white px-5 py-3 text-sm font-medium transition hover:border-primary hover:text-primary">
                    {{ category }}
                </button>
            </div>
        </section>

        <section class="container mx-auto px-6 lg:px-10 pb-20">
            <div class="grid gap-8 lg:grid-cols-12">
                <aside class="lg:col-span-3">
                    <div class="sticky top-24 rounded-xl bg-white border border-gray-100 p-6">
                        <div class="flex items-center justify-between">
                            <h3 class="text-lg font-bold text-gray-900">ফিল্টার</h3>

                            <button class="text-sm text-primary hover:underline">
                                রিসেট
                            </button>
                        </div>

                        <div class="mt-6">
                            <h4 class="text-sm font-semibold text-gray-700 mb-3">দাম</h4>
                            <div class="space-y-2">
                                <label
                                    class="flex items-center justify-between rounded-xl border border-gray-100 px-3 py-2 hover:bg-gray-50 cursor-pointer">
                                    <span class="text-sm text-gray-700">ফ্রি কোর্স</span>
                                    <input type="checkbox" class="accent-primary w-4 h-4">
                                </label>

                                <label
                                    class="flex items-center justify-between rounded-xl border border-gray-100 px-3 py-2 hover:bg-gray-50 cursor-pointer">
                                    <span class="text-sm text-gray-700">পেইড কোর্স</span>
                                    <input type="checkbox" class="accent-primary w-4 h-4">
                                </label>
                            </div>
                        </div>

                        <div class="mt-8">
                            <h4 class="text-sm font-semibold text-gray-700 mb-3">রেটিং</h4>
                            <div class="space-y-2">
                                <label
                                    class="flex items-center justify-between rounded-xl border border-gray-100 px-3 py-2 hover:bg-gray-50 cursor-pointer">
                                    <span class="text-sm text-gray-700">৪.৫+ রেটিং</span>
                                    <input type="checkbox" class="accent-primary w-4 h-4">
                                </label>

                                <label
                                    class="flex items-center justify-between rounded-xl border border-gray-100 px-3 py-2 hover:bg-gray-50 cursor-pointer">
                                    <span class="text-sm text-gray-700">৪.০+ রেটিং</span>
                                    <input type="checkbox" class="accent-primary w-4 h-4">
                                </label>
                            </div>
                        </div>

                        <div class="mt-8">
                            <h4 class="text-sm font-semibold text-gray-700 mb-3">টপ ক্যাটাগরি</h4>

                            <div class="flex flex-wrap gap-2">
                                <button
                                    class="px-3 py-1.5 text-sm rounded-full border border-gray-200 hover:border-primary hover:text-primary transition">
                                    গণিত
                                </button>

                                <button
                                    class="px-3 py-1.5 text-sm rounded-full border border-gray-200 hover:border-primary hover:text-primary transition">
                                    ইংরেজি
                                </button>

                                <button
                                    class="px-3 py-1.5 text-sm rounded-full border border-gray-200 hover:border-primary hover:text-primary transition">
                                    প্রোগ্রামিং
                                </button>
                            </div>
                        </div>
                    </div>
                </aside>

                <div class="lg:col-span-9">
                    <div class="mb-6 flex items-center justify-between">
                        <h2 class="text-2xl font-bold">
                            জনপ্রিয় কোর্সসমূহ
                        </h2>

                        <select class="rounded-xl border border-slate-200 bg-white px-4 py-2">
                            <option>সর্বশেষ</option>
                            <option>সর্বাধিক বিক্রিত</option>
                            <option>সর্বোচ্চ রেটিং</option>
                        </select>
                    </div>

                    <div class="grid gap-6 md:grid-cols-2 xl:grid-cols-3">
                        <CourseCard v-for="course in courses" :course="course" />
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>