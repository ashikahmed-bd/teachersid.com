<script setup>
defineProps({
    faqs: {
        type: Array,
        default: () => []
    }
})
</script>

<template>
    <UCard>
        <template #header>
            <h2 class="text-xl font-bold">
                Frequently Asked Questions
            </h2>
        </template>

        <UAccordion :items="faqs" />
    </UCard>
</template>