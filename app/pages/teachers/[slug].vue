<script setup>
const { data: courses } = await useAsyncData(
  'courses',
  () => $fetch('/data/courses.json'),
  {
    default: () => [],
    server: false
  }
)

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
  <main class="bg-gray-50">
    <section class="bg-white">
      <div class="container mx-auto px-4 lg:px-8 py-4">
        <div class="flex items-center gap-2 text-sm text-gray-500">
          <span>হোম</span>
          <Icon name="heroicons:chevron-right" class="w-4 h-4" />
          <span>শিক্ষক খুঁজুন</span>
          <Icon name="heroicons:chevron-right" class="w-4 h-4" />
          <span class="text-gray-900 font-medium">রাকিবুল ইসলাম</span>
        </div>
      </div>
    </section>

    <section class="container mx-auto px-4 lg:px-8 py-8">
      <div class="grid gap-6 xl:grid-cols-[1fr_340px]">
        <div class="space-y-6">
          <section class="bg-white rounded-3xl border border-gray-100 p-6">
            <div class="grid lg:grid-cols-12 gap-6">
              <div class="lg:col-span-4">
                <img src="https://images.unsplash.com/photo-1560250097-0b93528c311a?q=80&w=900&auto=format&fit=crop"
                  class="rounded-2xl h-full w-full object-cover" />
              </div>

              <div class="lg:col-span-8">
                <div class="flex items-center gap-2">
                  <h1 class="text-4xl font-extrabold text-gray-900">
                    রাকিবুল ইসলাম
                  </h1>
                  <Icon name="heroicons:check-badge-solid" class="w-7 h-7 text-blue-600" />
                </div>
                <p class="text-gray-500 mt-2 text-lg">
                  গণিত শিক্ষক
                </p>

                <div class="flex flex-wrap gap-3 py-2">
                  <span class="px-4 py-2 bg-gray-100 rounded-xl text-sm font-medium">
                    SSC
                  </span>
                  <span class="px-4 py-2 bg-gray-100 rounded-xl text-sm font-medium">
                    HSC
                  </span>
                  <span class="px-4 py-2 bg-gray-100 rounded-xl text-sm font-medium">
                    Admission
                  </span>
                  <span class="px-4 py-2 bg-gray-100 rounded-xl text-sm font-medium">
                    Varsity
                  </span>
                </div>

                <div class="grid md:grid-cols-2 gap-4 py-2">
                  <div class="flex items-center gap-3 text-gray-700">
                    <Icon name="heroicons:briefcase" class="w-5 h-5 text-blue-600" />
                    <span>অভিজ্ঞতা: ৬+ বছর</span>
                  </div>

                  <div class="flex items-center gap-3 text-gray-700">
                    <Icon name="heroicons:user-group" class="w-5 h-5 text-blue-600" />
                    <span>শিক্ষার্থী: ৮,০০০+</span>
                  </div>

                  <div class="flex items-center gap-3 text-gray-700">
                    <Icon name="heroicons:book-open" class="w-5 h-5 text-blue-600" />
                    <span>কোর্স: ১৮টি</span>
                  </div>

                  <div class="flex items-center gap-3 text-gray-700">
                    <Icon name="heroicons:star" class="w-5 h-5 text-yellow-400" />
                    <span>রেটিং: 4.9 (320)</span>
                  </div>
                </div>

                <div class="text-body py-2.5">
                  <p>
                    আমি রাকিবুল ইসলাম, গণিত ও উচ্চতর গণিতের একজন অভিজ্ঞ শিক্ষক।
                    গত ৬ বছরের বেশি সময় ধরে অনলাইন ও অফলাইনে শিক্ষার্থীদের
                    পড়িয়ে আসছি। সহজ ও কার্যকর পদ্ধতিতে গণিত শেখানোই আমার মূল লক্ষ্য।
                  </p>
                </div>

                <div class="flex flex-wrap gap-4 mt-8">
                  <button
                    class="px-4 py-2.5 border border-border rounded font-semibold flex items-center gap-2 hover:bg-gray-50">
                    <Icon name="mdi:whatsapp" class="w-5 h-5 text-green-500" />
                    WhatsApp করুন
                  </button>

                  <button
                    class="px-4 py-2.5 border border-border rounded font-semibold flex items-center gap-2 hover:bg-gray-50">
                    <Icon name="heroicons:heart" class="w-5 h-5 text-red-500" />
                    রিপোর্ট করুন
                  </button>
                </div>
              </div>
            </div>
          </section>

          <section class="rounded-3xl bg-white p-5 shadow-sm ring-1 ring-gray-100">
            <h3 class="mb-5 text-xl font-bold text-gray-900">
              Media gallery
            </h3>

            <div class="w-full">
              <UCarousel ref="carousel" v-slot="{ item }" loop :items="items" :prev="{ onClick: onClickPrev }"
                :next="{ onClick: onClickNext }" class="w-full" @select="onSelect">
                <div class="relative overflow-hidden rounded">
                  <img :src="item" alt="Gallery image" class="h-72 w-full object-cover sm:h-96" loading="lazy" />

                  <button v-if="item.includes('img-02')" class="absolute inset-0 grid place-items-center bg-black/20">
                    <span class="grid size-16 place-items-center rounded-full bg-white/90 text-primary shadow-lg">
                      <UIcon name="i-lucide-play" class="size-7 fill-current" />
                    </span>
                  </button>
                </div>
              </UCarousel>

              <div class="mt-4 flex gap-3 overflow-x-auto pb-2">
                <button v-for="(item, index) in items" :key="index"
                  class="relative size-20 shrink-0 overflow-hidden rounded opacity-50 ring-2 ring-transparent transition hover:opacity-100"
                  :class="{
                    'opacity-100 ring-primary': activeIndex === index,
                  }" @click="select(index)">
                  <img :src="item" alt="Gallery thumbnail" class="h-full w-full object-cover" loading="lazy" />

                  <span v-if="item.includes('img-02')"
                    class="absolute inset-0 grid place-items-center bg-black/30 text-white">
                    <UIcon name="i-lucide-play" class="size-5 fill-current" />
                  </span>
                </button>
              </div>
            </div>
          </section>

          <section>
            <div class="mb-5 flex items-center justify-between gap-4">
              <h3 class="text-2xl font-bold text-gray-900">
                আমার কোর্সসমূহ
              </h3>
            </div>

            <UCarousel v-if="courses?.length" :items="courses" loop :autoplay="{ delay: 3000 }" :ui="{
              item: 'basis-full md:basis-1/2 xl:basis-1/3'
            }">
              <template #default="{ item: course }">
                <CourseCard :course="course" />
              </template>
            </UCarousel>
          </section>
        </div>

        <aside class="h-max space-y-5 xl:sticky xl:top-24">
          <section class="rounded-xl bg-white p-6 ">
            <h4 class="mb-5 font-bold text-gray-900">Contact details</h4>

            <div class="space-y-4">
              <div class="flex items-center gap-3">
                <div class="grid size-10 place-items-center rounded-full bg-red-50 text-red-500">
                  <UIcon name="i-lucide-phone-call" class="size-5" />
                </div>
                <span class="text-sm font-semibold text-gray-700">0800 - 28 *** - ***</span>
              </div>

              <div class="flex items-center gap-3">
                <div class="grid size-10 place-items-center rounded-full bg-purple-50 text-purple-500">
                  <UIcon name="i-lucide-mail" class="size-5" />
                </div>
                <span class="text-sm font-semibold text-gray-700">cindy287@*****.com</span>
              </div>

              <div class="flex items-center gap-3">
                <div class="grid size-10 place-items-center rounded-full bg-green-50 text-green-500">
                  <UIcon name="i-simple-icons-whatsapp" class="size-5" />
                </div>
                <span class="text-sm font-semibold text-gray-700">0800 - 28 *** - ***</span>
              </div>

              <div class="flex items-center gap-3">
                <div class="grid size-10 place-items-center rounded-full bg-orange-50 text-orange-500">
                  <UIcon name="i-lucide-globe" class="size-5" />
                </div>
                <span class="text-sm font-semibold text-gray-700">www.cindylorex77.com</span>
              </div>
            </div>
          </section>

          <section class="bg-white rounded-3xl border border-gray-100 p-6">
            <div class="space-y-6">
              <div class="flex items-center justify-between">
                <div class="flex items-center gap-3">
                  <Icon name="heroicons:users" class="w-6 h-6 text-blue-600" />
                  <span class="text-gray-600">মোট শিক্ষার্থী</span>
                </div>
                <span class="font-bold text-xl">৮,৫০০+</span>
              </div>
              <div class="flex items-center justify-between">
                <div class="flex items-center gap-3">
                  <Icon name="heroicons:book-open" class="w-6 h-6 text-blue-600" />
                  <span class="text-gray-600">মোট কোর্স</span>
                </div>
                <span class="font-bold text-xl">১৮টি</span>
              </div>
              <div class="flex items-center justify-between">
                <div class="flex items-center gap-3">
                  <Icon name="heroicons:star" class="w-6 h-6 text-yellow-400" />
                  <span class="text-gray-600">মোট রিভিউ</span>
                </div>
                <span class="font-bold text-xl">৩২০+</span>
              </div>
            </div>
          </section>

          <section class="bg-white rounded-3xl border border-gray-100 p-6">
            <div class="flex items-center justify-between">
              <h3 class="text-2xl font-bold">
                নেক্সট লাইভ ক্লাস
              </h3>

              <button class="text-blue-600 text-sm font-semibold">
                সব দেখুন
              </button>
            </div>

            <div class="mt-6 space-y-4">
              <div>
                <p class="text-gray-500 text-sm">
                  বিষয়
                </p>

                <h4 class="font-bold text-lg mt-1">
                  বীজগণিতের সহজ সমাধান
                </h4>
              </div>

              <div class="flex items-center gap-3 text-gray-600">
                <Icon name="heroicons:calendar-days" class="w-5 h-5 text-blue-600" />
                <span>২৬ মে, ২০২৬</span>
              </div>

              <div class="flex items-center gap-3 text-gray-600">
                <Icon name="heroicons:clock" class="w-5 h-5 text-blue-600" />
                <span>রাত ৯:০০ - ১০:০০</span>
              </div>
            </div>

            <button
              class="w-full mt-8 py-4 rounded-2xl border border-blue-600 text-blue-600 font-semibold hover:bg-blue-50 transition">
              লাইভ ক্লাসে যোগ দিন
            </button>
          </section>

          <!-- Reviews -->
          <section class="bg-white rounded-3xl border border-gray-100 p-6">
            <h3 class="text-2xl font-bold">
              শিক্ষার্থীদের মতামত
            </h3>

            <div class="flex items-center gap-3 mt-5">
              <h2 class="text-5xl font-extrabold">
                4.9
              </h2>

              <div>
                <div class="flex text-yellow-400">
                  ★★★★★
                </div>

                <p class="text-sm text-gray-500">
                  320+ রিভিউ
                </p>
              </div>
            </div>

            <!-- Review -->
            <div class="space-y-6 mt-8">

              <div class="flex gap-4">
                <img src="https://i.pravatar.cc/100?img=12" class="w-14 h-14 rounded-full" />

                <div>
                  <h4 class="font-bold">
                    তাসফিয়া রহমান
                  </h4>

                  <p class="text-sm text-gray-500 mt-1 leading-7">
                    স্যারের পড়ানোর স্টাইল অনেক ভালো। কঠিন বিষয়ও সহজে বুঝতে পারি।
                  </p>

                  <div class="text-yellow-400 mt-2">
                    ★★★★★
                  </div>
                </div>
              </div>

              <div class="flex gap-4">
                <img src="https://i.pravatar.cc/100?img=15" class="w-14 h-14 rounded-full" />

                <div>
                  <h4 class="font-bold">
                    সিয়াম হোসেন
                  </h4>

                  <p class="text-sm text-gray-500 mt-1 leading-7">
                    লাইভ ক্লাসগুলো খুবই হেল্পফুল। পরীক্ষার জন্য দারুণ প্রস্তুতি।
                  </p>

                  <div class="text-yellow-400 mt-2">
                    ★★★★★
                  </div>
                </div>
              </div>

            </div>

            <button
              class="w-full mt-8 py-4 rounded-2xl border border-blue-600 text-blue-600 font-semibold hover:bg-blue-50 transition">
              সব রিভিউ দেখুন
            </button>
          </section>

          <section class="rounded-xl bg-primary p-6 text-white">
            <div class="block mb-3">
              <h3 class="text-2xl font-bold">Join our tutor community</h3>
              <p class="mt-2 text-white/80">
                Join today and start spreading knowledge with students.
              </p>
            </div>
            <UButton color="neutral" size="lg" class="rounded-full">
              Join our community
            </UButton>
          </section>
        </aside>
      </div>
    </section>
  </main>
</template>
