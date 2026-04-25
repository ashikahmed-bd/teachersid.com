<script setup>
const year = new Date().getFullYear();

const socials = [
  { icon: "i-simple-icons-facebook", url: "https://www.facebook.com/" },
  { icon: "i-simple-icons-x", url: "https://twitter.com/" },
  { icon: "i-simple-icons-linkedin", url: "https://www.linkedin.com/" },
  { icon: "i-simple-icons-dribbble", url: "https://dribbble.com/" },
  { icon: "i-simple-icons-twitch", url: "https://www.twitch.tv/" },
];

const usefulLinks = [
  "About",
  "Success stories",
  "Online classes",
  "Join our community",
  "Courses",
  "Sign in now",
  "Programs & degrees",
  "How it works",
  "Learning materials",
  "F.A.Q",
];
</script>

<template>
  <footer class="bg-gray-900 text-white">
    <div class="mx-auto max-w-7xl px-4 py-16">
      <div class="grid gap-10 lg:grid-cols-3">
        <div>
          <h5 class="mb-5 text-lg font-bold">Useful links</h5>
          <div class="grid gap-3 sm:grid-cols-2">
            <NuxtLink
              v-for="item in usefulLinks"
              :key="item"
              to="/search-listing"
              class="text-sm text-gray-400 transition hover:text-primary"
            >
              {{ item }}
            </NuxtLink>
          </div>
        </div>

        <div>
          <h5 class="text-lg font-bold">Get mobile app</h5>
          <p class="mt-3 text-sm leading-7 text-gray-400">
            Take education on the go. Get our mobile app for FREE on your Apple
            and Android devices.
          </p>

          <div class="mt-6 flex flex-wrap gap-3">
            <a
              v-for="social in socials"
              :key="social.icon"
              :href="social.url"
              target="_blank"
              class="grid size-10 place-items-center rounded-full bg-white/10 text-gray-300 transition hover:bg-primary hover:text-white"
            >
              <UIcon :name="social.icon" class="size-5" />
            </a>
          </div>

          <div class="mt-5 flex flex-wrap gap-3">
            <a href="#">
              <img src="/ios.png" alt="ios" class="h-12 w-auto" />
            </a>
            <a href="#">
              <img src="/android.png" alt="android" class="h-12 w-auto" />
            </a>
          </div>
        </div>

        <div>
          <h5 class="text-lg font-bold">Signup for newsletter</h5>
          <p class="mt-3 text-sm leading-7 text-gray-400">
            Get updates, new classes, and learning tips directly in your inbox.
          </p>

          <form class="mt-5 flex overflow-hidden rounded-full bg-white p-1">
            <input
              type="email"
              placeholder="Enter email address"
              class="min-w-0 flex-1 bg-transparent px-4 text-sm text-gray-900 outline-none"
            />
            <button
              type="submit"
              class="grid size-11 place-items-center rounded-full bg-primary text-white"
            >
              <UIcon name="i-lucide-send" class="size-5" />
            </button>
          </form>
        </div>
      </div>
    </div>

    <div class="border-t border-white/10">
      <div
        class="mx-auto flex max-w-7xl flex-col gap-4 px-4 py-6 text-sm text-gray-400 sm:px-6 lg:flex-row lg:items-center lg:justify-between lg:px-8"
      >
        <p>© 2021 - {{ year }} All Rights Reserved.</p>

        <div class="flex flex-wrap gap-5">
          <NuxtLink to="/careers" class="hover:text-primary">Careers</NuxtLink>
          <NuxtLink to="/terms" class="hover:text-primary"
            >Terms of use</NuxtLink
          >
          <NuxtLink to="/privacy" class="hover:text-primary"
            >Privacy policy</NuxtLink
          >
          <NuxtLink to="/cookie" class="hover:text-primary"
            >Cookie notice</NuxtLink
          >
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped></style>
