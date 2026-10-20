<script>
export default {
    props: ['receivedproducts', 'totalAll'],
    emits: ['gotoOrder', 'checkout', 'minus'],

    data() {
        return {
            minusPrice: null,
        }
    },

    methods: {
        checkoutBtn(index, price, name, img) {
            alert('Ordered Successfully')

            this.$emit('gotoOrder', {
                price: price,
                name: name,
                img: img
            })

            this.$emit('minus', this.minusPrice = price)

            this.$emit('checkout', {
                price: price,
                name: name,
                img: img
            })

            this.receivedproducts.splice(index, 1)
        }
    }
}
</script>

<template>
    <div class="min-h-screen w-full px-4 py-6 sm:px-6 md:px-10 lg:px-16 xl:px-28">
        <!-- Top Spacing -->
        <div class="h-16 sm:h-20 md:h-28"></div>

        <!-- Header -->
        <div class="flex flex-col gap-3 py-5 sm:flex-row sm:items-center sm:justify-between">
            <h1 class="text-2xl font-serif italic sm:text-3xl">
                My Cart
            </h1>

            <h1 class="text-xl font-serif font-semibold sm:text-2xl md:text-3xl">
                Total: ₱ {{ Number(totalAll || 0).toLocaleString('en-PH', {
                    minimumFractionDigits: 2,
                    maximumFractionDigits: 2
                }) }}
            </h1>
        </div>

        <!-- Cart Container -->
        <div class="w-full rounded-lg bg-[#D9D9D9] p-3 sm:p-5 md:p-6">
            <!-- Empty Cart -->
            <div v-if="!receivedproducts || receivedproducts.length === 0"
                class="flex min-h-60 flex-col items-center justify-center gap-3 text-center sm:min-h-80">
                <p class="text-lg font-semibold text-gray-600 sm:text-xl">
                    Your cart is empty.
                </p>

                <p class="text-sm text-gray-500 sm:text-base">
                    Add some products to get started!
                </p>
            </div>

            <!-- Cart Products -->
            <div v-else class="flex flex-col gap-4">
                <div v-for="(put, index) in receivedproducts" :key="put.id ?? `${put.name}-${index}`"
                    class="flex w-full flex-col gap-4 rounded-lg bg-white p-4 shadow-md transition duration-300 hover:shadow-lg sm:flex-row sm:items-center sm:justify-between sm:gap-5">
                    <!-- Product Information -->
                    <div class="flex min-w-0 flex-1 items-center gap-3 sm:gap-4">
                        <img :src="put.img" :alt="put.name"
                            class="h-16 w-16 shrink-0 rounded-md object-cover sm:h-[71px] sm:w-[71px]" />

                        <div class="min-w-0 flex-1">
                            <p class="break-words text-base font-medium sm:text-lg">
                                {{ put.name }}
                            </p>

                            <p class="mt-1 text-base text-gray-600 sm:text-lg">
                                ₱ {{ Number(put.price).toLocaleString('en-PH', {
                                    minimumFractionDigits: 2,
                                    maximumFractionDigits: 2
                                }) }}
                            </p>
                        </div>
                    </div>

                    <!-- Checkout Button -->
                    <button @click="checkoutBtn(index, put.price, put.name, put.img)" type="button"
                        class="w-full shrink-0 cursor-pointer rounded-md bg-amber-900 px-5 py-3 text-sm font-semibold text-white transition duration-300 hover:scale-[1.02] hover:bg-amber-800 active:scale-95 sm:w-auto sm:py-2.5 sm:text-base">
                        Check Out
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>