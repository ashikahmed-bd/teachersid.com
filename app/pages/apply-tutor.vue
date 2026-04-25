<script setup>
const benefits = [
  {
    icon: "i-lucide-dollar-sign",
    title: "Earn money",
    desc: "Set your own rates and earn by teaching students online or offline.",
  },
  {
    icon: "i-lucide-clock",
    title: "Flexible schedule",
    desc: "Teach anytime, anywhere based on your availability.",
  },
  {
    icon: "i-lucide-users",
    title: "Reach more students",
    desc: "Get discovered by thousands of students actively looking for tutors.",
  },
  {
    icon: "i-lucide-star",
    title: "Build your profile",
    desc: "Showcase your skills, experience, and grow your reputation.",
  },
];

const steps = [
  { title: "Create profile", desc: "Sign up and add your teaching details." },
  { title: "Get verified", desc: "Our team reviews your profile for quality." },
  {
    title: "Start teaching",
    desc: "Receive student requests and begin teaching.",
  },
];
</script>

<template>
  <main class="bg-gray-50">
    <section class="relative overflow-hidden bg-white py-16 sm:py-20">
      <div
        class="absolute -top-24 right-0 size-72 rounded-full bg-primary/10 blur-3xl"
      ></div>

      <div class="relative mx-auto max-w-7xl px-4 text-center">
        <UBadge color="primary" variant="soft" class="mb-4 rounded-full">
          Become a Tutor
        </UBadge>

        <h1 class="text-4xl font-bold text-gray-900 sm:text-5xl">
          Share your knowledge. Earn money.
        </h1>

        <p class="mt-5 max-w-2xl mx-auto text-gray-600">
          Join our platform and start teaching students worldwide. Flexible
          hours, great income, and growth opportunities.
        </p>

        <UButton size="xl" class="mt-8 rounded-full"> Get started now </UButton>
      </div>
    </section>

    <section class="py-16">
      <div class="max-w-7xl mx-auto px-4">
        <div class="grid gap-6 md:grid-cols-2 lg:grid-cols-4">
          <div
            v-for="b in benefits"
            :key="b.title"
            class="bg-white p-6 rounded-3xl border border-border transition"
          >
            <UIcon :name="b.icon" class="size-8 text-primary" />
            <h3 class="mt-4 font-bold text-gray-900">{{ b.title }}</h3>
            <p class="mt-2 text-sm text-gray-600">{{ b.desc }}</p>
          </div>
        </div>
      </div>
    </section>

    <section class="py-16 bg-white">
      <div class="max-w-7xl mx-auto px-4 text-center">
        <h2 class="text-3xl font-bold text-gray-900">How it works</h2>

        <div class="mt-10 grid gap-6 md:grid-cols-3">
          <div
            v-for="(step, i) in steps"
            :key="step.title"
            class="p-6 rounded-3xl bg-gray-50"
          >
            <div class="text-primary font-bold text-lg">Step {{ i + 1 }}</div>
            <h3 class="mt-2 font-bold text-gray-900">
              {{ step.title }}
            </h3>
            <p class="mt-2 text-sm text-gray-600">
              {{ step.desc }}
            </p>
          </div>
        </div>
      </div>
    </section>

    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4">
        <div class="grid lg:grid-cols-2 gap-10 items-center">
          <!-- Left Content -->
          <div>
            <h2
              class="text-3xl sm:text-4xl font-bold text-gray-900 leading-tight"
            >
              Start your journey as a tutor
            </h2>

            <p class="mt-4 text-gray-600 leading-7">
              Share your knowledge, earn money, and help students succeed. Fill
              out the form and get started today.
            </p>

            <div class="mt-6 space-y-3 text-sm text-gray-600">
              <div class="flex items-center gap-2">
                <UIcon name="i-lucide-check-circle" class="text-green-500" />
                Flexible schedule
              </div>
              <div class="flex items-center gap-2">
                <UIcon name="i-lucide-check-circle" class="text-green-500" />
                Earn from home
              </div>
              <div class="flex items-center gap-2">
                <UIcon name="i-lucide-check-circle" class="text-green-500" />
                Connect with students worldwide
              </div>
            </div>
          </div>

          <div class="bg-white p-8 rounded-xl border border-border">
            <h3 class="text-xl font-bold text-gray-900 mb-6">
              Apply as a tutor
            </h3>

            <div class="grid gap-4">
              <UInput icon="i-lucide-user" size="lg" placeholder="Full name" />

              <UInput
                icon="i-lucide-mail"
                size="lg"
                placeholder="Email address"
              />

              <UInput
                icon="i-lucide-phone"
                size="lg"
                placeholder="Phone number"
              />

              <UInput
                icon="i-lucide-book"
                size="lg"
                placeholder="Subject you teach"
              />

              <UTextarea
                size="lg"
                placeholder="Tell us about yourself..."
                :rows="4"
              />

              <UButton
                block
                size="xl"
                class="rounded-full mt-4 shadow-lg hover:shadow-xl transition"
              >
                Submit Application
              </UButton>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="pb-16">
      <div class="max-w-7xl mx-auto px-4">
        <div class="bg-gray-950 text-white p-8 rounded-xl text-center">
          <h2 class="text-2xl font-bold">
            Ready to start your teaching journey?
          </h2>
          <p class="mt-3 text-gray-400">
            Join thousands of tutors and make a difference.
          </p>

          <UButton size="xl" class="mt-6 rounded-full"> Join now </UButton>
        </div>
      </div>
    </section>
  </main>
</template>
