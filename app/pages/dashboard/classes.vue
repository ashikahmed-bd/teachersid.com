<script setup>
const classes = [
  {
    title: "Mathematics Masterclass",
    tutor: "Armando Weber",
    image: "/listing/img-01.png",
    subject: "Mathematics",
    date: "Today",
    time: "10:00 AM - 11:00 AM",
    type: "Online",
    status: "Live",
    progress: 78,
  },
  {
    title: "English Communication",
    tutor: "Gwendolyn Parker",
    image: "/listing/img-02.png",
    subject: "English",
    date: "Tomorrow",
    time: "02:00 PM - 03:00 PM",
    type: "Online",
    status: "Upcoming",
    progress: 45,
  },
  {
    title: "Computer Science Basics",
    tutor: "Dwayne Garrett",
    image: "/listing/img-03.png",
    subject: "Computer Science",
    date: "Apr 29, 2026",
    time: "08:00 PM - 09:00 PM",
    type: "Home Tuition",
    status: "Scheduled",
    progress: 62,
  },
];

const stats = [
  { label: "Active Classes", value: "08", icon: "i-lucide-video" },
  { label: "Completed", value: "24", icon: "i-lucide-check-circle" },
  { label: "Hours Learned", value: "72h", icon: "i-lucide-clock" },
];
</script>

<template>
  <main class="max-w-5xl mx-auto px-4 py-6">
    <div
      class="mb-8 flex flex-col gap-4 sm:flex-row sm:items-center sm:justify-between"
    >
      <div>
        <h1 class="text-2xl font-bold text-gray-900 sm:text-3xl">My Classes</h1>
        <p class="mt-1 text-gray-500">
          Track your upcoming lessons and learning progress.
        </p>
      </div>

      <UButton size="xl" class="rounded-full">
        <UIcon name="i-lucide-search" class="mr-1 size-4" />
        Find New Class
      </UButton>
    </div>

    <!-- Stats -->
    <div class="mb-8 grid gap-4 sm:grid-cols-3">
      <div
        v-for="stat in stats"
        :key="stat.label"
        class="rounded-3xl bg-white p-5 shadow-sm ring-1 ring-gray-100"
      >
        <div class="flex items-center justify-between">
          <div>
            <p class="text-sm text-gray-500">{{ stat.label }}</p>
            <h3 class="mt-2 text-2xl font-bold text-gray-900">
              {{ stat.value }}
            </h3>
          </div>

          <div
            class="grid size-12 place-items-center rounded-2xl bg-primary/10 text-primary"
          >
            <UIcon :name="stat.icon" class="size-6" />
          </div>
        </div>
      </div>
    </div>

    <!-- Filter -->
    <div
      class="mb-6 flex flex-col gap-3 rounded-3xl bg-white p-4 shadow-sm ring-1 ring-gray-100 lg:flex-row lg:items-center"
    >
      <UInput
        icon="i-lucide-search"
        size="lg"
        placeholder="Search classes..."
        class="flex-1"
      />

      <USelect
        size="lg"
        placeholder="Status"
        :items="['All', 'Live', 'Upcoming', 'Scheduled', 'Completed']"
        class="lg:w-48"
      />

      <USelect
        size="lg"
        placeholder="Subject"
        :items="['All Subjects', 'Mathematics', 'English', 'Computer Science']"
        class="lg:w-56"
      />
    </div>

    <!-- Class Cards -->
    <div class="grid gap-5">
      <article
        v-for="item in classes"
        :key="item.title"
        class="overflow-hidden rounded-3xl bg-white p-5 shadow-sm ring-1 ring-gray-100 transition hover:-translate-y-1 hover:shadow-xl"
      >
        <div
          class="flex flex-col gap-5 lg:flex-row lg:items-center lg:justify-between"
        >
          <!-- Left -->
          <div class="flex gap-4">
            <img
              :src="item.image"
              :alt="item.tutor"
              class="size-20 rounded-2xl object-cover"
            />

            <div>
              <div class="mb-2 flex flex-wrap items-center gap-2">
                <UBadge
                  :color="item.status === 'Live' ? 'success' : 'primary'"
                  variant="soft"
                  class="rounded-full"
                >
                  {{ item.status }}
                </UBadge>

                <UBadge color="neutral" variant="soft" class="rounded-full">
                  {{ item.type }}
                </UBadge>
              </div>

              <h3 class="text-lg font-bold text-gray-900">
                {{ item.title }}
              </h3>

              <p class="mt-1 text-sm text-gray-500">Tutor: {{ item.tutor }}</p>

              <div class="mt-3 flex flex-wrap gap-4 text-sm text-gray-500">
                <span class="flex items-center gap-1">
                  <UIcon name="i-lucide-book-open" class="size-4" />
                  {{ item.subject }}
                </span>

                <span class="flex items-center gap-1">
                  <UIcon name="i-lucide-calendar" class="size-4" />
                  {{ item.date }}
                </span>

                <span class="flex items-center gap-1">
                  <UIcon name="i-lucide-clock" class="size-4" />
                  {{ item.time }}
                </span>
              </div>
            </div>
          </div>

          <!-- Right -->
          <div class="w-full lg:w-56">
            <div class="mb-2 flex items-center justify-between text-sm">
              <span class="text-gray-500">Progress</span>
              <span class="font-semibold text-gray-900"
                >{{ item.progress }}%</span
              >
            </div>

            <div class="h-2 overflow-hidden rounded-full bg-gray-100">
              <div
                class="h-full rounded-full bg-primary"
                :style="{ width: `${item.progress}%` }"
              ></div>
            </div>

            <div class="mt-4 flex gap-2">
              <UButton v-if="item.status === 'Live'" block class="rounded-full">
                Join Now
              </UButton>

              <UButton v-else block variant="soft" class="rounded-full">
                View Details
              </UButton>

              <UButton
                icon="i-lucide-message-circle"
                color="neutral"
                variant="soft"
                class="rounded-full"
              />
            </div>
          </div>
        </div>
      </article>
    </div>
  </main>
</template>
