<script setup>
defineProps({
    course: {
        type: Object,
        default: () => ({})
    }
})
</script>

<template>
    <section class="rounded-3xl bg-gradient-to-br from-slate-950 via-slate-900 to-slate-950 p-8 text-white lg:p-12">
        <div class="flex flex-wrap gap-2">
            <UBadge color="primary">Best Seller</UBadge>
            <UBadge color="warning">Top Rated</UBadge>
        </div>

        <h1 class="mt-4 text-4xl font-bold lg:text-5xl">
            {{ course.title }}
        </h1>

        <p class="mt-4 max-w-4xl text-slate-300">
            {{ course.subtitle }}
        </p>

        <div class="mt-6 flex flex-wrap gap-6 text-sm">
            <span>⭐ {{ course.rating }}</span>
            <span>👨‍🎓 {{ course.students }}</span>
            <span>🕒 {{ course.updatedAt }}</span>
        </div>
    </section>
</template>