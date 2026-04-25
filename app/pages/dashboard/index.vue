<script setup>
const stats = [
  { label: "Active Classes", value: "08", icon: "i-lucide-video" },
  { label: "My Tutors", value: "12", icon: "i-lucide-users" },
  { label: "Upcoming Bookings", value: "05", icon: "i-lucide-calendar-check" },
  { label: "Unread Messages", value: "03", icon: "i-lucide-message-circle" },
];

const classes = [
  {
    title: "Mathematics Masterclass",
    tutor: "Armando Weber",
    time: "Today, 10:00 AM",
    status: "Live",
  },
  {
    title: "English Communication",
    tutor: "Gwendolyn Parker",
    time: "Tomorrow, 2:00 PM",
    status: "Upcoming",
  },
  {
    title: "Computer Science Basics",
    tutor: "Dwayne Garrett",
    time: "Apr 29, 8:00 PM",
    status: "Scheduled",
  },
];

const tutors = [
  {
    name: "Armando Weber",
    subject: "Mathematics",
    image: "https://i.pravatar.cc/100?img=12",
  },
  {
    name: "Gwendolyn Parker",
    subject: "English",
    image: "https://i.pravatar.cc/100?img=32",
  },
  {
    name: "Dwayne Garrett",
    subject: "Computer Science",
    image: "https://i.pravatar.cc/100?img=22",
  },
];
</script>

<template>
  <main class="max-w-6xl mx-auto px-4 py-6">
    <!-- Welcome -->
    <section
      class="mb-6 overflow-hidden rounded-[2rem] bg-gray-950 p-6 text-white sm:p-8"
    >
      <div
        class="flex flex-col gap-6 lg:flex-row lg:items-center lg:justify-between"
      >
        <div>
          <UBadge color="primary" variant="solid" class="mb-4 rounded-full">
            Student Dashboard
          </UBadge>

          <h1 class="text-3xl font-bold sm:text-4xl">Welcome back, John 👋</h1>

          <p class="mt-3 max-w-2xl text-sm leading-7 text-gray-400">
            Track your classes, manage bookings, message tutors, and continue
            your learning journey.
          </p>
        </div>

        <div class="flex flex-wrap gap-3">
          <UButton size="xl" class="rounded-full"> Find Tutor </UButton>

          <UButton
            size="xl"
            color="neutral"
            variant="soft"
            class="rounded-full"
          >
            Book Class
          </UButton>
        </div>
      </div>
    </section>

    <!-- Stats -->
    <section class="mb-6 grid gap-4 sm:grid-cols-2 lg:grid-cols-4">
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
    </section>

    <div class="grid gap-6 lg:grid-cols-[1fr_340px]">
      <!-- Left -->
      <div class="space-y-6">
        <!-- Upcoming Classes -->
        <section
          class="rounded-3xl bg-white p-5 shadow-sm ring-1 ring-gray-100"
        >
          <div class="mb-5 flex items-center justify-between">
            <div>
              <h2 class="text-lg font-bold text-gray-900">Upcoming Classes</h2>
              <p class="text-sm text-gray-500">Your next scheduled lessons.</p>
            </div>

            <UButton
              to="/dashboard/classes"
              variant="soft"
              size="sm"
              class="rounded-full"
            >
              View all
            </UButton>
          </div>

          <div class="space-y-3">
            <div
              v-for="item in classes"
              :key="item.title"
              class="flex flex-col gap-3 rounded-2xl bg-gray-50 p-4 sm:flex-row sm:items-center sm:justify-between"
            >
              <div>
                <h3 class="font-semibold text-gray-900">
                  {{ item.title }}
                </h3>
                <p class="mt-1 text-sm text-gray-500">
                  {{ item.tutor }} • {{ item.time }}
                </p>
              </div>

              <div class="flex items-center gap-2">
                <UBadge
                  :color="item.status === 'Live' ? 'success' : 'primary'"
                  variant="soft"
                  class="rounded-full"
                >
                  {{ item.status }}
                </UBadge>

                <UButton
                  v-if="item.status === 'Live'"
                  size="sm"
                  class="rounded-full"
                >
                  Join
                </UButton>
              </div>
            </div>
          </div>
        </section>
      </div>

      <aside class="space-y-6">
        <section
          class="rounded-3xl bg-white p-5 shadow-sm ring-1 ring-gray-100"
        >
          <div class="mb-5 flex items-center justify-between">
            <h2 class="text-lg font-bold text-gray-900">My Tutors</h2>

            <NuxtLink
              to="/dashboard/tutors"
              class="text-sm font-semibold text-primary"
            >
              View all
            </NuxtLink>
          </div>

          <div class="space-y-4">
            <div
              v-for="tutor in tutors"
              :key="tutor.name"
              class="flex items-center gap-3"
            >
              <img
                :src="tutor.image"
                :alt="tutor.name"
                class="size-11 rounded-full object-cover"
              />

              <div class="min-w-0 flex-1">
                <h3 class="truncate font-semibold text-gray-900">
                  {{ tutor.name }}
                </h3>
                <p class="text-sm text-gray-500">
                  {{ tutor.subject }}
                </p>
              </div>

              <UButton
                icon="i-lucide-message-circle"
                color="neutral"
                variant="soft"
                size="sm"
                class="rounded-full"
              />
            </div>
          </div>
        </section>

        <!-- Package -->
        <section class="rounded-3xl bg-primary p-5 text-white">
          <h2 class="text-lg font-bold">Upgrade your learning plan</h2>
          <p class="mt-2 text-sm leading-6 text-white/80">
            Unlock more tutor contacts, priority bookings, and premium support.
          </p>

          <UButton color="neutral" size="lg" class="mt-5 rounded-full">
            Upgrade Plan
          </UButton>
        </section>
      </aside>
    </div>
  </main>
</template>
