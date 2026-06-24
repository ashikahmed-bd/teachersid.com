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

            <img src="/courses/class-7-math.jpg" alt="৭ম শ্রেণির গণিত" class="w-full h-auto object-cover" />

            <div class="p-4">
                <h3 class="line-clamp-2 text-lg font-bold text-title">
                    ৭ম শ্রেণির গণিত সম্পূর্ণ কোর্স
                </h3>

                <p class="mt-2 text-sm text-gray-600 line-clamp-2">
                    অধ্যায়ভিত্তিক ভিডিও লেকচার, কুইজ, অ্যাসাইনমেন্ট এবং পরীক্ষার পূর্ণ প্রস্তুতি।
                </p>

                <div class="mt-4 flex items-center gap-4 text-sm text-gray-500">
                    <div class="flex items-center gap-1">
                        <UIcon name="i-lucide-play-circle" class="size-4" />
                        <span>৪৮টি লেসন</span>
                    </div>

                    <div class="flex items-center gap-1">
                        <UIcon name="i-lucide-clock-3" class="size-4" />
                        <span>৩২ ঘণ্টা</span>
                    </div>
                </div>

                <div class="flex items-center justify-between border-t border-gray-100 pt-4">
                    <span class="text-xl font-bold text-primary">
                        ৳১,৫০০
                    </span>

                    <div class="flex items-center gap-1">
                        <UIcon name="i-lucide-star" class="size-4 fill-current text-yellow-400" />
                        <span class="font-medium">৪.৯</span>
                        <span class="text-xs text-gray-500">(১,২৫০)</span>
                    </div>
                </div>
            </div>
        </article>
    </NuxtLink>
</template>
