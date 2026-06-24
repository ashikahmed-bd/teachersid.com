<script setup>

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
    image: "/teachers/1.jpg",
  },
  {
    name: "Gwendolyn Parker",
    location: "Las Vegas, TN",
    price: "$1,385.10/hr",
    rating: 5.0,
    reviews: "38,494",
    image: "/teachers/2.jpg",
  },
  {
    name: "Glen Burns",
    location: "Chicago, OH",
    price: "$1,336.83/hr",
    rating: 5.0,
    reviews: "47,044",
    image: "/teachers/3.jpg",
  },
  {
    name: "William Williams",
    location: "Nashville, IL",
    price: "$1,198.12/hr",
    rating: 5.0,
    reviews: "57,282",
    image: "/teachers/4.jpg",
  },
];

const stories = [
  {
    teacherId: 1,
    name: "মোঃ রাকিবুল ইসলাম",
    role: "ওয়েব ডেভেলপমেন্ট ইন্সট্রাক্টর",
    image: "/teachers/1.jpg",
    title: "অনলাইনে ৫,০০০+ শিক্ষার্থীকে প্রশিক্ষণ দিয়েছি",
    text: "এই প্ল্যাটফর্মের মাধ্যমে আমি দেশ-বিদেশের হাজারো শিক্ষার্থীর কাছে আমার কোর্স পৌঁছে দিতে পেরেছি। কোর্স ম্যানেজমেন্ট, পেমেন্ট ও শিক্ষার্থী ব্যবস্থাপনা সবকিছুই খুব সহজ।",
  },
  {
    teacherId: 2,
    name: "সাবরিনা সুলতানা",
    role: "গ্রাফিক ডিজাইন ইন্সট্রাক্টর",
    image: "/teachers/2.jpg",
    title: "নিজের দক্ষতাকে সফল অনলাইন ব্যবসায় রূপ দিয়েছি",
    text: "প্ল্যাটফর্মটির মাধ্যমে আমি সহজেই কোর্স প্রকাশ করতে পারি এবং শিক্ষার্থীদের সাথে সরাসরি যোগাযোগ রাখতে পারি। ফলে আমার আয় এবং শিক্ষার্থীর সংখ্যা দুটোই বৃদ্ধি পেয়েছে।",
  },
  {
    teacherId: 3,
    name: "আবদুল্লাহ আল মামুন",
    role: "ডিজিটাল মার্কেটিং ইন্সট্রাক্টর",
    image: "/teachers/3.jpg",
    title: "একটি শক্তিশালী ব্যক্তিগত ব্র্যান্ড তৈরি করতে পেরেছি",
    text: "উচ্চমানের কোর্স প্রকাশ এবং শিক্ষার্থীদের ইতিবাচক রিভিউ আমাকে একজন বিশ্বস্ত প্রশিক্ষক হিসেবে প্রতিষ্ঠিত করেছে।",
  },
];

const categories = [
  {
    name: 'ভর্তি প্রস্তুতি',
    courses: '৮৫০+ কোর্স',
    icon: 'heroicons:building-library',
    bg: 'bg-[#f4fbf7]',
    iconBg: 'bg-green-100',
    iconColor: 'text-green-600',
  },
  {
    name: 'চাকরি প্রস্তুতি',
    courses: '১,৫০০+ কোর্স',
    icon: 'heroicons:briefcase',
    bg: 'bg-[#fff8f1]',
    iconBg: 'bg-orange-100',
    iconColor: 'text-orange-500',
  },
  {
    name: 'স্কিল ডেভেলপমেন্ট',
    courses: '৭৫০+ কোর্স',
    icon: 'heroicons:chart-bar',
    bg: 'bg-[#faf5ff]',
    iconBg: 'bg-purple-100',
    iconColor: 'text-purple-600',
  },
  {
    name: 'ভাষা শিক্ষা',
    courses: '৬০০+ কোর্স',
    icon: 'heroicons:language',
    bg: 'bg-[#fff5f7]',
    iconBg: 'bg-pink-100',
    iconColor: 'text-pink-600',
  },
  {
    name: 'প্রোগ্রামিং',
    courses: '১,২০০+ কোর্স',
    icon: 'heroicons:code-bracket',
    bg: 'bg-[#eef6ff]',
    iconBg: 'bg-blue-100',
    iconColor: 'text-blue-600',
  },
  {
    name: 'ডিজিটাল মার্কেটিং',
    courses: '৫৫০+ কোর্স',
    icon: 'heroicons:megaphone',
    bg: 'bg-[#fffaf0]',
    iconBg: 'bg-yellow-100',
    iconColor: 'text-yellow-600',
  },
  {
    name: 'ডিজাইন',
    courses: '৪০০+ কোর্স',
    icon: 'heroicons:paint-brush',
    bg: 'bg-[#f5f3ff]',
    iconBg: 'bg-indigo-100',
    iconColor: 'text-indigo-600',
  },
  {
    name: 'ফ্রিল্যান্সিং',
    courses: '৩০০+ কোর্স',
    icon: 'heroicons:globe-alt',
    bg: 'bg-[#f0fdf4]',
    iconBg: 'bg-emerald-100',
    iconColor: 'text-emerald-600',
  },
]


