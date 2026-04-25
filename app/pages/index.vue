<script setup>
const brands = [
  "/brand/img-01.png",
  "/brand/img-02.png",
  "/brand/img-03.png",
  "/brand/img-04.png",
  "/brand/img-05.png",
  "/brand/img-06.png",
  "/brand/img-07.png",
];

const stats = [
  {
    icon: "/stats/img-01.png",
    value: 560616,
    suffix: "",
    label: "Courses available for verified and top tutors",
  },
  {
    icon: "/stats/img-02.png",
    value: 648482,
    suffix: "",
    label: "Total tuition job posted on the platform till date",
  },
  {
    icon: "/stats/img-03.png",
    value: 20,
    suffix: "+ Hours",
    label: "User daily average time spent on the platform",
  },
  {
    icon: "/stats/img-04.png",
    value: 7,
    suffix: "+ Million",
    label: "Active instructor and students available",
  },
];

const counters = ref(stats.map(() => 0));
const started = ref(false);

const animateCounter = () => {
  stats.forEach((stat, i) => {
    let start = 0;
    const end = stat.value;
    const duration = 2000;
    const stepTime = Math.abs(Math.floor(duration / end));

    const timer = setInterval(() => {
      start += Math.ceil(end / 50);
      if (start >= end) {
        counters.value[i] = end;
        clearInterval(timer);
      } else {
        counters.value[i] = start;
      }
    }, stepTime);
  });
};

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      if (entries[0].isIntersecting && !started.value) {
        animateCounter();
        started.value = true;
      }
    },
    { threshold: 0.3 },
  );

  const el = document.getElementById("counter-section");
  if (el) observer.observe(el);
});

const instructors = [
  {
    name: "Dwayne Garrett",
    location: "Arlington, TN",
    price: "$893.30/hr",
    rating: 5.0,
    reviews: "66,951",
    image: "/qualified/img-01.jpg",
    avatar: "/professionol/img-01.jpg",
  },
  {
    name: "Gwendolyn Parker",
    location: "Las Vegas, TN",
    price: "$1,385.10/hr",
    rating: 5.0,
    reviews: "38,494",
    image: "/qualified/img-02.jpg",
    avatar: "/professionol/img-02.jpg",
  },
  {
    name: "Glen Burns",
    location: "Chicago, OH",
    price: "$1,336.83/hr",
    rating: 5.0,
    reviews: "47,044",
    image: "/qualified/img-03.jpg",
    avatar: "/professionol/img-03.jpg",
  },
  {
    name: "William Williams",
    location: "Nashville, IL",
    price: "$1,198.12/hr",
    rating: 5.0,
    reviews: "57,282",
    image: "/qualified/img-04.jpg",
    avatar: "/professionol/img-04.jpg",
  },
];

const stories = [
  {
    name: "Leonard Sullivan",
    role: "2nd Standard, Manchester UK",
    image: "/success_stories/img-01.jpg",
    title:
      "I highly recommend this platform, amazing experience with fast delivery",
    text: "Their teaching method is conceptual, motivating and friendly. I can clear my doubt any time. They have very deep knowledge of subject and exam pattern, with all the guidance of their tutors, I scored 98% in Mathematics and 96% in Physics.",
  },
  {
    name: "Deanna Griffin",
    role: "2nd Standard, Manchester UK",
    image: "/success_stories/img-02.jpg",
    title:
      "I highly recommend this platform, amazing experience with fast delivery",
    text: "Their teaching method is conceptual, motivating and friendly. I can clear my doubt any time. They have very deep knowledge of subject and exam pattern.",
  },
  {
    name: "Bruce Mccarthy",
    role: "2nd Standard, Manchester UK",
    image: "/success_stories/img-03.jpg",
    title:
      "I highly recommend this platform, amazing experience with fast delivery",
    text: "With the guidance of their tutors, I scored 98% in Mathematics and 96% in Physics. The overall learning experience was amazing.",
  },
];

const categories = [
  {
    title: "Music learning",
    count: "6,301 Listings",
    image: "/categories/img-09.jpg",
  },
  {
    title: "Computer & hardware",
    count: "4,329 Listings",
    image: "/categories/img-10.jpg",
  },
  {
    title: "Beauty learning",
    count: "6,406 Listings",
    image: "/categories/img-11.jpg",
  },
  {
    title: "IT & development",
    count: "5,925 Listings",
    image: "/categories/img-12.jpg",
  },
  {
    title: "Islamic education",
    count: "4,157 Listings",
    image: "/categories/img-13.jpg",
  },
];

