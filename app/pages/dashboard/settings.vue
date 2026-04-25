<script setup>
const tabs = [
  { label: "Profile", icon: "i-lucide-user", slot: "profile" },
  { label: "Security", icon: "i-lucide-lock", slot: "security" },
  { label: "Notifications", icon: "i-lucide-bell", slot: "notifications" },
];
</script>

<template>
  <main class="max-w-5xl mx-auto px-4 py-6">
    <div class="mb-6">
      <h1 class="text-2xl font-bold text-gray-900">Settings</h1>
      <p class="text-sm text-gray-500">
        Manage your profile, password, and preferences.
      </p>
    </div>

    <UTabs
      :items="tabs"
      class="rounded-3xl bg-white p-5 shadow-sm ring-1 ring-gray-100"
      :ui="{
        list: 'mb-6 rounded-full bg-gray-100 p-1',
      }"
    >
      <!-- Profile -->
      <template #profile>
        <div class="space-y-6">
          <div class="flex flex-col gap-4 sm:flex-row sm:items-center">
            <img
              src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?w=120&h=120&fit=crop"
              class="size-20 rounded-3xl object-cover"
              alt="profile"
            />

            <div>
              <h3 class="font-bold text-gray-900">Profile photo</h3>
              <p class="text-sm text-gray-500">Upload a clear profile image.</p>

              <div class="mt-3 flex gap-2">
                <UButton size="sm" class="rounded-full"> Upload </UButton>
                <UButton
                  size="sm"
                  variant="soft"
                  color="neutral"
                  class="rounded-full"
                >
                  Remove
                </UButton>
              </div>
            </div>
          </div>

          <div class="grid gap-4 sm:grid-cols-2">
            <UInput label="Full name" placeholder="John Doe" />
            <UInput label="Email address" placeholder="john@example.com" />
            <UInput label="Phone number" placeholder="+880 1XXXXXXXXX" />
            <UInput label="Education level" placeholder="Class 9" />
          </div>

          <UTextarea
            label="About"
            placeholder="Tell us about yourself..."
            :rows="4"
            class="w-full"
          />

          <UButton size="xl" class="rounded-full"> Save Changes </UButton>
        </div>
      </template>

      <!-- Security -->
      <template #security>
        <div class="space-y-5">
          <div class="grid gap-4 sm:grid-cols-2">
            <UInput
              type="password"
              label="Current password"
              placeholder="••••••••"
            />
            <UInput
              type="password"
              label="New password"
              placeholder="••••••••"
            />
            <UInput
              type="password"
              label="Confirm password"
              placeholder="••••••••"
            />
          </div>

          <div class="rounded-2xl bg-gray-50 p-5">
            <h3 class="font-bold text-gray-900">Two-factor authentication</h3>
            <p class="mt-1 text-sm text-gray-500">
              Add extra security to your student account.
            </p>

            <div class="mt-4">
              <USwitch label="Enable 2FA" />
            </div>
          </div>

          <UButton size="xl" class="rounded-full"> Update Password </UButton>
        </div>
      </template>

      <!-- Notifications -->
      <template #notifications>
        <div class="space-y-4">
          <div class="rounded-2xl bg-gray-50 p-5">
            <USwitch label="Class reminders" default-value />
            <p class="mt-1 text-sm text-gray-500">
              Receive reminders before upcoming classes.
            </p>
          </div>

          <div class="rounded-2xl bg-gray-50 p-5">
            <USwitch label="Tutor messages" default-value />
            <p class="mt-1 text-sm text-gray-500">
              Get notified when tutors send new messages.
            </p>
          </div>

          <div class="rounded-2xl bg-gray-50 p-5">
            <USwitch label="Payment updates" />
            <p class="mt-1 text-sm text-gray-500">
              Receive payment and invoice notifications.
            </p>
          </div>

          <UButton size="xl" class="rounded-full"> Save Preferences </UButton>
        </div>
      </template>
    </UTabs>
  </main>
</template>
