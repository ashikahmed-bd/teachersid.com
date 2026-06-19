<script setup>
defineProps({
    instructor: {
        type: Object,
        default: () => ({})
    }
})
</script>

<template>
    <UCard>
        <div class="flex flex-col gap-5 md:flex-row">
            <UAvatar :src="instructor.avatar" size="3xl" />

            <div>
                <h3 class="text-xl font-bold">
                    {{ instructor.name }}
                </h3>

                <p class="text-slate-500">
                    {{ instructor.title }}
                </p>

                <p class="mt-4">
                    {{ instructor.bio }}
                </p>
            </div>
        </div>
    </UCard>
</template>