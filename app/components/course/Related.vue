<script setup>
defineProps({
    courses: {
        type: Array,
        default: () => []
    }
})
</script>

<template>
    <div class="grid gap-6 md:grid-cols-2 lg:grid-cols-3">
        <CourseCard :course="course" v-for="course in courses" :key="course.title"/>
    </div>
</template>