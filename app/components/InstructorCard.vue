<script setup>
defineProps({
  instructor: {
    type: Object,
    default: () => ({}),
  },
});
</script>

<template>
  <article>
    <div class="bg-white rounded-3xl transition overflow-hidden border border-gray-100 hover:shadow-lg">
      <div class="relative">
        <img :src="instructor.image" :alt="instructor.name" class="w-full h-52 object-cover" />

        <span class="absolute top-3 left-3 bg-primary text-white text-xs px-3 py-1 rounded-full font-semibold">
          বিশেষ প্রশিক্ষক
        </span>
      </div>

      <div class="p-5">
        <div class="flex flex-col gap-4">
          <div class="space-y-2 text-sm text-gray-600">
            <div class="flex justify-between">
              <span>বিশেষজ্ঞতা:</span>
              <span class="font-medium text-gray-900">
                {{ instructor.specialty || 'ওয়েব ডেভেলপমেন্ট' }}
              </span>
            </div>

            <div class="flex justify-between">
              <span>অভিজ্ঞতা:</span>
              <span class="font-medium">
                {{ instructor.experience || '৫+ বছর' }}
              </span>
            </div>

            <div class="flex justify-between">
              <span>শিক্ষার্থী:</span>
              <span class="font-medium">
                {{ instructor.students || '১,২০০+' }}
              </span>
            </div>

            <div class="flex justify-between">
              <span>কোর্স সংখ্যা:</span>
              <span class="font-medium">
                {{ instructor.courses || '১৫+' }}
              </span>
            </div>
          </div>

          <!-- Footer -->
          <div class="flex items-center justify-between pt-4 border-t border-gray-100">
            <div class="flex items-center gap-2">
              <div class="flex items-center gap-1 text-yellow-500">
                <UIcon name="i-lucide-star" class="size-4 fill-current" />
                <span class="text-sm font-semibold text-gray-900">
                  {{ instructor.rating || '৫.০' }}
                </span>
              </div>

              <span class="text-sm text-gray-500">
                ({{ instructor.reviews || '১,২৫০' }} রিভিউ)
              </span>
            </div>

            <button
              class="flex items-center justify-center w-9 h-9 rounded-full border border-gray-200 text-gray-600 hover:bg-gray-50 hover:text-red-500 transition">
              <UIcon name="i-lucide-heart" class="size-4" />
            </button>
          </div>
        </div>
      </div>
    </div>
  </article>
</template>