<script setup>
const plans = [
  {
    name: "Basic",
    price: "$19",
    desc: "Perfect for students starting out.",
    popular: false,
    features: [
      "Access to verified tutors",
      "3 tutor contact unlocks",
      "Basic search filters",
      "Email support",
    ],
  },
  {
    name: "Standard",
    price: "$49",
    desc: "Best for regular learners.",
    popular: true,
    features: [
      "Access to verified tutors",
      "15 tutor contact unlocks",
      "Advanced search filters",
      "Online booking support",
      "Priority support",
    ],
  },
  {
    name: "Premium",
    price: "$99",
    desc: "For families and serious learners.",
    popular: false,
    features: [
      "Unlimited tutor browsing",
      "40 tutor contact unlocks",
      "Featured tutor matching",
      "Priority booking",
      "Dedicated support",
    ],
  },
];

const faqs = [
  {
    label: "Can I change my plan later?",
    content:
      "Yes, you can upgrade or downgrade your plan anytime from your account dashboard.",
  },
  {
    label: "Do I get access to tutor contact details?",
    content: "Yes, each plan includes a number of tutor contact unlocks.",
  },
  {
    label: "Is there any free trial?",
    content:
      "You can browse tutors for free. Contact unlocks require a paid plan.",
  },
];
</script>

<template>
  <main class="bg-gray-50">
    <!-- Hero -->
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
            Pricing
          </UBadge>

          <h1
            class="text-4xl font-bold tracking-tight text-gray-900 sm:text-5xl"
          >
            Simple pricing for smarter learning
          </h1>

          <p class="mt-5 text-base leading-7 text-gray-600 sm:text-lg">
            Choose the right plan to connect with expert tutors and start
            learning faster.
          </p>
        </div>
      </div>
    </section>

    <!-- Pricing Cards -->
    <section class="-mt-8 relative z-10 pb-16 sm:pb-20">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div class="grid gap-6 lg:grid-cols-3">
          <div
            v-for="plan in plans"
            :key="plan.name"
            class="relative rounded-3xl bg-white p-6 border border-border transition hover:-translate-y-1"
            :class="plan.popular ? 'ring-2 ring-primary ' : ''"
          >
            <div
              v-if="plan.popular"
              class="absolute right-5 top-5 rounded-full bg-primary px-3 py-1 text-xs font-semibold text-white"
            >
              Popular
            </div>

            <h3 class="text-xl font-bold text-gray-900">
              {{ plan.name }}
            </h3>

            <p class="mt-2 text-sm text-gray-500">
              {{ plan.desc }}
            </p>

            <div class="mt-6 flex items-end gap-1">
              <span class="text-4xl font-bold text-gray-900">
                {{ plan.price }}
              </span>
              <span class="mb-1 text-sm text-gray-500">/month</span>
            </div>

            <UButton
              block
              size="xl"
              class="mt-6 rounded-full"
              :variant="plan.popular ? 'solid' : 'soft'"
              color="primary"
            >
              Get started
            </UButton>

            <div class="mt-7 border-t border-gray-100 pt-6">
              <p class="mb-4 text-sm font-semibold text-gray-900">
                What’s included:
              </p>

              <ul class="space-y-3">
                <li
                  v-for="feature in plan.features"
                  :key="feature"
                  class="flex gap-2 text-sm text-gray-600"
                >
                  <UIcon
                    name="i-lucide-check"
                    class="mt-0.5 size-4 text-green-500"
                  />
                  <span>{{ feature }}</span>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="pb-16 sm:pb-20">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div class="grid gap-6 lg:grid-cols-[1fr_420px]">
          <div class="rounded-xl bg-white p-6 border border-border sm:p-8">
            <h2 class="text-2xl font-bold text-gray-900">
              Why choose our plans?
            </h2>

            <div class="mt-6 grid gap-4 sm:grid-cols-2">
              <div class="rounded-2xl bg-gray-50 p-5">
                <UIcon
                  name="i-lucide-shield-check"
                  class="size-7 text-primary"
                />
                <h3 class="mt-3 font-bold text-gray-900">Verified tutors</h3>
                <p class="mt-2 text-sm leading-6 text-gray-600">
                  Every tutor profile is reviewed for trust and quality.
                </p>
              </div>

              <div class="rounded-2xl bg-gray-50 p-5">
                <UIcon
                  name="i-lucide-calendar-check"
                  class="size-7 text-primary"
                />
                <h3 class="mt-3 font-bold text-gray-900">Easy booking</h3>
                <p class="mt-2 text-sm leading-6 text-gray-600">
                  Book online or home tuition with flexible scheduling.
                </p>
              </div>

              <div class="rounded-2xl bg-gray-50 p-5">
                <UIcon name="i-lucide-search" class="size-7 text-primary" />
                <h3 class="mt-3 font-bold text-gray-900">Smart search</h3>
                <p class="mt-2 text-sm leading-6 text-gray-600">
                  Filter tutors by subject, price, rating, location, and more.
                </p>
              </div>

              <div class="rounded-2xl bg-gray-50 p-5">
                <UIcon name="i-lucide-headphones" class="size-7 text-primary" />
                <h3 class="mt-3 font-bold text-gray-900">Helpful support</h3>
                <p class="mt-2 text-sm leading-6 text-gray-600">
                  Get support when choosing or contacting tutors.
                </p>
              </div>
            </div>
          </div>

          <div class="rounded-xl bg-gray-950 p-6 text-white sm:p-8">
            <UBadge color="primary" variant="solid" class="rounded-full">
              For Tutors
            </UBadge>

            <h2 class="mt-5 text-2xl font-bold">
              Want to teach on our platform?
            </h2>

            <p class="mt-3 text-sm leading-7 text-gray-400">
              Create your tutor profile, receive student requests, and grow your
              teaching business.
            </p>

            <UButton size="xl" to="/apply-tutor" class="mt-6 rounded-full">
              Become a tutor
              <UIcon name="i-lucide-arrow-right" class="ml-1 size-4" />
            </UButton>
          </div>
        </div>
      </div>
    </section>

    <section class="bg-white py-16 sm:py-20">
      <div class="mx-auto max-w-3xl px-4 sm:px-6 lg:px-8">
        <div class="mb-8 text-center">
          <h2 class="text-3xl font-bold text-gray-900">
            Frequently asked questions
          </h2>
          <p class="mt-2 text-gray-600">
            Everything you need to know before choosing a plan.
          </p>
        </div>

        <UAccordion :items="faqs" />
      </div>
    </section>
  </main>
</template>