</script>

<template>
  <main>

    <section class="bg-[url(/hero.png)] bg-cover bg-center bg-no-repeat">
      <div class="max-w-7xl mx-auto px-4 py-6">
        <div class="grid lg:grid-cols-2 gap-10 items-center">
          <div class="p-6 justify-self-start">
            <h1 class="text-title text-4xl lg:text-5xl font-extrabold leading-tight tracking-tight">
              আপনার প্রিয় শিক্ষকের
              <br />
              সাথে
              <span class="text-accent"> শিখুন, গড়ুন ভবিষ্যৎ</span>
            </h1>
            <p class="mt-8 text-body leading-9 max-w-xl">
              দেশের সেরা শিক্ষকদের কোর্স, লাইভ ক্লাস ও নোটস পেয়ে
              আপনার শেখার যাত্রাকে করুন আরও সহজ ও কার্যকর।
            </p>

            <div
              class="mt-10 flex bg-white rounded-2xl overflow-hidden shadow-xl shadow-blue-100 border border-gray-100">
              <input type="text" placeholder="আপনার কাঙ্ক্ষিত কোর্স সার্চ করুন..."
                class="flex-1 px-6 py-2.5 outline-none text-lg" />

              <button class="bg-blue-600 hover:bg-blue-700 transition px-8 flex items-center justify-center text-white">
                <Icon name="heroicons:magnifying-glass" class="w-7 h-7" />
              </button>
            </div>

            <div class="grid grid-cols-2 md:grid-cols-4 gap-5 mt-10">
              <div class="flex items-center gap-3">
                <div class="w-14 h-14 rounded-full bg-blue-50 flex items-center justify-center">
                  <Icon name="heroicons:book-open" class="w-6 h-6 text-blue-600" />
                </div>
                <div>
                  <h4 class="font-bold text-lg">৫,০০০+</h4>
                  <p class="text-gray-500 text-sm">কোর্সসমূহ</p>
                </div>
              </div>
              <div class="flex items-center gap-3">
                <div class="w-14 h-14 rounded-full bg-blue-50 flex items-center justify-center">
                  <Icon name="heroicons:user-group" class="w-6 h-6 text-blue-600" />
                </div>
                <div>
                  <h4 class="font-bold text-lg">১০,০০০+</h4>
                  <p class="text-gray-500 text-sm">শিক্ষক</p>
                </div>
              </div>
              <div class="flex items-center gap-3">
                <div class="w-14 h-14 rounded-full bg-blue-50 flex items-center justify-center">
                  <Icon name="heroicons:users" class="w-6 h-6 text-blue-600" />
                </div>
                <div>
                  <h4 class="font-bold text-lg">১,০০,০০০+</h4>
                  <p class="text-gray-500 text-sm">শিক্ষার্থী</p>
                </div>
              </div>

              <div class="flex items-center gap-3">
                <div class="w-14 h-14 rounded-full bg-blue-50 flex items-center justify-center">
                  <Icon name="heroicons:star" class="w-6 h-6 text-blue-600" />
                </div>

                <div>
                  <h4 class="font-bold text-lg">৪.৮/৫</h4>
                  <p class="text-gray-500 text-sm">রেটিং</p>
                </div>
              </div>
            </div>
          </div>

          <div class="hidden md:block justify-self-end">
            <div class="space-y-4">
              <div class="bg-white rounded-xl px-6 py-5 flex items-center gap-4 w-72">
                <div class="w-14 h-14 rounded-xl bg-blue-100 flex items-center justify-center">
                  <Icon name="heroicons:video-camera" class="w-7 h-7 text-blue-600" />
                </div>
                <div>
                  <h4 class="font-bold">লাইভ ক্লাস</h4>
                  <p class="text-sm text-gray-500">রিয়েল টাইমে শিখুন</p>
                </div>
              </div>

              <div class="bg-white rounded-xl px-6 py-5 flex items-center gap-4 w-72">
                <div class="w-14 h-14 rounded-xl bg-green-100 flex items-center justify-center">
                  <Icon name="heroicons:play-circle" class="w-7 h-7 text-green-600" />
                </div>

                <div>
                  <h4 class="font-bold">রেকর্ডেড ক্লাস</h4>
                  <p class="text-sm text-gray-500">যখন খুশি শিখুন</p>
                </div>
              </div>

              <div class="bg-white rounded-xl px-6 py-5 flex items-center gap-4 w-72">
                <div class="w-14 h-14 rounded-xl bg-purple-100 flex items-center justify-center">
                  <Icon name="heroicons:document-text" class="w-7 h-7 text-purple-600" />
                </div>

                <div>
                  <h4 class="font-bold">নোটস & রিসোর্স</h4>
                  <p class="text-sm text-gray-500">PDF ও স্টাডি ম্যাটেরিয়াল</p>
                </div>
              </div>

              <div class="bg-white rounded-xl px-6 py-5 flex items-center gap-4 w-72">
                <div class="w-14 h-14 rounded-xl bg-orange-100 flex items-center justify-center">
                  <Icon name="heroicons:trophy" class="w-7 h-7 text-orange-500" />
                </div>

                <div>
                  <h4 class="font-bold">সার্টিফিকেট</h4>
                  <p class="text-sm text-gray-500">কোর্স শেষে সার্টিফিকেট</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Features -->
    <section class="bg-white">
      <div class="container mx-auto px-6 py-14">
        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">

          <div class="flex gap-4">
            <div class="w-16 h-16 rounded-full bg-blue-50 flex items-center justify-center">
              <Icon name="heroicons:user" class="w-7 h-7 text-blue-600" />
            </div>

            <div>
              <h3 class="font-bold text-title">অভিজ্ঞ শিক্ষক</h3>
              <p class="text-body text-sm mt-1">
                দেশের সেরা অভিজ্ঞ শিক্ষক
              </p>
            </div>
          </div>

          <div class="flex gap-4">
            <div class="w-16 h-16 rounded-full bg-blue-50 flex items-center justify-center">
              <Icon name="heroicons:academic-cap" class="w-7 h-7 text-blue-600" />
            </div>

            <div>
              <h3 class="font-bold text-title">মানসম্মত কোর্স</h3>
              <p class="text-body text-sm mt-1">
                বাস্তবমুখী ও আপডেটেড কোর্স
              </p>
            </div>
          </div>

          <div class="flex gap-4">
            <div class="w-16 h-16 rounded-full bg-blue-50 flex items-center justify-center">
              <Icon name="heroicons:sparkles" class="w-7 h-7 text-blue-600" />
            </div>

            <div>
              <h3 class="font-bold text-title">সহজ শেখার অভিজ্ঞতা</h3>
              <p class="text-body text-sm mt-1">
                সহজ ইন্টারফেস ও গাইডলাইন
              </p>
            </div>
          </div>

          <div class="flex gap-4">
            <div class="w-16 h-16 rounded-full bg-blue-50 flex items-center justify-center">
              <Icon name="heroicons:shield-check" class="w-7 h-7 text-blue-600" />
            </div>

            <div>
              <h3 class="font-bold text-title">নিরাপদ পেমেন্ট</h3>
              <p class="text-body text-sm mt-1">
                ১০০% নিরাপদ লেনদেন
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Categories -->
    <section class="max-w-7xl mx-auto px-6 py-8">

      <div class="flex items-center justify-between mb-10">
        <h2 class="text-xl font-bold text-title">জনপ্রিয় ক্যাটাগরি</h2>
        <button class="text-sm text-accent font-semibold flex items-center gap-2">
          সব দেখুন
          <Icon name="heroicons:arrow-right" class="w-5 h-5" />
        </button>
      </div>

      <div>
        <UCarousel v-slot="{ item }" :items="categories" loop wheel-gestures :autoplay="{ delay: 2000 }" :ui="{
          item: 'basis-1/2 md:basis-1/3 lg:basis-1/6 px-2',
        }">
          <div :class="[
            item.bg,
            'rounded-xl p-6 lg:p-8 hover:-translate-y-1 transition h-full'
          ]">
            <div :class="[
              item.iconBg,
              'w-14 h-14 lg:w-16 lg:h-16 rounded-full flex items-center justify-center mb-4 lg:mb-6'
            ]">
              <Icon :name="item.icon" :class="[item.iconColor, 'w-7 h-7 lg:w-8 lg:h-8']" />
            </div>

            <h3 class="font-bold text-sm lg:text-base truncate">
              {{ item.name }}
            </h3>

            <p class="text-gray-500 mt-2 text-sm lg:text-base">
              {{ item.courses }}
            </p>
          </div>
        </UCarousel>
      </div>
    </section>


    <section class="py-8 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center max-w-2xl mx-auto mb-12">
          <h4 class="text-primary font-semibold mb-2">
            আমাদের দক্ষ প্রশিক্ষকবৃন্দ
          </h4>

          <h2 class="text-xl sm:text-2xl font-bold text-title">
            অভিজ্ঞ ও যোগ্য প্রশিক্ষকদের সাথে শিখুন
          </h2>

          <p class="mt-4 text-body">
            দেশের সেরা প্রশিক্ষকদের কাছ থেকে বাস্তবমুখী শিক্ষা গ্রহণ করুন।
            প্রতিটি প্রশিক্ষক তাদের নিজ নিজ ক্ষেত্রে অভিজ্ঞ এবং শিক্ষার্থীদের
            সফলতা নিশ্চিত করতে প্রতিশ্রুতিবদ্ধ।
          </p>
        </div>

        <UCarousel :items="instructors" loop :autoplay="{ delay: 2000 }" :ui="{
          item: 'basis-full sm:basis-1/2 lg:basis-1/3',
        }">
          <template #default="{ item }">
            <InstructorCard :instructor="item" />
          </template>
        </UCarousel>

        <div class="text-center mt-12">
          <NuxtLink to="/search-listing"
            class="inline-flex items-center gap-2 bg-primary text-white px-6 py-3 rounded-full font-semibold shadow hover:shadow-lg transition">
            সকল প্রশিক্ষক দেখুন
            <UIcon name="i-lucide-chevron-right" class="size-5" />
          </NuxtLink>
        </div>
      </div>
    </section>

    <section class="relative overflow-hidden bg-gray-50 py-8">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div class="mb-10 max-w-3xl">
          <h2 class="text-3xl font-bold leading-tight text-gray-900 sm:text-4xl lg:text-5xl"> আমাদের সফল <span
              class="text-primary">#শিক্ষকগণ</span> </h2>
          <p class="mt-4 text-lg text-gray-600"> অভিজ্ঞ প্রশিক্ষকদের সাথে শিখুন এবং আপনার দক্ষতাকে নতুন উচ্চতায় নিয়ে
            যান। </p>
        </div>
        <UCarousel :items="stories" loop fade :autoplay="{ delay: 3500 }" :ui="{ item: 'basis-full', }"> <template
            #default="{ item }">
            <NuxtLink :to="`/teachers/${item.slug}`">
              <article
                class="border border-border grid items-center gap-8 rounded-2xl bg-white p-4 transition-all duration-300 hover:shadow-xl md:grid-cols-2">
                <div class="relative">
                  <img :src="item.image" :alt="item.name" class="h-72 w-full rounded-xl object-cover sm:h-96" />
                  <div
                    class="absolute -bottom-5 right-6 grid size-16 place-items-center rounded-2xl bg-primary shadow-lg">
                    <UIcon name="i-lucide-graduation-cap" class="size-8 text-white" />
                  </div>
                </div>
                <div class="pt-6 md:pt-0">
                  <div class="mb-5 flex text-yellow-400">
                    <UIcon v-for="i in 5" :key="i" name="i-lucide-star" class="size-5 fill-current" />
                  </div>
                  <h3 class="text-2xl font-bold leading-snug text-gray-900 lg:text-3xl"> {{ item.title }} </h3>
                  <blockquote class="mt-5 text-base leading-8 text-gray-600 lg:text-lg"> “{{ item.text }}” </blockquote>
                  <div class="mt-7">
                    <h4 class="text-lg font-bold text-gray-900"> {{ item.name }} </h4>
                    <p class="mt-1 text-sm text-gray-500"> {{ item.role }} </p>
                    <div class="mt-4 inline-flex items-center gap-2 text-primary font-semibold"> প্রোফাইল দেখুন
                      <UIcon name="i-lucide-arrow-right" class="size-4" />
                    </div>
                  </div>
                </div>
              </article>
            </NuxtLink>
          </template> </UCarousel>
      </div>
    </section>


    <section class="container mx-auto px-6 lg:px-10 py-24">
      <div class="relative overflow-hidden rounded-xl bg-gradient-to-br from-slate-950 via-blue-950 to-indigo-950">
        <div class="relative grid items-center gap-12 lg:grid-cols-2">
          <div class="p-8 space-y-4">
            <span
              class="inline-flex items-center rounded-full border border-white/10 bg-white/5 px-4 py-2 text-sm font-medium text-blue-200 backdrop-blur">
              ৫০,০০০+ শিক্ষার্থী ইতোমধ্যে যুক্ত হয়েছে
            </span>

            <h2 class="text-2xl font-black leading-tight text-white lg:text-5xl">
              আজই শুরু করুন
              <span class="bg-gradient-to-r from-blue-400 to-cyan-400 bg-clip-text text-transparent">
                আপনার শেখার যাত্রা
              </span>
            </h2>

            <p class="max-w-2xl text-sm leading-8 text-slate-300 lg:text-base">
              ইন্ডাস্ট্রি এক্সপার্টদের কাছ থেকে শিখুন, সার্টিফিকেট অর্জন করুন
              এবং আপনার ক্যারিয়ারকে নিয়ে যান পরবর্তী স্তরে।
            </p>

            <div class="flex flex-wrap gap-6">
              <div>
                <h4 class="text-3xl font-bold text-white">50K+</h4>
                <p class="text-slate-400">শিক্ষার্থী</p>
              </div>

              <div>
                <h4 class="text-3xl font-bold text-white">1,200+</h4>
                <p class="text-slate-400">কোর্স</p>
              </div>

              <div>
                <h4 class="text-3xl font-bold text-white">300+</h4>
                <p class="text-slate-400">প্রশিক্ষক</p>
              </div>
            </div>

            <div class="mt-10 flex flex-wrap gap-4">
              <NuxtLink to="/courses"
                class="group inline-flex items-center gap-2 rounded bg-white px-6 py-3 font-semibold text-slate-900 transition-all hover:-translate-y-1 hover:shadow-2xl">
                কোর্স ব্রাউজ করুন
              </NuxtLink>

              <NuxtLink to="/become-instructor"
                class="inline-flex items-center gap-2 rounded border border-white/15 bg-white/5 px-6 py-3 font-semibold text-white backdrop-blur transition-all hover:bg-white/10">
                শিক্ষক হিসেবে যোগ দিন
              </NuxtLink>
            </div>
          </div>

          <div class="relative hidden h-full lg:flex items-center justify-center">
            <img src="https://images.unsplash.com/photo-1522202176988-66273c2fd55f?q=80&w=1200&auto=format&fit=crop"
              alt="Students Learning" class="h-auto w-full object-cover" />
          </div>
        </div>
      </div>
    </section>

  </main>
</template>
