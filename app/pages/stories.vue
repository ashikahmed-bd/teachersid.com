<script setup>
const stories = [
  {
    name: "Leonard Sullivan",
    role: "Student, Manchester UK",
    image: "/success_stories/img-01.jpg",
    result: "98%",
    subject: "Mathematics",
    title: "Improved grades with personalized online tutoring",
    text: "The tutor explained every concept clearly and helped me build confidence before exams.",
  },
  {
    name: "Deanna Griffin",
    role: "Parent, London UK",
    image: "/success_stories/img-02.jpg",
    result: "A+",
    subject: "Science",
    title: "A smooth learning experience for my child",
    text: "Flexible scheduling and friendly teaching made learning easier and more consistent.",
  },
  {
    name: "Bruce Mccarthy",
    role: "Student, Birmingham UK",
    image: "/success_stories/img-03.jpg",
    result: "95%",
    subject: "Physics",
    title: "From struggling to confident in just weeks",
    text: "Step-by-step guidance helped me understand difficult topics and prepare better.",
  },
  {
    name: "Evelyn Mccoy",
    role: "Student, Manchester UK",
    image: "/success_stories/img-04.jpg",
    result: "96%",
    subject: "English",
    title: "Better communication, better results",
    text: "My tutor helped me improve writing, speaking, and exam preparation.",
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
            Success Stories
          </UBadge>

          <h1
            class="text-4xl font-bold tracking-tight text-gray-900 sm:text-5xl"
          >
            Real students. Real progress. Real success.
          </h1>

          <p class="mt-5 text-base leading-7 text-gray-600 sm:text-lg">
            See how students and parents achieved better learning outcomes with
            expert tutors.
          </p>
        </div>
      </div>
    </section>

    <section class="-mt-8 relative z-10">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div
          class="grid gap-4 rounded-3xl bg-white p-5 sm:grid-cols-3 border border-border"
        >
          <div class="rounded-2xl bg-gray-50 p-5 text-center">
            <h3 class="text-3xl font-bold text-gray-900">20K+</h3>
            <p class="mt-1 text-sm text-gray-500">Happy students</p>
          </div>
          <div class="rounded-2xl bg-gray-50 p-5 text-center">
            <h3 class="text-3xl font-bold text-gray-900">98%</h3>
            <p class="mt-1 text-sm text-gray-500">Student satisfaction</p>
          </div>
          <div class="rounded-2xl bg-gray-50 p-5 text-center">
            <h3 class="text-3xl font-bold text-gray-900">4.9</h3>
            <p class="mt-1 text-sm text-gray-500">Average tutor rating</p>
          </div>
        </div>
      </div>
    </section>

    <section class="py-16 sm:py-20">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div
          class="mb-10 flex flex-col gap-4 sm:flex-row sm:items-end sm:justify-between"
        >
          <div>
            <h2 class="text-3xl font-bold text-gray-900">Featured stories</h2>
            <p class="mt-2 text-gray-600">
              Inspiring journeys from our learning community.
            </p>
          </div>

          <UButton variant="soft" color="primary" class="rounded-full">
            Share your story
            <UIcon name="i-lucide-arrow-right" class="ml-1 size-4" />
          </UButton>
        </div>

        <div class="grid gap-6 md:grid-cols-2">
          <article
            v-for="story in stories"
            :key="story.name"
            class="group overflow-hidden rounded-3xl bg-white border border-border transition hover:-translate-y-1 hover:border-primary"
          >
            <div class="grid md:grid-cols-[220px_1fr]">
              <div class="relative h-64 md:h-full">
                <img
                  :src="story.image"
                  :alt="story.name"
                  class="h-full w-full object-cover transition duration-500 group-hover:scale-105"
                />
                <div
                  class="absolute left-4 top-4 rounded-2xl bg-white/90 px-4 py-3 backdrop-blur"
                >
                  <h4 class="text-2xl font-bold text-primary">
                    {{ story.result }}
                  </h4>
                  <p class="text-xs font-semibold text-gray-600">
                    {{ story.subject }}
                  </p>
                </div>
              </div>

              <div class="p-6">
                <div class="mb-4 flex text-yellow-400">
                  <UIcon
                    v-for="i in 5"
                    :key="i"
                    name="i-lucide-star"
                    class="size-4 fill-current"
                  />
                </div>

                <h3 class="text-xl font-bold leading-snug text-gray-900">
                  {{ story.title }}
                </h3>

                <p class="mt-3 text-sm leading-7 text-gray-600">
                  “{{ story.text }}”
                </p>

                <div class="mt-6 border-t border-gray-100 pt-4">
                  <h4 class="font-bold text-gray-900">{{ story.name }}</h4>
                  <p class="text-sm text-gray-500">{{ story.role }}</p>
                </div>
              </div>
            </div>
          </article>
        </div>
      </div>
    </section>

    <!-- CTA -->
    <section class="pb-16 sm:pb-20">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div
          class="rounded-[2rem] bg-gray-950 p-8 text-white sm:p-10 lg:flex lg:items-center lg:justify-between"
        >
          <div>
            <h2 class="text-2xl font-bold sm:text-3xl">
              Ready to write your own success story?
            </h2>
            <p class="mt-3 max-w-2xl text-gray-400">
              Find an expert tutor and start learning with confidence today.
            </p>
          </div>

          <UButton size="xl" class="mt-6 rounded-full lg:mt-0">
            Find a tutor
          </UButton>
        </div>
      </div>
    </section>
  </main>
</template>
