<script setup>
const savedTutors = [
  {
    name: "Armando Weber",
    subject: "Mathematics Tutor",
    image: "https://i.pravatar.cc/120?img=12",
    location: "Sacramento, CA",
    rating: 4.8,
    reviews: "4,448",
    price: "$562.32/hr",
    status: "Available",
  },
  {
    name: "Gwendolyn Parker",
    subject: "English Tutor",
    image: "https://i.pravatar.cc/120?img=32",
    location: "Las Vegas, TN",
    rating: 5.0,
    reviews: "38,494",
    price: "$1,385.10/hr",
    status: "Busy",
  },
  {
    name: "Dwayne Garrett",
    subject: "Computer Science Tutor",
    image: "https://i.pravatar.cc/120?img=22",
    location: "Arlington, TN",
    rating: 4.7,
    reviews: "4,448",
    price: "$893.30/hr",
    status: "Available",
  },
];
</script>

<template>
  <main class="max-w-5xl mx-auto px-4 py-6">
    <!-- Header -->
    <div
      class="mb-6 flex flex-col gap-4 sm:flex-row sm:items-center sm:justify-between"
    >
      <div>
        <h1 class="text-2xl font-bold text-gray-900">Saved Tutors</h1>
        <p class="text-sm text-gray-500">
          Your favorite tutors saved for quick booking.
        </p>
      </div>

      <UButton class="rounded-full">
        <UIcon name="i-lucide-search" class="mr-1 size-4" />
        Find More Tutors
      </UButton>
    </div>

    <!-- Search / Filter -->
    <div
      class="mb-6 grid gap-3 rounded-3xl bg-white p-4 shadow-sm ring-1 ring-gray-100 md:grid-cols-[1fr_180px]"
    >
      <UInput
        icon="i-lucide-search"
        size="lg"
        placeholder="Search saved tutors..."
      />

      <USelect
        size="lg"
        placeholder="Availability"
        :items="['All', 'Available', 'Busy']"
      />
    </div>

    <!-- Tutors -->
    <div class="grid gap-5 sm:grid-cols-2 lg:grid-cols-3">
      <article
        v-for="tutor in savedTutors"
        :key="tutor.name"
        class="rounded-3xl bg-white p-5 shadow-sm ring-1 ring-gray-100 transition hover:-translate-y-1 hover:shadow-xl"
      >
        <div class="flex items-start justify-between gap-4">
          <div class="flex items-center gap-3">
            <div class="relative">
              <img
                :src="tutor.image"
                :alt="tutor.name"
                class="size-14 rounded-2xl object-cover"
              />
              <span
                class="absolute -bottom-1 -right-1 size-4 rounded-full border-2 border-white"
                :class="
                  tutor.status === 'Available'
                    ? 'bg-green-500'
                    : 'bg-yellow-400'
                "
              ></span>
            </div>

            <div>
              <h3 class="flex items-center gap-1 font-bold text-gray-900">
                {{ tutor.name }}
                <UIcon
                  name="i-lucide-badge-check"
                  class="size-4 text-green-500"
                />
              </h3>
              <p class="text-sm text-gray-500">{{ tutor.subject }}</p>
            </div>
          </div>

          <button
            class="grid size-9 place-items-center rounded-full bg-red-50 text-red-500 transition hover:bg-red-100"
          >
            <UIcon name="i-lucide-heart" class="size-4 fill-current" />
          </button>
        </div>

        <div class="mt-5 space-y-3 text-sm text-gray-600">
          <div class="flex items-center gap-2">
            <UIcon name="i-lucide-map-pin" class="size-4 text-gray-400" />
            {{ tutor.location }}
          </div>

          <div class="flex items-center gap-2">
            <UIcon
              name="i-lucide-star"
              class="size-4 fill-current text-yellow-400"
            />
            <span>
              <strong class="text-gray-900">{{ tutor.rating }}</strong>
              ({{ tutor.reviews }})
            </span>
          </div>

          <div
            class="flex items-center justify-between rounded-2xl bg-gray-50 px-4 py-3"
          >
            <span>Starting from</span>
            <strong class="text-gray-900">{{ tutor.price }}</strong>
          </div>
        </div>

        <div class="mt-5 grid grid-cols-2 gap-2">
          <UButton variant="soft" color="neutral" class="rounded-full">
            Message
          </UButton>

          <UButton class="rounded-full"> Book Now </UButton>
        </div>

        <UButton
          to="/tutor-detail"
          block
          variant="ghost"
          color="primary"
          class="mt-2 rounded-full"
        >
          View Profile
        </UButton>
      </article>
    </div>
  </main>
</template>
