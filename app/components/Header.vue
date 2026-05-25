<script setup>
const isOpen = ref(false);

const navItems = [
  { label: "হোম", to: "/" },
  { label: "কোর্সসমূহ", to: "/courses" },
  { label: "শিক্ষকগণ", to: "/tutors" },
  { label: "ব্লগ", to: "/blog" },
  { label: "যোগাযোগ", to: "/pricing" },
  { label: "যোগাযোগ", to: "/contact" },
];

const items = [
  [
    {
      label: "Dashboard",
      to: "/dashboard",
      icon: "i-lucide-layout-dashboard",
    },
    {
      label: "My Classes",
      to: "/dashboard/classes",
      icon: "i-lucide-video",
    },
    {
      label: "My Tutors",
      to: "/dashboard/tutors",
      icon: "i-lucide-users",
    },
    {
      label: "Bookings",
      to: "/dashboard/bookings",
      icon: "i-lucide-calendar-check",
    },

    {
      label: "Saved Tutors",
      to: "/dashboard/saved",
      icon: "i-lucide-heart",
    },
    {
      label: "Payments",
      to: "/dashboard/payments",
      icon: "i-lucide-credit-card",
    },
    {
      label: "Reviews",
      to: "/dashboard/reviews",
      icon: "i-lucide-star",
    },
  ],
  [
    {
      label: "Profile Settings",
      icon: "i-lucide-user",
      to: "/dashboard/settings",
    },
    {
      label: "Logout",
      icon: "i-lucide-log-out",
      click: () => console.log("logout"),
    },
  ],
];
</script>

<template>
  <header class="sticky top-0 z-50 border-b border-gray-100 bg-white/80 backdrop-blur-xl">
    <div class="max-w-7xl mx-auto w-full px-4 sm:px-6 lg:px-8">
      <div class="h-20 flex items-center justify-between">
        <a href="/" class="flex items-center shrink-0">
          <img src="/logo.svg" alt="logo" class="h-10 w-auto object-contain" />
        </a>

        <nav class="hidden lg:flex items-center gap-2 px-2 py-2">
          <NuxtLink v-for="item in navItems" :key="item.label" :to="item.to"
            class="px-4 py-2 text-base font-semibold text-body transition hover:text-primary">
            {{ item.label }}
          </NuxtLink>
        </nav>

        <template v-if="false">
          <div class="flex items-center gap-3">
            <button
              class="hidden md:grid size-10 place-items-center rounded-full border border-gray-100 bg-white text-gray-700 transition hover:bg-gray-50 hover:text-primary">
              <UIcon name="i-lucide-heart" class="size-5" />
            </button>

            <button
              class="hidden md:grid size-10 place-items-center rounded-full border border-gray-100 bg-white text-gray-700 transition hover:bg-gray-50 hover:text-primary">
              <UIcon name="i-lucide-bell" class="size-5" />
            </button>

            <UDropdownMenu :items="items" :ui="{
              item: 'py-2 px-4 text-base w-60',
              label: 'text-sm font-medium',
            }">
              <button type="button" class="cursor-pointer">
                <img class="size-10 rounded-full object-cover"
                  src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?w=100&h=100&fit=crop"
                  alt="profile" />
              </button>
            </UDropdownMenu>

            <!-- Mobile Button -->
            <button
              class="lg:hidden grid size-10 place-items-center rounded-full border border-gray-100 bg-white text-gray-700 shadow-sm"
              @click="isOpen = !isOpen">
              <UIcon :name="isOpen ? 'i-lucide-x' : 'i-lucide-menu'" class="size-5" />
            </button>
          </div>
        </template>

        <template v-else>
          <div class="flex items-center gap-4">
            
            <button
              class="hidden md:flex px-6 py-2 rounded border border-blue-600 text-blue-600 font-semibold hover:bg-blue-50 transition">
              লগইন
            </button>

            <button
              class="px-6 py-2 rounded bg-blue-600 text-white font-semibold shadow-lg shadow-blue-200 hover:bg-blue-700 transition">
              সাইন আপ
            </button>
          </div>
        </template>
      </div>

      <!-- Mobile Menu -->
      <Transition enter-active-class="transition duration-200 ease-out" enter-from-class="opacity-0 -translate-y-2"
        enter-to-class="opacity-100 translate-y-0" leave-active-class="transition duration-150 ease-in"
        leave-from-class="opacity-100 translate-y-0" leave-to-class="opacity-0 -translate-y-2">
        <div v-if="isOpen" class="lg:hidden pb-4">
          <nav class="rounded-3xl border border-gray-100 bg-white p-3 shadow-xl shadow-gray-100">
            <NuxtLink v-for="item in navItems" :key="item.label" :to="item.to"
              class="flex items-center justify-between rounded-2xl px-4 py-3 text-sm font-semibold text-gray-700 transition hover:bg-gray-50 hover:text-primary"
              @click="isOpen = false">
              <span>{{ item.label }}</span>
              <UIcon name="i-lucide-chevron-right" class="size-4" />
            </NuxtLink>

            <div class="mt-3 flex items-center gap-3 border-t border-gray-100 pt-3">
              <button
                class="flex flex-1 items-center justify-center gap-2 rounded-2xl bg-gray-50 px-4 py-3 text-sm font-semibold text-gray-700">
                <UIcon name="i-lucide-heart" class="size-5" />
                Wishlist
              </button>

              <button
                class="flex flex-1 items-center justify-center gap-2 rounded-2xl bg-gray-50 px-4 py-3 text-sm font-semibold text-gray-700">
                <UIcon name="i-lucide-bell" class="size-5" />
                Alerts
              </button>
            </div>
          </nav>
        </div>
      </Transition>
    </div>
  </header>
</template>