const tutorGroups = [
  {
    title: "Tutors in Atlanta",
    links: [
      "B.Tech IT",
      "B.Tech Chemical",
      "B.Tech Petroleum",
      "B.Tech Ceramic",
      "B.Tech Production",
    ],
  },
  {
    title: "Tutors in Atlanta",
    links: [
      "B.Tech Robotics",
      "B.Tech Industrial",
      "B.Tech Biotech",
      "B.Tech Communications",
      "B.Tech Civil",
    ],
  },
  {
    title: "Tutors in Tulsa",
    links: [
      "B.Tech Ceramic",
      "B.Tech Mechatronics",
      "B.Tech Aerospace",
      "B.Tech Power",
    ],
  },
  {
    title: "Tutors in Oklahoma City",
    links: [
      "B.Tech Ceramic",
      "B.Tech Aeronautical",
      "B.Tech Communications",
      "B.Tech Electrical",
      "Content writing",
    ],
  },
  {
    title: "Tutors in Virginia Beach",
    links: [
      "B.Tech Environmental",
      "B.Tech Mech",
      "B.Tech Robotics",
      "B.Tech Transportation",
      "B.Tech Marine",
    ],
  },
  {
    title: "Tutors in San Francisco",
    links: [
      "B.Tech Marine",
      "B.Tech Environmental",
      "B.Tech Textile",
      "B.Tech ECE",
      "B.Tech CSE",
    ],
  },
  {
    title: "Tutors in Mesa",
    links: [
      "B.Tech ECE",
      "B.Tech IT",
      "B.Tech Industrial",
      "B.Tech Aeronautical",
      "B.Tech CSE",
    ],
  },
  {
    title: "Tutors in Boston",
    links: [
      "B.Tech Petroleum",
      "B.Tech Metallurgical",
      "B.Tech Mining",
      "B.Tech Power",
      "B.Tech Aerospace",
    ],
  },
];
</script>

