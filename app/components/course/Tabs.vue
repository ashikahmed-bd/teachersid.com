<script setup>
defineProps({
    curriculum: {
        type: Array,
        default: () => []
    },
    instructor: {
        type: Object,
        default: () => ({})
    },
    reviews: {
        type: Array,
        default: () => []
    },
    faqs: {
        type: Array,
        default: () => []
    }
})
</script>

<template>
    <UTabs :items="[
        { label: 'Overview', slot: 'overview' },
        { label: 'Curriculum', slot: 'curriculum' },
        { label: 'Instructor', slot: 'instructor' },
        { label: 'Reviews', slot: 'reviews' },
        { label: 'FAQ', slot: 'faq' }
    ]">
        <template #overview>
            <slot name="overview" />
        </template>

        <template #curriculum>
            <CourseCurriculum :curriculum="curriculum" />
        </template>

        <template #instructor>
            <CourseInstructor :instructor="instructor" />
        </template>

        <template #reviews>
            <CourseReviews :reviews="reviews" />
        </template>

        <template #faq>
            <CourseFaq :faqs="faqs" />
        </template>
    </UTabs>
</template>