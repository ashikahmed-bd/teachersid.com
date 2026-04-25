<script setup>
const categories = [
  {
    title: "Mathematics",
    count: "6,301 Tutors",
    icon: "i-lucide-calculator",
    color: "bg-blue-50 text-blue-600",
  },
  {
    title: "Science",
    count: "4,892 Tutors",
    icon: "i-lucide-flask-conical",
    color: "bg-green-50 text-green-600",
  },
  {
    title: "English",
    count: "3,724 Tutors",
    icon: "i-lucide-book-open",
    color: "bg-purple-50 text-purple-600",
  },
  {
    title: "Computer Science",
    count: "5,210 Tutors",
    icon: "i-lucide-monitor",
    color: "bg-orange-50 text-orange-600",
  },
  {
    title: "Islamic Education",
    count: "2,157 Tutors",
    icon: "i-lucide-moon-star",
    color: "bg-emerald-50 text-emerald-600",
  },
  {
    title: "Music Learning",
    count: "1,830 Tutors",
    icon: "i-lucide-music",
    color: "bg-pink-50 text-pink-600",
  },
  {
    title: "Language Courses",
    count: "3,490 Tutors",
    icon: "i-lucide-languages",
    color: "bg-indigo-50 text-indigo-600",
  },
  {
    title: "Business Studies",
    count: "2,768 Tutors",
    icon: "i-lucide-briefcase-business",
    color: "bg-yellow-50 text-yellow-600",
  },
];
</script>

<template>
  <main class="bg-gray-50">
    <section class="relative overflow-hidden bg-white py-16 sm:py-20">
      <div
        class="absolute -top-24 right-0 size-72 rounded-full bg-primary/10 blur-3xl"
      ></div>
      <div
        class="absolute bottom-0 left-0 size-72 rounded-full bg-blue-100 blur-3xl"
      ></div>

      <div class="relative mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div class="mx-auto max-w-3xl text-center">
          <UBadge color="primary" variant="soft" class="mb-4 rounded-full">
            Explore Categories
          </UBadge>

          <h1
            class="text-4xl font-bold tracking-tight text-gray-900 sm:text-5xl"
          >
            Find the perfect tutor by category
          </h1>

          <p class="mt-5 text-base leading-7 text-gray-600 sm:text-lg">
            Browse top learning categories and connect with qualified tutors for
            online or home tuition.
          </p>

          <div class="mt-8 mx-auto max-w-2xl">
            <div class="flex rounded-full bg-white p-2 border border-border">
              <UInput
                icon="i-lucide-search"
                placeholder="Search category..."
                variant="none"
                class="flex-1"
              />
              <UButton class="rounded-full px-6"> Search </UButton>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="py-14 sm:py-16">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div
          class="mb-8 flex flex-col gap-4 sm:flex-row sm:items-end sm:justify-between"
        >
          <div>
            <h2 class="text-2xl font-bold text-gray-900 sm:text-3xl">
              Popular Categories
            </h2>
            <p class="mt-2 text-gray-600">
              Choose a subject and start learning today.
            </p>
          </div>

          <UButton variant="soft" color="primary" class="rounded-full">
            View all
            <UIcon name="i-lucide-arrow-right" class="ml-1 size-4" />
          </UButton>
        </div>

        <div class="grid gap-5 sm:grid-cols-2 lg:grid-cols-4">
          <NuxtLink
            v-for="category in categories"
            :key="category.title"
            to="/search"
            class="group rounded-xl bg-white p-6 border border-border hover:border-primary transition hover:-translate-y-1"
          >
            <div
              class="mb-5 grid size-14 place-items-center rounded-2xl"
              :class="category.color"
            >
              <UIcon :name="category.icon" class="size-7" />
            </div>

            <h3
              class="text-lg font-bold text-gray-900 group-hover:text-primary"
            >
              {{ category.title }}
            </h3>

            <p class="mt-1 text-sm text-gray-500">
              {{ category.count }}
            </p>

            <div
              class="mt-6 flex items-center justify-between border-t border-gray-100 pt-4"
            >
              <span class="text-sm font-semibold text-primary">
                Explore tutors
              </span>
              <span
                class="grid size-9 place-items-center rounded-full bg-gray-50 text-gray-500 transition group-hover:bg-primary group-hover:text-white"
              >
                <UIcon name="i-lucide-arrow-right" class="size-4" />
              </span>
            </div>
          </NuxtLink>
        </div>
      </div>
    </section>

    <section class="pb-16">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div
          class="rounded-xl bg-gray-950 p-8 text-white sm:p-10 lg:flex lg:items-center lg:justify-between"
        >
          <div>
            <h2 class="text-2xl font-bold sm:text-3xl">
              Can’t find your subject?
            </h2>
            <p class="mt-3 max-w-2xl text-gray-400">
              Tell us what you want to learn and we’ll help you find the right
              tutor.
            </p>
          </div>

          <UButton size="xl" class="mt-6 rounded-full lg:mt-0">
            Request a tutor
          </UButton>
        </div>
      </div>
    </section>
  </main>
</template>
