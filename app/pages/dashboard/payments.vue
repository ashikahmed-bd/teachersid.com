<script setup>
const payments = [
  {
    id: "#PAY-1024",
    title: "Mathematics Lesson",
    tutor: "Armando Weber",
    amount: "$120.00",
    method: "Visa •••• 4242",
    date: "Apr 26, 2026",
    status: "Paid",
  },
  {
    id: "#PAY-1025",
    title: "English Speaking Class",
    tutor: "Gwendolyn Parker",
    amount: "$85.00",
    method: "Mastercard •••• 8891",
    date: "Apr 22, 2026",
    status: "Pending",
  },
  {
    id: "#PAY-1026",
    title: "Computer Science Basics",
    tutor: "Dwayne Garrett",
    amount: "$150.00",
    method: "PayPal",
    date: "Apr 18, 2026",
    status: "Failed",
  },
];

const stats = [
  { label: "Total Spent", value: "$2,450", icon: "i-lucide-wallet" },
  { label: "Paid Invoices", value: "18", icon: "i-lucide-check-circle" },
  { label: "Pending", value: "03", icon: "i-lucide-clock" },
];
</script>

<template>
  <main class="max-w-5xl mx-auto px-4 py-6">
    <!-- Header -->
    <div
      class="mb-6 flex flex-col gap-4 sm:flex-row sm:items-center sm:justify-between"
    >
      <div>
        <h1 class="text-2xl font-bold text-gray-900">Payments</h1>
        <p class="text-sm text-gray-500">
          Track your payment history and invoices.
        </p>
      </div>

      <UButton class="rounded-full">
        <UIcon name="i-lucide-download" class="mr-1 size-4" />
        Download Report
      </UButton>
    </div>

    <!-- Stats -->
    <div class="mb-6 grid gap-4 sm:grid-cols-3">
      <div
        v-for="stat in stats"
        :key="stat.label"
        class="rounded-3xl bg-white p-5 shadow-sm ring-1 ring-gray-100"
      >
        <div class="flex items-center justify-between">
          <div>
            <p class="text-sm text-gray-500">{{ stat.label }}</p>
            <h3 class="mt-2 text-2xl font-bold text-gray-900">
              {{ stat.value }}
            </h3>
          </div>

          <div
            class="grid size-12 place-items-center rounded-2xl bg-primary/10 text-primary"
          >
            <UIcon :name="stat.icon" class="size-6" />
          </div>
        </div>
      </div>
    </div>

    <!-- Filters -->
    <div
      class="mb-6 grid gap-3 rounded-3xl bg-white p-4 shadow-sm ring-1 ring-gray-100 md:grid-cols-[1fr_180px_180px]"
    >
      <UInput
        icon="i-lucide-search"
        size="lg"
        placeholder="Search payments..."
      />

      <USelect
        size="lg"
        placeholder="Status"
        :items="['All', 'Paid', 'Pending', 'Failed']"
      />

      <USelect
        size="lg"
        placeholder="Method"
        :items="['All', 'Visa', 'Mastercard', 'PayPal']"
      />
    </div>

    <!-- Payment List -->
    <div class="space-y-4">
      <article
        v-for="payment in payments"
        :key="payment.id"
        class="rounded-3xl bg-white p-5 shadow-sm ring-1 ring-gray-100 transition hover:-translate-y-1 hover:shadow-lg"
      >
        <div
          class="flex flex-col gap-5 lg:flex-row lg:items-center lg:justify-between"
        >
          <div>
            <div class="mb-2 flex flex-wrap items-center gap-2">
              <UBadge color="neutral" variant="soft" class="rounded-full">
                {{ payment.id }}
              </UBadge>

              <UBadge
                :color="
                  payment.status === 'Paid'
                    ? 'success'
                    : payment.status === 'Pending'
                      ? 'warning'
                      : 'error'
                "
                variant="soft"
                class="rounded-full"
              >
                {{ payment.status }}
              </UBadge>
            </div>

            <h3 class="text-lg font-bold text-gray-900">
              {{ payment.title }}
            </h3>

            <p class="mt-1 text-sm text-gray-500">Tutor: {{ payment.tutor }}</p>

            <div class="mt-3 flex flex-wrap gap-4 text-sm text-gray-500">
              <span class="flex items-center gap-1">
                <UIcon name="i-lucide-calendar" class="size-4" />
                {{ payment.date }}
              </span>

              <span class="flex items-center gap-1">
                <UIcon name="i-lucide-credit-card" class="size-4" />
                {{ payment.method }}
              </span>
            </div>
          </div>

          <div class="lg:text-right">
            <p class="text-sm text-gray-500">Amount</p>
            <h4 class="text-2xl font-bold text-gray-900">
              {{ payment.amount }}
            </h4>

            <div class="mt-3 flex gap-2 lg:justify-end">
              <UButton
                size="sm"
                variant="soft"
                color="neutral"
                class="rounded-full"
              >
                Invoice
              </UButton>

              <UButton
                size="sm"
                variant="soft"
                color="primary"
                class="rounded-full"
              >
                Details
              </UButton>
            </div>
          </div>
        </div>
      </article>
    </div>
  </main>
</template>
