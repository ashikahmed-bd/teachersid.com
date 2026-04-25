<script setup>
const reviews = [
  {
    id: "#REV-1024",
    tutor: "Armando Weber",
    subject: "Mathematics",
    image: "https://i.pravatar.cc/100?img=12",
    rating: 5,
    date: "Apr 26, 2026",
    status: "Published",
    text: "Excellent tutor. He explains every topic clearly and makes difficult math problems easy to understand.",
  },
  {
    id: "#REV-1025",
    tutor: "Gwendolyn Parker",
    subject: "English",
    image: "https://i.pravatar.cc/100?img=32",
    rating: 4,
    date: "Apr 20, 2026",
    status: "Published",
    text: "Very friendly and helpful. My speaking confidence improved a lot after the sessions.",
  },
  {
    id: "#REV-1026",
    tutor: "Dwayne Garrett",
    subject: "Computer Science",
    image: "https://i.pravatar.cc/100?img=22",
    rating: 5,
    date: "Apr 12, 2026",
    status: "Pending",
    text: "Great teaching style and practical examples. I learned the basics very quickly.",
  },
];

const stats = [
  { label: "Total Reviews", value: "12", icon: "i-lucide-message-square-text" },
  { label: "Average Rating", value: "4.8", icon: "i-lucide-star" },
  { label: "Pending Reviews", value: "02", icon: "i-lucide-clock" },
];
</script>

<template>
  <main class="max-w-5xl mx-auto px-4 py-6">
    <div
      class="mb-6 flex flex-col gap-4 sm:flex-row sm:items-center sm:justify-between"
    >
      <div>
        <h1 class="text-2xl font-bold text-gray-900">Reviews</h1>
        <p class="text-sm text-gray-500">
          Manage your tutor reviews and feedback history.
        </p>
      </div>

      <UButton class="rounded-full">
        <UIcon name="i-lucide-plus" class="mr-1 size-4" />
        Add Review
      </UButton>
    </div>

    <div class="mb-6 grid gap-4 sm:grid-cols-3">
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

    <div
      class="mb-6 grid gap-3 rounded-3xl bg-white p-4 shadow-sm ring-1 ring-gray-100 md:grid-cols-[1fr_180px]"
    >
      <UInput
        icon="i-lucide-search"
        size="lg"
        placeholder="Search reviews..."
      />

      <USelect
        size="lg"
        placeholder="Status"
        :items="['All', 'Published', 'Pending']"
      />
    </div>

    <div class="space-y-4">
      <article
        v-for="review in reviews"
        :key="review.id"
        class="rounded-3xl bg-white p-5 shadow-sm ring-1 ring-gray-100 transition hover:-translate-y-1 hover:shadow-lg"
      >
        <div
          class="flex flex-col gap-5 sm:flex-row sm:items-start sm:justify-between"
        >
          <div class="flex gap-4">
            <img
              :src="review.image"
              :alt="review.tutor"
              class="size-14 rounded-2xl object-cover"
            />

            <div>
              <div class="mb-2 flex flex-wrap items-center gap-2">
                <UBadge color="neutral" variant="soft" class="rounded-full">
                  {{ review.id }}
                </UBadge>

                <UBadge
                  :color="review.status === 'Published' ? 'success' : 'warning'"
                  variant="soft"
                  class="rounded-full"
                >
                  {{ review.status }}
                </UBadge>
              </div>

              <h3 class="font-bold text-gray-900">
                {{ review.tutor }}
              </h3>

              <p class="text-sm text-gray-500">{{ review.subject }} Tutor</p>

              <div class="mt-3 flex items-center gap-1 text-yellow-400">
                <UIcon
                  v-for="i in review.rating"
                  :key="i"
                  name="i-lucide-star"
                  class="size-4 fill-current"
                />

                <UIcon
                  v-for="i in 5 - review.rating"
                  :key="`empty-${i}`"
                  name="i-lucide-star"
                  class="size-4 text-gray-300"
                />

                <span class="ml-2 text-sm text-gray-500">
                  {{ review.date }}
                </span>
              </div>
            </div>
          </div>

          <div class="flex gap-2">
            <UButton
              icon="i-lucide-pencil"
              size="sm"
              color="neutral"
              variant="soft"
              class="rounded-full"
            />

            <UButton
              icon="i-lucide-trash-2"
              size="sm"
              color="error"
              variant="soft"
              class="rounded-full"
            />
          </div>
        </div>

        <p
          class="mt-5 rounded-2xl bg-gray-50 p-4 text-sm leading-7 text-gray-600"
        >
          “{{ review.text }}”
        </p>
      </article>
    </div>
  </main>
</template>
