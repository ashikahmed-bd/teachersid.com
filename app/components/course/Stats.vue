<script setup>
defineProps({
    course: {
        type: Object,
        default: () => ({})
    }
})
</script>

<template>
    <div class="grid gap-4 grid-cols-2 lg:grid-cols-6">
        <UCard>
            <div class="text-center">
                <p class="text-2xl font-bold">
                    {{ course.modules }}
                </p>
                <p>Modules</p>
            </div>
        </UCard>

        <UCard>
            <div class="text-center">
                <p class="text-2xl font-bold">
                    {{ course.lectures }}
                </p>
                <p>Lectures</p>
            </div>
        </UCard>

        <UCard>
            <div class="text-center">
                <p class="text-2xl font-bold">
                    {{ course.hours }}
                </p>
                <p>Hours</p>
            </div>
        </UCard>

        <UCard>
            <div class="text-center">
                <p class="text-2xl font-bold">
                    {{ course.quizzes }}
                </p>
                <p>Quizzes</p>
            </div>
        </UCard>

        <UCard>
            <div class="text-center">
                <p class="text-2xl font-bold">
                    {{ course.assignments }}
                </p>
                <p>Assignments</p>
            </div>
        </UCard>

        <UCard>
            <div class="text-center">
                <p class="text-2xl font-bold">✓</p>
                <p>Certificate</p>
            </div>
        </UCard>
    </div>
</template>