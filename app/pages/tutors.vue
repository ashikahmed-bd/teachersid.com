<script setup>
const sortOptions = ["Price low to high", "Price high to low", "Top rated"];

const tags = [
  "Pre-School",
  "Middle (Class 6-8)",
  "Intermediate",
  "5.0 Stars",
  "Online bookings",
  "Male only",
];

const subjects = [
  "Social studies",
  "Urdu",
  "Mathematic",
  "English",
  "Drawing",
  "Computer science",
];

const tutors = [
  {
    name: "Mistie Monge",
    image: "/listing/img-01.png",
    location: "Phoenix, MN",
    price: "$712.93/hr",
  },
  {
    name: "Jamie Armstrong",
    image: "/listing/img-02.png",
    location: "New Orleans, OR",
    price: "$610.29/hr",
  },
  {
    name: "Nathaniel Fischer",
    image: "/listing/img-03.png",
    location: "San Francisco, ID",
    price: "$481.84/hr",
  },
  {
    name: "Bernard Keller",
    image: "/listing/img-04.png",
    location: "Austin, AZ",
    price: "$505.81/hr",
  },
];
</script>

<template>
  <main class="bg-gray-50 py-10">
    <div class="mx-auto max-w-7xl px-4">
      <div class="mb-6 rounded-3xl bg-white p-5 border border-border">
        <div
          class="flex flex-col gap-4 lg:flex-row lg:items-center lg:justify-between"
        >
          <h3 class="text-xl font-bold text-gray-900">
            132,576 Search results in
            <span class="text-primary">“Mathematic”</span>
            tutors
          </h3>

          <div class="flex flex-wrap items-center gap-3">
            <USelect
              :items="sortOptions"
              default-value="Price low to high"
              class="w-48"
            />

            <div class="flex items-center gap-2">
              <button
                class="grid size-9 place-items-center rounded-full bg-white text-primary"
              >
                <UIcon name="i-lucide-list" class="size-4" />
              </button>
              <button
                class="grid size-9 place-items-center rounded-full text-gray-500"
              >
                <UIcon name="i-lucide-grid-2x2" class="size-4" />
              </button>
            </div>
          </div>
        </div>

        <div class="mt-5 grid gap-3 lg:grid-cols-[1fr_260px_auto]">
          <UInput
            icon="i-lucide-search"
            size="xl"
            placeholder="What do you want to explore?"
          />

          <USelect
            size="xl"
            placeholder="Select category"
            :items="[
              'Automotive',
              'Beauty & Care',
              'Marketing',
              'Child Care',
              'House Cleaning',
            ]"
          />

          <UButton
            size="xl"
            color="primary"
            class="justify-center rounded-full px-7"
          >
            Search now
          </UButton>
        </div>

        <div class="mt-5 flex flex-wrap gap-2">
          <UBadge
            v-for="tag in tags"
            :key="tag"
            color="neutral"
            variant="soft"
            class="rounded-full px-3 py-1.5"
          >
            {{ tag }}
            <UIcon name="i-lucide-x" class="ml-1 size-3" />
          </UBadge>
        </div>
      </div>

      <div class="grid gap-6 xl:grid-cols-[300px_1fr]">
        <aside class="h-max rounded-3xl bg-white p-5 border border-border">
          <div class="flex items-center justify-between">
            <h4 class="text-lg font-bold text-gray-900">Filters</h4>
            <UButton variant="ghost" color="neutral" size="sm"> Clear </UButton>
          </div>

          <div class="mt-6 space-y-7">
            <div>
              <h5 class="mb-3 font-semibold text-gray-900">Education level</h5>
              <USelect
                placeholder="Select education level"
                :items="[
                  'Primary (Class 1-5)',
                  'Middle (Class 6-8)',
                  'Secondary (Class 9-10)',
                  'Language courses',
                  'Short courses',
                ]"
              />
            </div>

            <div>
              <h5 class="mb-3 font-semibold text-gray-900">Choose subjects</h5>
              <div class="space-y-3">
                <UCheckbox
                  v-for="subject in subjects"
                  :key="subject"
                  :label="subject"
                  :default-value="
                    [
                      'Social studies',
                      'Mathematic',
                      'Computer science',
                    ].includes(subject)
                  "
                />
              </div>
            </div>

            <div>
              <h5 class="mb-3 font-semibold text-gray-900">Price range</h5>
              <div class="grid grid-cols-2 gap-3">
                <UInput type="number" placeholder="Min price" />
                <UInput type="number" placeholder="Max price" />
              </div>
            </div>

            <div>
              <h5 class="mb-3 font-semibold text-gray-900">Rating</h5>
              <div class="space-y-3">
                <UCheckbox label="5.0 / 5.0" default-value />
                <UCheckbox label="4.0 / 5.0" />
                <UCheckbox label="3.0 / 5.0" default-value />
              </div>
            </div>

            <div>
              <h5 class="mb-3 font-semibold text-gray-900">Location</h5>
              <UInput icon="i-lucide-map-pin" placeholder="Enter location" />
            </div>

            <div>
              <h5 class="mb-3 font-semibold text-gray-900">Miscellaneous</h5>
              <div class="space-y-3">
                <UCheckbox label="Online bookings" default-value />
                <UCheckbox label="Profile photos" />
                <UCheckbox label="Male only" default-value />
                <UCheckbox label="Female only" />
              </div>
            </div>

            <UButton block size="lg" class="rounded-full">
              Apply filters
            </UButton>
          </div>
        </aside>

        <section class="space-y-5">
          <article
            v-for="tutor in tutors"
            :key="tutor.name"
            class="rounded-3xl bg-white p-5 border border-border hover:border-primary transition hover:-translate-y-1"
          >
            <div
              class="flex flex-col gap-5 lg:flex-row lg:items-start lg:justify-between"
            >
              <div class="flex gap-4">
                <img
                  :src="tutor.image"
                  :alt="tutor.name"
                  class="size-20 rounded-2xl object-cover"
                />

                <div>
                  <h5
                    class="flex items-center gap-1 text-lg font-bold text-gray-900"
                  >
                    <NuxtLink to="/tutor-detail" class="hover:text-primary">
                      {{ tutor.name }}
                    </NuxtLink>
                    <UIcon
                      name="i-lucide-badge-check"
                      class="size-4 text-green-500"
                    />
                  </h5>

                  <div
                    class="mt-2 flex flex-wrap items-center gap-3 text-sm text-gray-500"
                  >
                    <span class="flex items-center gap-1">
                      <UIcon
                        name="i-lucide-star"
                        class="size-4 fill-current text-yellow-400"
                      />
                      <strong class="text-gray-900">5.0</strong>
                      (4,448)
                    </span>

                    <span class="flex items-center gap-1">
                      <UIcon name="i-lucide-map-pin" class="size-4" />
                      {{ tutor.location }}
                    </span>
                  </div>
                </div>
              </div>

              <div class="lg:text-right">
                <span class="text-sm text-gray-500">Starting from:</span>
                <h4 class="text-2xl font-bold text-gray-900">
                  {{ tutor.price }}
                </h4>
              </div>
            </div>

            <p class="mt-5 text-sm leading-7 text-gray-600">
              Hello there! My name is Frederick and I'm currently a pre-medical
              student. I have a deep passion for teaching and I am looking for
              students to help them get ahead of school and ace their grades!
            </p>

            <div class="mt-5">
              <h6 class="mb-3 text-sm font-semibold text-gray-900">
                You can get teaching service direct at
              </h6>

              <div class="flex flex-wrap gap-2">
                <UBadge color="success" variant="soft" class="rounded-full">
                  <UIcon name="i-lucide-home" class="mr-1 size-4" />
                  My home
                </UBadge>
                <UBadge color="info" variant="soft" class="rounded-full">
                  <UIcon name="i-lucide-map-pin" class="mr-1 size-4" />
                  Student's home
                </UBadge>
                <UBadge color="warning" variant="soft" class="rounded-full">
                  <UIcon name="i-lucide-video" class="mr-1 size-4" />
                  Online
                </UBadge>
              </div>
            </div>

            <div
              class="mt-6 flex flex-col gap-3 border-t border-gray-100 pt-5 sm:flex-row sm:items-center sm:justify-between"
            >
              <button
                class="inline-flex items-center gap-2 text-sm font-semibold text-gray-500 hover:text-red-500"
              >
                <UIcon name="i-lucide-heart" class="size-5" />
                Add to save
              </button>

              <div class="flex gap-3">
                <UButton
                  variant="soft"
                  color="neutral"
                  size="xl"
                  class="rounded"
                >
                  Let’s chat
                </UButton>
                <UButton :to="`/tutor/ashikahmed`" size="xl" class="rounded">
                  View full profile
                </UButton>
              </div>
            </div>
          </article>

          <!-- Pagination -->
          <div class="flex justify-center pt-4">
            <UPagination :page="4" :total="600" :items-per-page="10" />
          </div>
        </section>
      </div>
    </div>
  </main>
</template>
