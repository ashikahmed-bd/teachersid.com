<script setup>
defineProps({
    course: {
        type: Object,
        required: true
    }
})
</script>

<template>
    <NuxtLink :to="`/courses/${course.slug}/${course.id}`">
        <article
            class="overflow-hidden rounded-xl bg-white border border-gray-100 transition duration-300 hover:-translate-y-1">

            <img src="/courses/class-7-math.jpg" alt="Class 7 Mathematics" class="w-full h-auto object-cover" />

            <div class="p-4">
                <h3 class="line-clamp-2 text-lg font-bold text-title">
                    Class 7 Mathematics Complete Course
                </h3>

                <p class="mt-2 text-sm text-gray-600 line-clamp-2">
                    Chapter-wise video lessons, quizzes, assignments and exam preparation.
                </p>

                <div class="mt-4 flex items-center gap-4 text-sm text-gray-500">
                    <div class="flex items-center gap-1">
                        <UIcon name="i-lucide-play-circle" class="size-4" />
                        <span>48 Lessons</span>
                    </div>

                    <div class="flex items-center gap-1">
                        <UIcon name="i-lucide-clock-3" class="size-4" />
                        <span>32 Hours</span>
                    </div>
                </div>

                <div class="flex items-center justify-between border-t border-gray-100 pt-4">
                    <span class="text-xl font-bold text-primary">
                        ৳1,500
                    </span>

                    <div class="flex items-center gap-1">
                        <UIcon name="i-lucide-star" class="size-4 fill-current text-yellow-400" />
                        <span class="font-medium">4.9</span>
                        <span class="text-xs text-gray-500">(1,250)</span>
                    </div>
                </div>
            </div>
        </article>
    </NuxtLink>
</template>
