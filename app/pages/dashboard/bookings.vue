<script setup>
const bookings = [
  {
    id: "#BK-1024",
    title: "Mathematics Lesson",
    tutor: "Armando Weber",
    image: "https://i.pravatar.cc/100?img=12",
    date: "Today",
    time: "10:00 AM - 11:00 AM",
    type: "Online",
    status: "Confirmed",
  },
  {
    id: "#BK-1025",
    title: "English Speaking Class",
    tutor: "Gwendolyn Parker",
    image: "https://i.pravatar.cc/100?img=32",
    date: "Tomorrow",
    time: "02:00 PM - 03:00 PM",
    type: "Home Tuition",
    status: "Pending",
  },
  {
    id: "#BK-1026",
    title: "Computer Science Basics",
    tutor: "Dwayne Garrett",
    image: "https://i.pravatar.cc/100?img=22",
    date: "Apr 29, 2026",
    time: "08:00 PM - 09:00 PM",
    type: "Online",
    status: "Completed",
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
        <h1 class="text-2xl font-bold text-gray-900">Bookings</h1>
        <p class="text-sm text-gray-500">
          Manage your class bookings and schedules.
        </p>
      </div>

      <UButton class="rounded-full">
        <UIcon name="i-lucide-plus" class="mr-1 size-4" />
        New Booking
      </UButton>
    </div>

    <!-- Stats -->
    <div class="mb-6 grid gap-4 sm:grid-cols-3">
      <div class="rounded-3xl bg-white p-5 shadow-sm ring-1 ring-gray-100">
        <p class="text-sm text-gray-500">Confirmed</p>
        <h3 class="mt-2 text-2xl font-bold text-gray-900">12</h3>
      </div>

      <div class="rounded-3xl bg-white p-5 shadow-sm ring-1 ring-gray-100">
        <p class="text-sm text-gray-500">Pending</p>
        <h3 class="mt-2 text-2xl font-bold text-gray-900">03</h3>
      </div>

      <div class="rounded-3xl bg-white p-5 shadow-sm ring-1 ring-gray-100">
        <p class="text-sm text-gray-500">Completed</p>
        <h3 class="mt-2 text-2xl font-bold text-gray-900">28</h3>
      </div>
    </div>

    <!-- Filters -->
    <div
      class="mb-6 grid gap-3 rounded-3xl bg-white p-4 shadow-sm ring-1 ring-gray-100 md:grid-cols-[1fr_180px_180px]"
    >
      <UInput
        icon="i-lucide-search"
        size="lg"
        placeholder="Search booking..."
      />

      <USelect
        size="lg"
        placeholder="Status"
        :items="['All', 'Confirmed', 'Pending', 'Completed', 'Cancelled']"
      />

      <USelect
        size="lg"
        placeholder="Type"
        :items="['All', 'Online', 'Home Tuition']"
      />
    </div>

    <!-- Booking List -->
    <div class="space-y-4">
      <article
        v-for="booking in bookings"
        :key="booking.id"
        class="rounded-3xl bg-white p-5 shadow-sm ring-1 ring-gray-100 transition hover:-translate-y-1 hover:shadow-lg"
      >
        <div
          class="flex flex-col gap-5 lg:flex-row lg:items-center lg:justify-between"
        >
          <div class="flex gap-4">
            <img
              :src="booking.image"
              :alt="booking.tutor"
              class="size-16 rounded-2xl object-cover"
            />

            <div>
              <div class="mb-2 flex flex-wrap items-center gap-2">
                <UBadge color="neutral" variant="soft" class="rounded-full">
                  {{ booking.id }}
                </UBadge>

                <UBadge
                  :color="
                    booking.status === 'Confirmed'
                      ? 'success'
                      : booking.status === 'Pending'
                        ? 'warning'
                        : 'neutral'
                  "
                  variant="soft"
                  class="rounded-full"
                >
                  {{ booking.status }}
                </UBadge>
              </div>

              <h3 class="text-lg font-bold text-gray-900">
                {{ booking.title }}
              </h3>

              <p class="mt-1 text-sm text-gray-500">
                Tutor: {{ booking.tutor }}
              </p>

              <div class="mt-3 flex flex-wrap gap-4 text-sm text-gray-500">
                <span class="flex items-center gap-1">
                  <UIcon name="i-lucide-calendar" class="size-4" />
                  {{ booking.date }}
                </span>

                <span class="flex items-center gap-1">
                  <UIcon name="i-lucide-clock" class="size-4" />
                  {{ booking.time }}
                </span>

                <span class="flex items-center gap-1">
                  <UIcon name="i-lucide-video" class="size-4" />
                  {{ booking.type }}
                </span>
              </div>
            </div>
          </div>

          <div class="flex flex-wrap gap-2">
            <UButton v-if="booking.status === 'Confirmed'" class="rounded-full">
              Join Class
            </UButton>

            <UButton
              v-if="booking.status === 'Pending'"
              color="neutral"
              variant="soft"
              class="rounded-full"
            >
              Waiting
            </UButton>

            <UButton variant="soft" color="primary" class="rounded-full">
              Details
            </UButton>

            <UButton
              icon="i-lucide-message-circle"
              color="neutral"
              variant="soft"
              class="rounded-full"
            />
          </div>
        </div>
      </article>
    </div>
  </main>
</template>
