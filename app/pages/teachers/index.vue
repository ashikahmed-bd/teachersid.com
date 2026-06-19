<script setup>
const tags = [
  "প্রি-স্কুল",
  "মাধ্যমিক (৬-৮ শ্রেণি)",
  "উচ্চ মাধ্যমিক",
  "৫.০ স্টার",
  "অনলাইন বুকিং",
  "শুধুমাত্র পুরুষ",
];

const subjects = [
  "সামাজিক বিজ্ঞান",
  "উর্দু",
  "গণিত",
  "ইংরেজি",
  "অঙ্কন",
  "কম্পিউটার বিজ্ঞান",
];

const teachers = [
  {
    name: "Abdul Karim",
    subject: "Mathematics",
    qualification: "MSc in Mathematics",
    rating: 4.8,
    reviews: 120,
    students: 540,
    price: 500,
    image: "https://i.pravatar.cc/150?img=1",
    subjects: ["Algebra", "Calculus", "Geometry"]
  },
  {
    name: "Nusrat Jahan",
    subject: "Physics",
    qualification: "BSc in Physics",
    rating: 4.7,
    reviews: 98,
    students: 430,
    price: 450,
    image: "https://i.pravatar.cc/150?img=2",
    subjects: ["Mechanics", "Thermodynamics"]
  },
  {
    name: "Mohammad Ali",
    subject: "Chemistry",
    qualification: "MSc in Chemistry",
    rating: 4.6,
    reviews: 85,
    students: 390,
    price: 400,
    image: "https://i.pravatar.cc/150?img=3",
    subjects: ["Organic", "Inorganic"]
  },
  {
    name: "Farhana Rahman",
    subject: "Biology",
    qualification: "MSc in Biology",
    rating: 4.9,
    reviews: 150,
    students: 610,
    price: 550,
    image: "https://i.pravatar.cc/150?img=4",
    subjects: ["Zoology", "Botany"]
  },
  {
    name: "Tanvir Hossain",
    subject: "English",
    qualification: "MA in English",
    rating: 4.5,
    reviews: 75,
    students: 320,
    price: 350,
    image: "https://i.pravatar.cc/150?img=5",
    subjects: ["Grammar", "Literature"]
  },
  {
    name: "Sabrina Islam",
    subject: "ICT",
    qualification: "BSc in CSE",
    rating: 4.7,
    reviews: 110,
    students: 500,
    price: 600,
    image: "https://i.pravatar.cc/150?img=6",
    subjects: ["Programming", "Web Development"]
  },
  {
    name: "Rakib Hasan",
    subject: "Accounting",
    qualification: "MCom",
    rating: 4.4,
    reviews: 60,
    students: 250,
    price: 300,
    image: "https://i.pravatar.cc/150?img=7",
    subjects: ["Finance", "Business Studies"]
  },
  {
    name: "Jannat Ara",
    subject: "Economics",
    qualification: "MSc in Economics",
    rating: 4.6,
    reviews: 90,
    students: 410,
    price: 420,
    image: "https://i.pravatar.cc/150?img=8",
    subjects: ["Microeconomics", "Macroeconomics"]
  },
  {
    name: "Imran Hossain",
    subject: "History",
    qualification: "MA in History",
    rating: 4.3,
    reviews: 55,
    students: 210,
    price: 280,
    image: "https://i.pravatar.cc/150?img=9",
    subjects: ["World History", "Bangladesh History"]
  },
  {
    name: "Shila Akter",
    subject: "General Science",
    qualification: "BSc in Science",
    rating: 4.5,
    reviews: 70,
    students: 300,
    price: 380,
    image: "https://i.pravatar.cc/150?img=10",
    subjects: ["Physics Basics", "Chemistry Basics"]
  },
  {
    name: "Omar Faruk",
    subject: "Mathematics",
    qualification: "BSc in Applied Mathematics",
    rating: 4.6,
    reviews: 88,
    students: 410,
    price: 480,
    image: "https://i.pravatar.cc/150?img=11",
    subjects: ["Algebra", "Statistics"]
  },
  {
    name: "Mahiya Khan",
    subject: "Physics",
    qualification: "MSc in Theoretical Physics",
    rating: 4.8,
    reviews: 132,
    students: 560,
    price: 650,
    image: "https://i.pravatar.cc/150?img=12",
    subjects: ["Quantum", "Relativity"]
  },
  {
    name: "Hasan Mahmud",
    subject: "Chemistry",
    qualification: "MSc in Organic Chemistry",
    rating: 4.5,
    reviews: 76,
    students: 340,
    price: 420,
    image: "https://i.pravatar.cc/150?img=13",
    subjects: ["Organic", "Reaction Mechanism"]
  },
  {
    name: "Raisa Sultana",
    subject: "English",
    qualification: "MA in English Literature",
    rating: 4.7,
    reviews: 101,
    students: 480,
    price: 390,
    image: "https://i.pravatar.cc/150?img=14",
    subjects: ["Writing", "Speaking"]
  },
  {
    name: "Naimul Islam",
    subject: "ICT",
    qualification: "BSc in Software Engineering",
    rating: 4.9,
    reviews: 160,
    students: 720,
    price: 700,
    image: "https://i.pravatar.cc/150?img=15",
    subjects: ["Laravel", "Vue.js", "Node.js"]
  }
]
</script>

