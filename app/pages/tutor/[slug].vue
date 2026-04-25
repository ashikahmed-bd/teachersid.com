<script setup>
const activeTab = ref("intro");
const selectedImage = ref("/tutordetail/slider/img-01.jpg");

const languages = [
  "English",
  "Arabic",
  "Chinese",
  "Hebrew",
  "French",
  "Spanish",
];

const education = [
  {
    title: "MBBS, MD, DM Rheumatology",
    university: "University of Florida",
    location: "San Francisco, TN",
    date: "June 2018 - Present",
    description:
      "Experienced in modern teaching methods with strong academic background.",
  },
  {
    title: "MBBS, MS, Mch Neurosurgery",
    university: "University of Massachusetts-Amherst",
    location: "Kansas City, LA",
    date: "January 2014 - May 2018",
    description:
      "Focused on practical learning, student guidance, and exam preparation.",
  },
];

const teachGroups = [
  {
    title: "Class 9 - 10",
    subjects: [
      "Computer Science",
      "Mathematics",
      "General Science",
      "English",
      "Islamiat",
    ],
  },
  {
    title: "Class 6 - 8",
    subjects: ["Mathematics", "Computer Science", "General Science", "English"],
  },
  {
    title: "Short courses",
    subjects: ["Physical education", "History", "Basic French", "Learn ESL"],
  },
];

const gallery = [
  "/tutordetail/slider/img-01.jpg",
  "/tutordetail/slider/img-02.jpg",
  "/tutordetail/slider/img-03.jpg",
  "/tutordetail/slider/img-04.jpg",
  "/tutordetail/slider/img-05.jpg",
];

const reviews = [
  {
    name: "Ronnie Montgomery",
    image: "/tutordetail/review/img-01.png",
    rating: 5,
    time: "02 sec ago",
    text: "Amazing tutor. Very clear explanation and friendly teaching style.",
  },
  {
    name: "Margaret Hansen",
    image: "/tutordetail/review/img-02.png",
    rating: 4,
    time: "05 days ago",
    text: "Great experience. The tutor explains difficult topics in a simple way.",
  },
];

const relatedTutors = [
  {
    name: "William Williams",
    location: "Nashville, IL",
    price: "$1,198.12/hr",
    image: "/qualified/img-04.jpg",
    avatar: "/professionol/img-04.jpg",
  },
  {
    name: "Gwendolyn Parker",
    location: "Las Vegas, TN",
    price: "$1,385.10/hr",
    image: "/qualified/img-02.jpg",
    avatar: "/professionol/img-02.jpg",
  },
  {
    name: "Dwayne Garrett",
    location: "Arlington, TN",
    price: "$893.30/hr",
    image: "/qualified/img-01.jpg",
    avatar: "/professionol/img-01.jpg",
  },
];

const carousel = ref();
const activeIndex = ref(0);

const items = [
  "/tutordetail/slider/img-01.jpg",
  "/tutordetail/slider/img-02.jpg",
  "/tutordetail/slider/img-03.jpg",
  "/tutordetail/slider/img-04.jpg",
  "/tutordetail/slider/img-05.jpg",
  "/tutordetail/slider/img-06.jpg",
  "/tutordetail/slider/img-07.jpg",
];

function onSelect(index) {
  activeIndex.value = index;
}

function select(index) {
  activeIndex.value = index;
  carousel.value?.emblaApi?.scrollTo(index);
}

function onClickPrev() {
  carousel.value?.emblaApi?.scrollPrev();
}

function onClickNext() {
  carousel.value?.emblaApi?.scrollNext();
}
</script>

