<script setup>
defineProps({
    course: {
        type: Object,
        default: () => ({})
    }
});

const enroll = (course) => {
    if (!course?.id || !course?.slug) return

    navigateTo(`/checkout/${course.slug}/${course.id}`)
}
</script>

<template>
    <div class="sticky top-24 p-4 border border-border rounded-xl">
        <img :src="course.cover_url" class="aspect-video w-full rounded-lg object-cover">

        <div class="mt-5 flex items-center gap-3">
            <span class="text-3xl font-bold">
                ৳{{ course.price }}
            </span>

            <span class="line-through text-slate-400">
                ৳{{ course.oldPrice }}
            </span>
        </div>

        <UButton block size="xl" class="mt-5" @click="enroll(course)">
            Enroll Now
        </UButton>

        <UButton block size="xl" variant="outline" class="mt-3">
            Add To Cart
        </UButton>


        <div class="space-y-4 text-sm mt-6">
            <div class="flex justify-between">
                <span>Language</span>
                <span>{{ course.language }}</span>
            </div>

            <div class="flex justify-between">
                <span>Lectures</span>
                <span>{{ course.lectures }}</span>
            </div>

            <div class="flex justify-between">
                <span>Duration</span>
                <span>{{ course.hours }}h</span>
            </div>
        </div>
    </div>
</template>