<template>
  <main class="bg-gray-50 py-10">
    <div class="mx-auto max-w-7xl px-4">

      <div class="max-w-4xl mx-auto py-8">
        <div class="flex flex-col gap-4 lg:flex-row lg:items-center lg:justify-between">
          <h3 class="text-xl font-bold text-gray-900">
            132,576 টি সার্চ রেজাল্ট পাওয়া গেছে
            <span class="text-primary">“গণিত”</span>
            টিউটরদের মধ্যে
          </h3>
        </div>

        <div class="mt-5 grid gap-3 lg:grid-cols-[1fr_260px_auto]">
          <UInput icon="i-lucide-search" size="xl" placeholder="আপনি কী খুঁজতে চান?" />
          <UButton size="xl" color="primary" class="justify-center rounded-full px-7">
            খুঁজুন
          </UButton>
        </div>

        <div class="mt-5 flex flex-wrap gap-2">
          <UBadge v-for="tag in tags" :key="tag" color="neutral" variant="soft" class="rounded-full px-3 py-1.5">
            {{ tag }}
            <UIcon name="i-lucide-x" class="ml-1 size-3" />
          </UBadge>
        </div>
      </div>

      <div class="grid gap-6 xl:grid-cols-[280px_1fr]">
        <aside class="h-max rounded-3xl bg-white p-5 border border-border">
          <div class="flex items-center justify-between">
            <h4 class="text-lg font-bold text-gray-900">ফিল্টার</h4>
            <UButton variant="ghost" color="neutral" size="sm"> পরিষ্কার করুন </UButton>
          </div>

          <div class="mt-6 space-y-7">
            <div>
              <h5 class="mb-3 font-semibold text-gray-900">শিক্ষার স্তর</h5>
              <USelect placeholder="শিক্ষার স্তর নির্বাচন করুন" :items="[
                'প্রাথমিক (১-৫ শ্রেণি)',
                'মাধ্যমিক (৬-৮ শ্রেণি)',
                'উচ্চ মাধ্যমিক (৯-১০ শ্রেণি)',
                'ভাষা কোর্স',
                'স্বল্প মেয়াদী কোর্স',
              ]" />
            </div>

            <div>
              <h5 class="mb-3 font-semibold text-gray-900">বিষয় নির্বাচন</h5>
              <div class="space-y-3">
                <UCheckbox v-for="subject in subjects" :key="subject" :label="subject" :default-value="[
                  'সামাজিক বিজ্ঞান',
                  'গণিত',
                  'কম্পিউটার বিজ্ঞান',
                ].includes(subject)
                  " />
              </div>
            </div>

            <div>
              <h5 class="mb-3 font-semibold text-gray-900">মূল্য সীমা</h5>
              <div class="grid grid-cols-2 gap-3">
                <UInput type="number" placeholder="সর্বনিম্ন মূল্য" />
                <UInput type="number" placeholder="সর্বোচ্চ মূল্য" />
              </div>
            </div>

            <div>
              <h5 class="mb-3 font-semibold text-gray-900">রেটিং</h5>
              <div class="space-y-3">
                <UCheckbox label="৫.০ / ৫.০" default-value />
                <UCheckbox label="৪.০ / ৫.০" />
                <UCheckbox label="৩.০ / ৫.০" default-value />
              </div>
            </div>

            <div>
              <h5 class="mb-3 font-semibold text-gray-900">অবস্থান</h5>
              <UInput icon="i-lucide-map-pin" placeholder="অবস্থান লিখুন" />
            </div>

            <div>
              <h5 class="mb-3 font-semibold text-gray-900">অন্যান্য</h5>
              <div class="space-y-3">
                <UCheckbox label="অনলাইন বুকিং" default-value />
                <UCheckbox label="প্রোফাইল ছবি" />
                <UCheckbox label="শুধুমাত্র পুরুষ" default-value />
                <UCheckbox label="শুধুমাত্র মহিলা" />
              </div>
            </div>

            <UButton block size="lg" class="rounded-full">
              ফিল্টার প্রয়োগ করুন
            </UButton>
          </div>
        </aside>

        <section class="space-y-5">
          <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
            <TeacherCard v-for="teacher in teachers" :teacher="teacher" />
          </div>
        </section>
      </div>
    </div>
  </main>
</template>