<template>
  <main>
    <section class="relative overflow-hidden py-20 lg:py-28">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div class="grid items-center gap-12 lg:grid-cols-2">
          <div>
            <div class="max-w-2xl">
              <h1
                class="text-4xl font-bold tracking-tight text-slate-900 sm:text-5xl lg:text-6xl"
              >
                A good
                <span class="text-indigo-600">#education</span>
                is always a base of
              </h1>

              <span
                class="mt-4 block text-4xl font-bold text-indigo-600 sm:text-5xl"
              >
                Equitable soci
              </span>

              <p class="mt-6 max-w-xl text-lg leading-8 text-slate-600">
                Consectur adipiscing elitsedo eiusmod tempor incididuntem
                utaborate dolore magna aliqua ad minim veniamque.
              </p>

              <ul class="mt-10 flex flex-col gap-5 sm:flex-row sm:items-center">
                <li class="relative">
                  <a
                    href="signup.html"
                    class="bg-primary inline-flex items-center gap-2 rounded-full px-7 py-4 text-base font-semibold text-white transition hover:scale-105"
                  >
                    <span>Start as student</span>
                    <i class="icon icon-chevron-right"></i>
                  </a>
                </li>

                <li>
                  <a
                    href="signup.html"
                    class="inline-flex items-center gap-3 rounded-full border border-slate-200 bg-white px-7 py-4 text-base font-semibold text-slate-900 transition hover:border-indigo-200 hover:scale-105"
                  >
                    <span>Join as Instructor</span>
                    <em class="not-italic text-sm font-medium text-green-600"
                      >It’s Free!</em
                    >
                  </a>
                </li>
              </ul>

              <div class="mt-8 flex items-start gap-3">
                <UIcon name="i-lucide-shield-check" class="size-5" />
                <p class="text-sm leading-6 text-slate-600">
                  You can also join as parent to explore
                  <a
                    href="signup.html"
                    class="font-semibold text-indigo-600 hover:underline"
                  >
                    Join today
                  </a>
                </p>
              </div>
            </div>
          </div>

          <!-- Image -->
          <div class="hidden lg:block">
            <div class="relative">
              <div
                class="absolute inset-0 rounded-full bg-indigo-100 blur-3xl"
              ></div>
              <img
                src="/banners/02.png"
                alt="Education banner"
                class="relative z-10 mx-auto max-w-full"
              />
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="py-8 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4">
        <UCarousel
          :items="brands"
          :ui="{
            item: 'basis-1/2 sm:basis-1/3 md:basis-1/4 lg:basis-1/6',
          }"
          loop
          autoplay
          :autoplay="{ delay: 2000 }"
        >
          <template #default="{ item }">
            <div
              class="max-h-12 flex items-center justify-center bg-white transition"
            >
              <img
                :src="item"
                alt="brand"
                class="w-full object-contain transition p-4"
              />
            </div>
          </template>
        </UCarousel>
      </div>
    </section>

    <section class="py-8 bg-white overflow-hidden">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div
          class="grid grid-cols-1 lg:grid-cols-2 gap-12 lg:gap-16 items-center"
        >
          <!-- Content -->
          <div>
            <h4 class="mb-3 text-base sm:text-lg font-semibold text-primary">
              Better Learning. Better Results
            </h4>

            <h2
              class="max-w-xl text-3xl sm:text-4xl lg:text-5xl font-bold leading-tight text-gray-900"
            >
              Online education platform that fits for everyone
            </h2>

            <p
              class="mt-5 max-w-xl text-base sm:text-lg leading-8 text-gray-600"
            >
              Accusamus et iusidio dignissimos ducimus blanditiis praesentium
              voluptatum deleniti atque corrupti quos dolores etmquasa molestias
              epturi sint occaecati cupiditate non providente mikume molareshe.
            </p>

            <NuxtLink
              to="/how-it-work"
              class="mt-8 inline-flex items-center gap-2 rounded-full bg-primary px-6 py-3.5 text-sm sm:text-base font-semibold text-white shadow-lg shadow-primary/20 transition hover:-translate-y-0.5 hover:shadow-xl"
            >
              <span>Explore more about us</span>
              <UIcon name="i-lucide-chevron-right" class="size-5" />
            </NuxtLink>
          </div>

          <div class="relative">
            <div class="relative mx-auto max-w-lg">
              <div class="relative rounded-2xl bg-gray-50 p-4 sm:p-6">
                <figure class="overflow-hidden rounded-xl">
                  <img
                    src="/platform/img-01.png"
                    alt="online learning platform"
                    class="w-full object-cover"
                  />
                </figure>

                <img
                  src="/platform/img-02.png"
                  alt="student"
                  class="absolute -bottom-6 -left-3 sm:-left-8 w-32 sm:w-44 rounded-3xl border-4 border-white"
                />

                <div
                  class="absolute -bottom-5 right-4 sm:right-8 rounded-2xl bg-white px-5 py-4 border border-gray-100"
                >
                  <h6
                    class="text-xs font-semibold uppercase tracking-wide text-gray-500"
                  >
                    Founder & CEO
                  </h6>
                  <h5 class="mt-1 text-base sm:text-lg font-bold text-gray-900">
                    Allen Wake
                  </h5>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="counter-section" class="py-8 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
          <div
            v-for="(stat, i) in stats"
            :key="i"
            class="rounded-3xl bg-white border border-border hover:border-primary p-4 text-center transition"
          >
            <img :src="stat.icon" alt="icon" class="mx-auto mb-4 h-12 w-auto" />

            <h4 class="text-2xl sm:text-3xl font-bold text-gray-900">
              {{ counters[i].toLocaleString() }}
              <span class="text-primary">
                {{ stat.suffix }}
              </span>
            </h4>

            <p class="mt-3 text-sm text-gray-600 leading-6">
              {{ stat.label }}
            </p>
          </div>
        </div>
      </div>
    </section>

    <section class="py-8 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center max-w-2xl mx-auto mb-12">
          <h4 class="text-primary font-semibold mb-2">
            Our featured instructors
          </h4>
          <h2 class="text-3xl sm:text-4xl font-bold text-gray-900">
            Every instructor is professional and highly qualified
          </h2>
          <p class="mt-4 text-gray-600">
            Accusamus et iusidio dignissimos ducimus blanditiis praesentium
            voluptatum deleniti atque corrupti quos dolores.
          </p>
        </div>

        <UCarousel
          :items="instructors"
          loop
          :autoplay="{ delay: 2000 }"
          :ui="{
            item: 'basis-full sm:basis-1/2 lg:basis-1/3',
          }"
        >
          <template #default="{ item }">
            <InstructorCard :instructor="item" />
          </template>
        </UCarousel>

        <div class="text-center mt-12">
          <NuxtLink
            to="/search-listing"
            class="inline-flex items-center gap-2 bg-primary text-white px-6 py-3 rounded-full font-semibold shadow hover:shadow-lg transition"
          >
            Explore all instructors
            <UIcon name="i-lucide-chevron-right" class="size-5" />
          </NuxtLink>
        </div>
      </div>
    </section>

    <section class="relative overflow-hidden bg-gray-50 py-8">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div class="mb-10 max-w-3xl">
          <h2
            class="text-3xl font-bold leading-tight text-gray-900 sm:text-4xl lg:text-5xl"
          >
            See how our visitors & members made their
            <span class="text-primary">#Success Stories</span>
          </h2>
        </div>

        <UCarousel
          :items="stories"
          loop
          dots
          fade
          :autoplay="{ delay: 3500 }"
          :ui="{
            item: 'basis-full',
          }"
        >
          <template #default="{ item }">
            <article
              class="border border-border hover:border-primary grid items-center gap-8 rounded-2xl bg-white p-4 md:grid-cols-2"
            >
              <div class="relative">
                <img
                  :src="item.image"
                  :alt="item.name"
                  class="h-72 w-full rounded-xl object-cover sm:h-96"
                />

                <div
                  class="absolute -bottom-5 right-6 grid size-16 place-items-center rounded-2xl bg-primary shadow-lg"
                >
                  <UIcon name="i-lucide-quote" class="size-8 text-white" />
                </div>
              </div>

              <div class="pt-6 md:pt-0">
                <div class="mb-5 flex text-yellow-400">
                  <UIcon
                    v-for="i in 5"
                    :key="i"
                    name="i-lucide-star"
                    class="size-5 fill-current"
                  />
                </div>

                <h3
                  class="text-2xl font-bold leading-snug text-gray-900 lg:text-3xl"
                >
                  {{ item.title }}
                </h3>

                <blockquote
                  class="mt-5 text-base leading-8 text-gray-600 lg:text-lg"
                >
                  “{{ item.text }}”
                </blockquote>

                <div class="mt-7">
                  <h4 class="text-lg font-bold text-gray-900">
                    {{ item.name }}
                  </h4>
                  <p class="mt-1 text-sm text-gray-500">
                    {{ item.role }}
                  </p>
                </div>
              </div>
            </article>
          </template>
        </UCarousel>
      </div>
    </section>

    <section class="py-8 bg-white">
      <div class="max-w-7xl mx-auto px-4">
        <div class="text-center max-w-2xl mx-auto mb-12">
          <h4 class="text-primary font-semibold mb-2">
            Let’s make a quick start today
          </h4>
          <h2 class="text-3xl sm:text-4xl font-bold text-gray-900">
            Choose from the top visited categories you may like
          </h2>
          <p class="mt-4 text-gray-600">
            Accusamus et iusidio dignissimos ducimus blanditiis praesentium
            voluptatum deleniti atque corrupti quos dolores.
          </p>
        </div>

        <UCarousel
          :items="categories"
          loop
          dots
          :autoplay="{ delay: 5000 }"
          :ui="{
            item: 'basis-1/2 sm:basis-1/3 lg:basis-1/4',
          }"
        >
          <template #default="{ item }">
            <div class="p-2">
              <NuxtLink
                to="/search-listing"
                class="group block overflow-hidden rounded-2xl border border-border bg-white transition"
              >
                <div class="relative h-48 overflow-hidden">
                  <img
                    :src="item.image"
                    class="w-full h-full object-cover group-hover:scale-110 transition duration-500"
                  />
                </div>

                <div class="p-5">
                  <h6
                    class="text-base font-semibold text-gray-900 group-hover:text-primary transition"
                  >
                    {{ item.title }}
                  </h6>

                  <span class="text-sm text-gray-500">
                    {{ item.count }}
                  </span>
                </div>
              </NuxtLink>
            </div>
          </template>
        </UCarousel>

        <!-- Button -->
        <div class="text-center mt-12">
          <NuxtLink
            to="/search-listing"
            class="inline-flex items-center gap-2 bg-primary text-white px-6 py-3 rounded-full font-semibold shadow hover:shadow-lg transition"
          >
            Explore All categories
            <UIcon name="i-lucide-chevron-right" class="size-5" />
          </NuxtLink>
        </div>
      </div>
    </section>

    <section class="bg-gray-950 py-8">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div class="mb-12 text-center">
          <h5 class="text-base font-semibold text-primary">
            Explore from our huge collection
          </h5>
          <h3 class="mt-3 text-3xl font-bold text-white sm:text-4xl">
            Approach tutors near to your house
          </h3>
        </div>

        <div class="grid gap-6 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4">
          <div
            v-for="group in tutorGroups"
            :key="group.title + group.links[0]"
            class="rounded-3xl border border-white/10 bg-white/[0.03] p-6 transition hover:-translate-y-1 hover:bg-white/[0.06]"
          >
            <h5 class="mb-4 text-lg font-bold text-white">
              {{ group.title }}
            </h5>

            <ul class="space-y-3">
              <li v-for="link in group.links" :key="link">
                <NuxtLink
                  to="/search-listing"
                  class="text-sm text-gray-400 transition hover:text-primary"
                >
                  {{ link }}
                </NuxtLink>
              </li>

              <li class="pt-2">
                <NuxtLink
                  to="/search-listing"
                  class="inline-flex items-center gap-1 text-sm font-semibold text-primary"
                >
                  Explore all
                  <UIcon name="i-lucide-arrow-right" class="size-4" />
                </NuxtLink>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>