<template>
  <main class="bg-gray-50 py-10 sm:py-14">
    <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
      <div class="grid gap-6 xl:grid-cols-[1fr_340px]">
        <div class="space-y-6">
          <section
            class="rounded-3xl bg-white p-5 shadow-sm ring-1 ring-gray-100"
          >
            <div
              class="flex flex-col gap-5 lg:flex-row lg:items-start lg:justify-between"
            >
              <div class="flex gap-4">
                <img
                  src="/tutordetail/img-01.jpg"
                  alt="tutor"
                  class="size-48 rounded-2xl object-cover"
                />

                <div>
                  <h2
                    class="flex items-center gap-2 text-xl sm:text-2xl font-bold text-gray-900"
                  >
                    Armando weber
                    <UIcon
                      name="i-lucide-badge-check"
                      class="size-5 text-green-500"
                    />
                  </h2>

                  <p class="text-sm text-gray-500 mt-1">
                    Spreading knowledge everywhere that's all I do
                  </p>

                  <div
                    class="flex flex-wrap items-center gap-4 mt-3 text-sm text-gray-600"
                  >
                    <span class="flex items-center gap-1">
                      <UIcon
                        name="i-lucide-star"
                        class="size-4 text-yellow-400 fill-current"
                      />
                      <strong class="text-gray-900">4.5/5.0</strong>
                      <span>(4,448)</span>
                    </span>

                    <span class="flex items-center gap-1">
                      <UIcon
                        name="i-lucide-check-circle"
                        class="size-4 text-green-500"
                      />
                      <strong>95%</strong>
                      <span>Job completion</span>
                    </span>
                  </div>

                  <div
                    class="flex items-center gap-1 mt-2 text-sm text-gray-500"
                  >
                    <UIcon name="i-lucide-map-pin" class="size-4" />
                    Sacramento, CA
                  </div>

                  <div class="mt-4">
                    <p class="text-sm font-semibold text-gray-700 mb-1">
                      Languages I know
                    </p>
                    <div class="flex flex-wrap gap-2 text-sm text-gray-600">
                      <span
                        >English, Arabic, Chinese, Hebrew, French, Spanish</span
                      >
                      <button class="text-primary font-medium">+02 more</button>
                    </div>
                  </div>
                </div>
              </div>

              <div class="text-left lg:text-right">
                <span class="text-sm text-gray-500">Starting from:</span>
                <h3 class="text-2xl font-bold text-primary">$562.32/hr</h3>
              </div>
            </div>

            <div
              class="flex flex-col gap-4 lg:flex-row lg:items-center lg:justify-between"
            >
              <div class="flex items-center gap-2 text-sm text-gray-600">
                <UIcon name="i-lucide-globe" class="size-4" />
                <a href="#" class="text-primary hover:underline">
                  www.tutorlinkhere.com/tutor/uk/armando/295548
                </a>
                <UIcon name="i-lucide-copy" class="size-4 cursor-pointer" />
              </div>

              <div class="flex items-center gap-3">
                <button
                  class="flex items-center gap-1 text-gray-500 hover:text-red-500"
                >
                  <UIcon name="i-lucide-heart" class="size-5" />
                  <span>Save</span>
                </button>

                <UButton variant="soft" color="neutral" size="xl">
                  Let’s talk now
                </UButton>

                <UButton size="xl"> Book a tution </UButton>
              </div>
            </div>
          </section>

          <section class="rounded-3xl bg-white p-5">
            <UTabs
              color="neutral"
              variant="link"
              :items="[
                {
                  label: 'Introduction',
                  icon: 'i-lucide-home',
                  slot: 'intro',
                },
                {
                  label: 'Reviews',
                  icon: 'i-lucide-message-square-more',
                  slot: 'reviews',
                },
              ]"
            >
              <template #intro>
                <div class="space-y-8">
                  <section>
                    <h3 class="text-xl font-bold text-gray-900">
                      A brief introduction
                    </h3>
                    <p class="mt-4 leading-8 text-gray-600">
                      I am passionate about helping students understand concepts
                      clearly. My teaching style is friendly, practical, and
                      focused on real improvement. I help students prepare for
                      exams, improve confidence, and build strong academic
                      foundations.
                    </p>

                    <ul
                      class="mt-5 grid gap-3 text-sm text-gray-600 sm:grid-cols-2"
                    >
                      <li class="flex gap-2">
                        <UIcon
                          name="i-lucide-check"
                          class="mt-0.5 size-4 text-green-500"
                        />
                        Concept based teaching
                      </li>
                      <li class="flex gap-2">
                        <UIcon
                          name="i-lucide-check"
                          class="mt-0.5 size-4 text-green-500"
                        />
                        Regular progress tracking
                      </li>
                      <li class="flex gap-2">
                        <UIcon
                          name="i-lucide-check"
                          class="mt-0.5 size-4 text-green-500"
                        />
                        Exam preparation support
                      </li>
                      <li class="flex gap-2">
                        <UIcon
                          name="i-lucide-check"
                          class="mt-0.5 size-4 text-green-500"
                        />
                        Flexible online/offline classes
                      </li>
                    </ul>
                  </section>

                  <section>
                    <h3 class="text-xl font-bold text-gray-900">Education</h3>
                    <div class="mt-4 space-y-4">
                      <UAccordion
                        :items="
                          education.map((item) => ({
                            label: item.title,
                            content: item.description,
                            icon: 'i-lucide-graduation-cap',
                            university: item.university,
                            location: item.location,
                            date: item.date,
                          }))
                        "
                      >
                        <template #body="{ item }">
                          <div class="space-y-3 text-sm text-gray-600">
                            <div class="flex flex-wrap gap-4">
                              <span class="flex items-center gap-1">
                                <UIcon
                                  name="i-lucide-building-2"
                                  class="size-4"
                                />
                                {{ item.university }}
                              </span>
                              <span class="flex items-center gap-1">
                                <UIcon name="i-lucide-map-pin" class="size-4" />
                                {{ item.location }}
                              </span>
                              <span class="flex items-center gap-1">
                                <UIcon
                                  name="i-lucide-calendar"
                                  class="size-4"
                                />
                                {{ item.date }}
                              </span>
                            </div>
                            <p>{{ item.content }}</p>
                          </div>
                        </template>
                      </UAccordion>
                    </div>
                  </section>

                  <section>
                    <h3 class="text-xl font-bold text-gray-900">I can teach</h3>
                    <div class="mt-4 space-y-5">
                      <div
                        v-for="group in teachGroups"
                        :key="group.title"
                        class="rounded-2xl bg-gray-50 p-4"
                      >
                        <h4 class="font-bold text-gray-900">
                          {{ group.title }}
                        </h4>
                        <div class="mt-3 flex flex-wrap gap-2">
                          <NuxtLink
                            v-for="subject in group.subjects"
                            :key="subject"
                            to="/search-listing"
                            class="rounded-full bg-white px-3 py-1.5 text-sm text-gray-600 ring-1 ring-gray-100 transition hover:text-primary"
                          >
                            {{ subject }}
                          </NuxtLink>
                        </div>
                      </div>
                    </div>
                  </section>

                  <section
                    class="rounded-3xl bg-white p-5 shadow-sm ring-1 ring-gray-100"
                  >
                    <h3 class="mb-5 text-xl font-bold text-gray-900">
                      Media gallery
                    </h3>

                    <div class="w-full">
                      <UCarousel
                        ref="carousel"
                        v-slot="{ item }"
                        loop
                        :items="items"
                        :prev="{ onClick: onClickPrev }"
                        :next="{ onClick: onClickNext }"
                        class="w-full"
                        @select="onSelect"
                      >
                        <div class="relative overflow-hidden rounded">
                          <img
                            :src="item"
                            alt="Gallery image"
                            class="h-72 w-full object-cover sm:h-96"
                            loading="lazy"
                          />

                          <button
                            v-if="item.includes('img-02')"
                            class="absolute inset-0 grid place-items-center bg-black/20"
                          >
                            <span
                              class="grid size-16 place-items-center rounded-full bg-white/90 text-primary shadow-lg"
                            >
                              <UIcon
                                name="i-lucide-play"
                                class="size-7 fill-current"
                              />
                            </span>
                          </button>
                        </div>
                      </UCarousel>

                      <div class="mt-4 flex gap-3 overflow-x-auto pb-2">
                        <button
                          v-for="(item, index) in items"
                          :key="index"
                          class="relative size-20 shrink-0 overflow-hidden rounded opacity-50 ring-2 ring-transparent transition hover:opacity-100"
                          :class="{
                            'opacity-100 ring-primary': activeIndex === index,
                          }"
                          @click="select(index)"
                        >
                          <img
                            :src="item"
                            alt="Gallery thumbnail"
                            class="h-full w-full object-cover"
                            loading="lazy"
                          />

                          <span
                            v-if="item.includes('img-02')"
                            class="absolute inset-0 grid place-items-center bg-black/30 text-white"
                          >
                            <UIcon
                              name="i-lucide-play"
                              class="size-5 fill-current"
                            />
                          </span>
                        </button>
                      </div>
                    </div>
                  </section>
                </div>
              </template>
              <template #reviews>
                <div class="space-y-8">
                  <div>
                    <h3 class="text-xl font-bold text-gray-900">
                      Reviews (4,448)
                    </h3>

                    <div class="mt-5 space-y-5">
                      <div
                        v-for="review in reviews"
                        :key="review.name"
                        class="flex gap-4 rounded-2xl bg-gray-50 p-4"
                      >
                        <img
                          :src="review.image"
                          :alt="review.name"
                          class="size-12 rounded-full object-cover"
                        />

                        <div>
                          <div class="flex flex-wrap items-center gap-3">
                            <h4 class="font-bold text-gray-900">
                              {{ review.name }}
                            </h4>
                            <span class="text-xs text-gray-500">{{
                              review.time
                            }}</span>
                          </div>

                          <div
                            class="mt-1 flex items-center gap-1 text-yellow-400"
                          >
                            <UIcon
                              v-for="i in review.rating"
                              :key="i"
                              name="i-lucide-star"
                              class="size-4 fill-current"
                            />
                          </div>

                          <p class="mt-3 text-sm leading-7 text-gray-600">
                            {{ review.text }}
                          </p>
                        </div>
                      </div>
                    </div>
                  </div>

                  <div>
                    <h3 class="text-xl font-bold text-gray-900">
                      Add your review
                    </h3>

                    <form class="mt-5 space-y-4">
                      <div>
                        <label
                          class="mb-2 block text-sm font-semibold text-gray-700"
                        >
                          Give rating
                        </label>
                        <div class="flex gap-1 text-yellow-400">
                          <UIcon
                            v-for="i in 5"
                            :key="i"
                            name="i-lucide-star"
                            class="size-6 fill-current"
                          />
                        </div>
                      </div>

                      <UTextarea
                        placeholder="Enter review details"
                        :rows="5"
                        class="w-full"
                      />

                      <UCheckbox
                        label="I have read and agree to all Terms & conditions"
                      />

                      <UButton size="lg" class="rounded-full">
                        Submit Review
                      </UButton>
                    </form>
                  </div>
                </div>
              </template>
            </UTabs>
          </section>

          <section class="rounded-xl bg-primary p-6 text-white">
            <div
              class="flex flex-col gap-5 lg:flex-row lg:items-center lg:justify-between"
            >
              <div>
                <h3 class="text-2xl font-bold">Join our tutor community</h3>
                <p class="mt-2 text-white/80">
                  Join today and start spreading knowledge with students.
                </p>
              </div>

              <UButton color="neutral" size="lg" class="rounded-full">
                Join our community
              </UButton>
            </div>
          </section>

          <section>
            <div class="mb-5 flex items-center justify-between gap-4">
              <h3 class="text-2xl font-bold text-gray-900">
                Explore related tutors
              </h3>
            </div>

            <UCarousel
              :items="relatedTutors"
              loop
              :autoplay="{ delay: 3000 }"
              :ui="{
                item: 'basis-full md:basis-1/2 xl:basis-1/3',
              }"
            >
              <template #default="{ item: tutor }">
                <article
                  class="overflow-hidden rounded-xl border border-border hover:border-primary bg-white transition duration-300 hover:-translate-y-1"
                >
                  <div class="relative h-44">
                    <img
                      :src="tutor.image"
                      class="h-full w-full object-cover"
                      :alt="tutor.name"
                    />

                    <span
                      class="absolute left-3 top-3 rounded-full bg-primary px-3 py-1 text-xs font-semibold text-white"
                    >
                      FEATURED
                    </span>
                  </div>

                  <div class="p-5">
                    <div class="flex items-center gap-3">
                      <img
                        :src="tutor.avatar"
                        :alt="tutor.name"
                        class="size-12 rounded-full object-cover"
                      />

                      <div>
                        <h4
                          class="flex items-center gap-1 font-bold text-gray-900"
                        >
                          {{ tutor.name }}
                          <UIcon
                            name="i-lucide-badge-check"
                            class="size-4 text-green-500"
                          />
                        </h4>

                        <p class="text-sm text-gray-500">
                          {{ tutor.location }}
                        </p>
                      </div>
                    </div>

                    <div class="mt-4 space-y-2 text-sm text-gray-600">
                      <p>
                        Starting from:
                        <strong class="text-gray-900">{{ tutor.price }}</strong>
                      </p>

                      <p>
                        Qualification:
                        <strong class="text-gray-900">B.Tech/B.E.</strong>
                      </p>
                    </div>

                    <div
                      class="mt-5 flex items-center justify-between border-t border-gray-100 pt-4"
                    >
                      <div class="flex items-center gap-1">
                        <UIcon
                          name="i-lucide-star"
                          class="size-4 fill-current text-yellow-400"
                        />
                        <strong class="text-sm">5.0</strong>
                        <span class="text-xs text-gray-500">(4,448)</span>
                      </div>

                      <button
                        class="grid size-9 place-items-center rounded-full border border-gray-200 transition hover:text-red-500"
                      >
                        <UIcon name="i-lucide-heart" class="size-4" />
                      </button>
                    </div>
                  </div>
                </article>
              </template>
            </UCarousel>
          </section>
        </div>

        <aside class="h-max space-y-5 xl:sticky xl:top-24">
          <div class="rounded-xl bg-white p-6 border border-border">
            <h4 class="text-center font-bold text-gray-900">
              Hello! You can have my teaching services direct at
            </h4>

            <div class="mt-5 space-y-3">
              <UBadge
                color="success"
                variant="soft"
                class="w-full justify-between rounded p-3"
              >
                <span class="flex items-center gap-2">
                  <UIcon name="i-lucide-home" class="size-4" />
                  My home
                </span>
                <UIcon name="i-lucide-check-circle" class="size-4" />
              </UBadge>

              <UBadge
                color="info"
                variant="soft"
                class="w-full justify-between rounded p-3"
              >
                <span class="flex items-center gap-2">
                  <UIcon name="i-lucide-map-pin" class="size-4" />
                  Student's home
                </span>
                <UIcon name="i-lucide-check-circle" class="size-4" />
              </UBadge>

              <UBadge
                color="warning"
                variant="soft"
                class="w-full justify-between rounded p-3"
              >
                <span class="flex items-center gap-2">
                  <UIcon name="i-lucide-video" class="size-4" />
                  Online
                </span>
                <UIcon name="i-lucide-check-circle" class="size-4" />
              </UBadge>
            </div>
          </div>

          <div class="rounded-xl bg-white p-6 border border-border">
            <h4 class="mb-5 font-bold text-gray-900">Contact details</h4>

            <div class="space-y-4">
              <div class="flex items-center gap-3">
                <div
                  class="grid size-10 place-items-center rounded-full bg-red-50 text-red-500"
                >
                  <UIcon name="i-lucide-phone-call" class="size-5" />
                </div>
                <span class="text-sm font-semibold text-gray-700"
                  >0800 - 28 *** - ***</span
                >
              </div>

              <div class="flex items-center gap-3">
                <div
                  class="grid size-10 place-items-center rounded-full bg-purple-50 text-purple-500"
                >
                  <UIcon name="i-lucide-mail" class="size-5" />
                </div>
                <span class="text-sm font-semibold text-gray-700"
                  >cindy287@*****.com</span
                >
              </div>

              <div class="flex items-center gap-3">
                <div
                  class="grid size-10 place-items-center rounded-full bg-green-50 text-green-500"
                >
                  <UIcon name="i-simple-icons-whatsapp" class="size-5" />
                </div>
                <span class="text-sm font-semibold text-gray-700"
                  >0800 - 28 *** - ***</span
                >
              </div>

              <div class="flex items-center gap-3">
                <div
                  class="grid size-10 place-items-center rounded-full bg-orange-50 text-orange-500"
                >
                  <UIcon name="i-lucide-globe" class="size-5" />
                </div>
                <span class="text-sm font-semibold text-gray-700"
                  >www.cindylorex77.com</span
                >
              </div>
            </div>
          </div>

          <div class="rounded-xl bg-gray-950 p-6 text-center text-white">
            <h4 class="font-bold">Unlock contact details</h4>
            <p class="mt-2 text-sm leading-6 text-gray-400">
              Buy a package to unlock full phone, email and WhatsApp details.
            </p>

            <UButton to="/package" block size="lg" class="mt-5 rounded-full">
              <UIcon name="i-lucide-lock" class="mr-2 size-4" />
              Unlock feature
            </UButton>
          </div>
        </aside>
      </div>
    </div>
  </main>
</template>
