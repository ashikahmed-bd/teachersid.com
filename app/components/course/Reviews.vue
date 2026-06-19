<script setup>
defineProps({
    reviews: {
        type: Array,
        default: () => []
    }
})
</script>

<template>
    <UCard>
        <template #header>
            <h2 class="text-xl font-bold">
                Student Reviews
            </h2>
        </template>

        <div class="space-y-4">
            <div v-for="review in reviews" :key="review.name" class="rounded-xl border p-4">
                <h4 class="font-semibold">
                    {{ review.name }}
                </h4>

                <p class="text-yellow-500">
                    ⭐ {{ review.rating }}
                </p>

                <p class="mt-2">
                    {{ review.comment }}
                </p>
            </div>
        </div>
    </UCard>
</template>