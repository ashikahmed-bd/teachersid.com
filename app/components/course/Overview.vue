<script setup>
defineProps({
    description: {
        type: String,
        default: ''
    }
})
</script>

<template>
    <div class="space-y-6">
        <UCard>
            <template #header>
                <h2 class="text-xl font-bold">
                    Course Overview
                </h2>
            </template>

            <div v-html="description" class="prose max-w-none text-body">
            </div>
        </UCard>
    </div>
</template>
