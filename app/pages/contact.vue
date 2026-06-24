<script setup>
const form = reactive({
    name: '',
    email: '',
    phone: '',
    subject: '',
    message: ''
})
</script>

<template>
    <main class="bg-slate-50">
        <section class="relative overflow-hidden bg-gradient-to-r from-blue-600 to-indigo-700 py-20">
            <div class="container mx-auto px-6 lg:px-10 relative z-10">
                <div class="max-w-3xl">
                    <h1 class="text-4xl lg:text-5xl font-bold text-white">
                        যোগাযোগ করুন
                    </h1>

                    <p class="mt-4 text-lg text-white/80">
                        যেকোনো প্রশ্ন, পরামর্শ বা সহযোগিতার জন্য আমাদের সাথে যোগাযোগ করুন।
                    </p>

                    <div class="mt-6 flex items-center gap-2 text-white/70">
                        <NuxtLink to="/">হোম</NuxtLink>
                        <UIcon name="i-lucide-chevron-right" class="size-4" />
                        <span>যোগাযোগ</span>
                    </div>
                </div>
            </div>
        </section>

        <section class="container mx-auto px-6 lg:px-10 py-20">
            <div class="grid gap-10 lg:grid-cols-5">
                <div class="lg:col-span-2 space-y-6">
                    <div class="rounded-3xl bg-white p-6 border border-border">
                        <div class="flex size-12 items-center justify-center rounded-xl bg-blue-100 text-blue-600">
                            <UIcon name="i-lucide-map-pin" class="size-6" />
                        </div>

                        <h3 class="mt-4 text-xl font-bold text-slate-900">
                            অফিস ঠিকানা
                        </h3>

                        <p class="mt-2 text-slate-600">
                            ঢাকা, বাংলাদেশ
                        </p>
                    </div>

                    <div class="rounded-3xl bg-white p-6 border border-border">
                        <div class="flex size-12 items-center justify-center rounded-xl bg-green-100 text-green-600">
                            <UIcon name="i-lucide-phone" class="size-6" />
                        </div>

                        <h3 class="mt-4 text-xl font-bold text-slate-900">
                            ফোন নম্বর
                        </h3>

                        <p class="mt-2 text-slate-600">
                            +880 1XXXXXXXXX
                        </p>
                    </div>

                    <div class="rounded-3xl bg-white p-6border border-border">
                        <div class="flex size-12 items-center justify-center rounded-xl bg-orange-100 text-orange-600">
                            <UIcon name="i-lucide-mail" class="size-6" />
                        </div>
                        <h3 class="mt-4 text-xl font-bold text-slate-900">
                            ইমেইল
                        </h3>
                        <p class="mt-2 text-slate-600">
                            support@example.com
                        </p>
                    </div>
                </div>

                <div class="lg:col-span-3">
                    <div class="rounded-3xl bg-white p-8 border border-border">
                        <div class="mb-8">
                            <h2 class="text-3xl font-bold text-slate-900">
                                আমাদের মেসেজ পাঠান
                            </h2>

                            <p class="mt-2 text-slate-600">
                                নিচের ফর্মটি পূরণ করুন, আমরা দ্রুত আপনার সাথে যোগাযোগ করবো।
                            </p>
                        </div>

                        <form class="space-y-6">

                            <div class="grid gap-6 md:grid-cols-2">

                                <div>
                                    <label class="mb-2 block text-sm font-medium">
                                        আপনার নাম
                                    </label>

                                    <input v-model="form.name" type="text"
                                        class="w-full rounded-xl border border-slate-200 px-4 py-3 outline-none focus:border-primary">
                                </div>

                                <div>
                                    <label class="mb-2 block text-sm font-medium">
                                        ফোন নম্বর
                                    </label>

                                    <input v-model="form.phone" type="text"
                                        class="w-full rounded-xl border border-slate-200 px-4 py-3 outline-none focus:border-primary">
                                </div>

                            </div>

                            <div>
                                <label class="mb-2 block text-sm font-medium">
                                    ইমেইল
                                </label>

                                <input v-model="form.email" type="email"
                                    class="w-full rounded-xl border border-slate-200 px-4 py-3 outline-none focus:border-primary">
                            </div>

                            <div>
                                <label class="mb-2 block text-sm font-medium">
                                    বিষয়
                                </label>

                                <input v-model="form.subject" type="text"
                                    class="w-full rounded-xl border border-slate-200 px-4 py-3 outline-none focus:border-primary">
                            </div>

                            <div>
                                <label class="mb-2 block text-sm font-medium">
                                    বার্তা
                                </label>

                                <textarea v-model="form.message" rows="6"
                                    class="w-full rounded-xl border border-slate-200 px-4 py-3 outline-none focus:border-primary resize-none"></textarea>
                            </div>

                            <button type="submit"
                                class="inline-flex items-center gap-2 rounded-xl bg-primary px-6 py-3 font-medium text-white transition hover:opacity-90">
                                মেসেজ পাঠান
                                <UIcon name="i-lucide-send" class="size-5" />
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </section>

        <!-- Map -->
        <section class="container mx-auto px-6 lg:px-10 pb-20">
            <div class="overflow-hidden rounded-3xl border border-slate-200 bg-white">
                <iframe class="h-[450px] w-full"
                    src="https://maps.google.com/maps?q=Dhaka&t=&z=13&ie=UTF8&iwloc=&output=embed" loading="lazy">
                </iframe>
            </div>
        </section>

    </main>
</template>