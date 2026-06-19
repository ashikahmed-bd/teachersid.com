<script setup>
defineProps({
    teacher: {
        type: Object,
        required: true,
    },
})
</script>

<template>
    <div class="bg-white rounded-2xl overflow-hidden border border-gray-200 transition">
        <div class="relative p-4 bg-gradient-to-br from-blue-950 via-blue-900 to-blue-800 text-white">
            <span class="absolute top-3 left-3 bg-amber-400 text-blue-950 text-xs font-semibold px-3 py-1 rounded-full">
                প্রিমিয়াম শিক্ষক
            </span>

            <!-- Wishlist -->
            <button class="absolute top-3 right-3 text-white hover:text-red-300">
                <UIcon name="i-lucide-heart" class="size-5" />
            </button>

            <div class="flex items-center gap-4 pt-8">
                <img :src="teacher.image" :alt="teacher.name"
                    class="w-20 h-20 rounded-xl object-cover border-2 border-white/20">

                <div class="flex-1">
                    <h3 class="font-bold text-base">
                        {{ teacher.name }}
                    </h3>

                    <p class="text-sm text-blue-100">
                        {{ teacher.subject }}
                    </p>

                    <p class="text-sm font-medium truncate">
                        {{ teacher.qualification }}
                    </p>

                    <div class="flex items-center gap-4 text-sm">
                        <div class="flex items-center gap-1">
                            <UIcon name="i-lucide-star" class="size-4 text-yellow-400 fill-current" />
                            <span>{{ teacher.rating }}</span>
                            <span class="text-blue-200">
                                ({{ teacher.reviews }})
                            </span>
                        </div>
                        <div class="flex items-center gap-1">
                            <UIcon name="i-lucide-users" class="size-4" />
                            <span>{{ teacher.students }}</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="flex flex-wrap gap-2 px-4 py-2.5">
            <span v-for="badge in teacher.subjects" :key="badge"
                class="px-3 py-1 rounded-full bg-primary/10 text-primary text-xs font-medium">
                {{ badge }}
            </span>
        </div>

        <div class="p-4 flex items-center justify-between">
            <div class="block">
                <p class="text-xs text-gray-500">প্রতি ঘণ্টা</p>
                <p class="text-xl font-bold text-primary">৳ {{ teacher.price }}</p>
            </div>

            <NuxtLink :to="`/teachers/abu-toha`"
                class="text-sm px-4 py-2 rounded bg-primary text-white font-medium hover:opacity-90">
                প্রোফাইল দেখুন
            </NuxtLink>
        </div>
    </div>
</template>