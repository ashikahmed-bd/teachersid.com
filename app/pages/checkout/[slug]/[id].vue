<script setup>
import { ref } from 'vue'
import { useRoute, useRouter } from 'vue-router'

const route = useRoute()
const router = useRouter()

const course = ref({
    id: route.params.id,
    slug: route.params.slug,
    title: 'Class 7 Mathematics Complete Course',
    price: 1500,
    currency: '৳'
})

const methods = ref([
    {
        key: 'bkash',
        name: 'bKash',
        number: '017XXXXXXXX',
        color: 'text-pink-600',
        bg: 'bg-pink-50'
    },
    {
        key: 'nagad',
        name: 'Nagad',
        number: '018XXXXXXXX',
        color: 'text-orange-600',
        bg: 'bg-orange-50'
    },
    {
        key: 'upay',
        name: 'Upay',
        number: '019XXXXXXXX',
        color: 'text-purple-600',
        bg: 'bg-purple-50'
    }
])

const selected = ref(methods.value[0])
const trxId = ref('')
const loading = ref(false)

const copyNumber = async () => {
    await navigator.clipboard.writeText(selected.value.number)
}

const submitPayment = async () => {
    if (!trxId.value) return

    loading.value = true
    await new Promise(r => setTimeout(r, 1200))

    router.push(`/payment/success?course=${course.value.id}`)
}
</script>

<template>
    <main>
        <div class="max-w-6xl mx-auto px-4 py-8 ">
            <div class="grid lg:grid-cols-3 gap-8">
                <div class="lg:col-span-2 space-y-6">

                    <div>
                        <h1 class="text-2xl font-bold">Payment Checkout</h1>
                        <p class="text-sm text-title">
                            Choose payment method and complete transfer
                        </p>
                    </div>

                    <div class="p-5 border border-border rounded-2xl bg-white">
                        <h2 class="text-lg font-bold">{{ course.title }}</h2>
                        <p class="text-gray-500 mt-1">
                            Total: {{ course.currency }} {{ course.price }}
                        </p>
                    </div>

                    <div class="space-y-3">
                        <h3 class="font-semibold text-gray-800">Select Payment Method</h3>
                        <div class="grid md:grid-cols-3 gap-4">
                            <div v-for="m in methods" :key="m.key" @click="selected = m"
                                class="cursor-pointer p-4 rounded-2xl border border-border transition">
                                <div class="flex items-center justify-between">
                                    <span class="font-bold" :class="m.color">
                                        {{ m.name }}
                                    </span>
                                    <span class="w-3 h-3 rounded-full"
                                        :class="selected.key === m.key ? 'bg-primary' : 'bg-gray-300'" />
                                </div>
                                <p class="text-sm text-gray-500 mt-2">
                                    {{ m.number }}
                                </p>
                            </div>
                        </div>
                    </div>

                    <div class="p-5 border border-border rounded-2xl bg-gray-50 space-y-3">
                        <h3 class="font-semibold">Payment Instructions</h3>
                        <div class="flex justify-between text-sm">
                            <span>Method</span>
                            <span class="font-semibold">{{ selected.name }}</span>
                        </div>
                        <div class="flex justify-between text-sm items-center">
                            <span>Number</span>
                            <div class="flex items-center gap-2">
                                <span class="font-semibold">
                                    {{ selected.number }}
                                </span>
                                <button class="text-blue-600 text-sm" @click="copyNumber">
                                    Copy
                                </button>
                            </div>
                        </div>
                        <p class="text-xs text-gray-500">
                            Send money to this number and enter transaction ID below.
                        </p>
                    </div>
                </div>

                <div class="lg:col-span-1">
                    <div class="p-6 border border-border rounded-2xl bg-white sticky top-24">
                        <h3 class="font-bold text-lg mb-4">Confirm Payment</h3>
                        <div class="space-y-2">
                            <label class="text-sm text-gray-500">
                                Transaction ID
                            </label>
                            <input v-model="trxId" type="text" placeholder="Enter transaction ID"
                                class="w-full border border-border rounded-xl px-4 py-3 focus:ring focus:outline-none" />
                        </div>
                        <div class="mt-4">
                            <label class="text-sm text-gray-500">
                                Screenshot (optional)
                            </label>
                            <input type="file" class="w-full mt-2 text-sm" />
                        </div>
                        <UButton block size="xl" class="mt-6" :loading="loading" @click="submitPayment">
                            Submit Payment
                        </UButton>
                        <p class="text-xs text-gray-400 mt-3 text-center">
                            Verification within 1–2 hours
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </main>

</template>