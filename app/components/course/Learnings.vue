<script setup>
defineProps({
    learnings: {
        type: Array,
        default: () => []
    }
})
</script>

<template>
    <UCard>
        <template #header>
            <h2 class="text-xl font-bold">
                What You'll Learn
            </h2>
        </template>

        <div class="grid md:grid-cols-2">
            <div v-for="(item, index) in learnings" :key="index"
                class="flex items-start gap-2 rounded-lg p-2 hover:bg-gray-50 transition">
                <UIcon name="i-heroicons-check-circle-solid" class="size-5 shrink-0 text-primary" />
                <span class="text-sm leading-relaxed text-body">{{ item }}</span>
            </div>
        </div>
    </UCard>
</template>