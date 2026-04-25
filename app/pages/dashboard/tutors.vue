<script setup>
const tutors = [
  {
    name: "Armando Weber",
    subject: "Mathematics",
    rating: 4.8,
    image: "https://i.pravatar.cc/100?img=1",
    status: "Active",
  },
  {
    name: "Gwendolyn Parker",
    subject: "English",
    rating: 5.0,
    image: "https://i.pravatar.cc/100?img=2",
    status: "Active",
  },
  {
    name: "Dwayne Garrett",
    subject: "Computer Science",
    rating: 4.7,
    image: "https://i.pravatar.cc/100?img=3",
    status: "Inactive",
  },
];
</script>

<template>
  <main class="max-w-5xl mx-auto px-4 py-6">
    <!-- Header -->
    <div
      class="flex flex-col sm:flex-row sm:items-center sm:justify-between gap-4 mb-6"
    >
      <div>
        <h1 class="text-2xl font-bold text-gray-900">My Tutors</h1>
        <p class="text-sm text-gray-500">Manage and connect with your tutors</p>
      </div>

      <UButton class="rounded-full">
        <UIcon name="i-lucide-search" class="mr-1 size-4" />
        Find Tutor
      </UButton>
    </div>

    <!-- Search -->
    <div class="mb-6">
      <UInput icon="i-lucide-search" placeholder="Search tutor..." size="lg" />
    </div>

    <!-- Tutors Grid -->
    <div class="grid gap-5 sm:grid-cols-2">
      <div
        v-for="tutor in tutors"
        :key="tutor.name"
        class="bg-white p-5 rounded-3xl shadow-sm ring-1 ring-gray-100 hover:shadow-lg transition"
      >
        <div class="flex items-center gap-4">
          <!-- Avatar -->
          <img :src="tutor.image" class="w-14 h-14 rounded-full object-cover" />

          <!-- Info -->
          <div class="flex-1">
            <h3 class="font-semibold text-gray-900 flex items-center gap-1">
              {{ tutor.name }}
              <UIcon
                name="i-lucide-badge-check"
                class="size-4 text-green-500"
              />
            </h3>

            <p class="text-sm text-gray-500">
              {{ tutor.subject }}
            </p>

            <!-- Rating -->
            <div class="flex items-center gap-1 mt-1 text-sm text-yellow-500">
              <UIcon name="i-lucide-star" class="size-4 fill-current" />
              {{ tutor.rating }}
            </div>
          </div>

          <!-- Status -->
          <UBadge
            :color="tutor.status === 'Active' ? 'success' : 'neutral'"
            variant="soft"
          >
            {{ tutor.status }}
          </UBadge>
        </div>

        <!-- Actions -->
        <div class="flex gap-2 mt-5">
          <UButton size="sm" class="rounded-full flex-1"> Message </UButton>

          <UButton size="sm" variant="soft" class="rounded-full flex-1">
            View Profile
          </UButton>

          <button
            class="w-9 h-9 flex items-center justify-center rounded-full border hover:text-red-500"
          >
            <UIcon name="i-lucide-heart" />
          </button>
        </div>
      </div>
    </div>
  </main>
</template>
