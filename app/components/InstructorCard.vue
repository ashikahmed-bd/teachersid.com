<script setup>
const props = defineProps({
  instructor: {
    type: Object,
    default: () => ({}),
  },
});
</script>

<template>
  <article>
    <div
      class="bg-white rounded-3xl transition overflow-hidden border border-gray-100"
    >
      <div class="relative">
        <img :src="instructor.image" class="w-full h-52 object-cover" />

        <span
          class="absolute top-3 left-3 bg-primary text-white text-xs px-3 py-1 rounded-full font-semibold"
        >
          FEATURED
        </span>
      </div>

      <div class="p-5">
        <div class="flex flex-col gap-4">
          <!-- Top Profile -->
          <div class="flex items-center gap-3">
            <img
              :src="instructor.avatar"
              alt="author"
              class="w-12 h-12 rounded-full object-cover"
            />

            <div>
              <h5
                class="flex items-center gap-1 text-base font-semibold text-gray-900"
              >
                <NuxtLink to="/tutor-detail" class="hover:text-primary">
                  Gwendolyn Parker
                </NuxtLink>

                <!-- Verified -->
                <UIcon
                  name="i-lucide-badge-check"
                  class="size-4 text-green-500"
                />
              </h5>

              <span class="text-sm text-gray-500"> Las Vegas, TN </span>
            </div>
          </div>

          <div class="space-y-2 text-base text-gray-600">
            <div class="flex justify-between">
              <span>Starting from:</span>
              <span class="font-semibold text-gray-900">$1,385.10/hr</span>
            </div>

            <div class="flex justify-between">
              <span>Mobile:</span>
              <span class="font-medium">xxx-xxxxx-11</span>
            </div>

            <div class="flex justify-between">
              <span>Whatsapp:</span>
              <span class="font-medium">xxx-xxxxx-80</span>
            </div>

            <div class="flex justify-between">
              <span>Qualification:</span>
              <span class="font-medium">B.Tech/B.E.</span>
            </div>
          </div>

          <div
            class="flex items-center justify-between pt-4 border-t border-gray-100"
          >
            <!-- Rating -->
            <div class="flex items-center gap-2">
              <div class="flex items-center gap-1 text-yellow-500">
                <UIcon name="i-lucide-star" class="size-4 fill-current" />
                <span class="text-sm font-semibold text-gray-900">5.0</span>
              </div>

              <span class="text-sm text-gray-500"> (38,494) </span>
            </div>

            <!-- Wishlist -->
            <button
              class="flex items-center justify-center w-9 h-9 rounded-full border border-gray-200 text-gray-600 hover:bg-gray-50 hover:text-red-500 transition"
            >
              <UIcon name="i-lucide-heart" class="size-4" />
            </button>
          </div>
        </div>
      </div>
    </div>
  </article>
</template>

<style scoped></style>
