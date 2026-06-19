<script setup>
defineProps({
    curriculum: {
        type: Array,
        default: () => []
    }
})
</script>

<template>
    <UCard>
        <template #header>
            <h2 class="text-xl font-bold">
                Course Curriculum
            </h2>
        </template>

        <UAccordion :items="curriculum" />
    </UCard>
</template>