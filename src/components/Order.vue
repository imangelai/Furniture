<script>
export default {
    props: ['orderlist'],

    data() {
        return {
            displayButton: true,
        }
    },

    methods: {
        cancel(index) {
            this.orderlist.splice(index, 1)
        }
    },

    mounted() {
        console.log(this.orderlist)

        setTimeout(() => {
            this.displayButton = false
        }, 10000)
    }
}
</script>

<template>
    <div class="min-h-screen w-full px-4 py-8 sm:px-6 lg:px-12 xl:px-20">
        <div class="h-16 sm:h-24 lg:h-32"></div>

        <h1 class="py-5 text-2xl font-serif italic sm:text-3xl">
            My Orders
        </h1>

        <div class="flex w-full justify-center">
            <div class="h-fit min-h-75 w-full rounded-lg bg-[#D9D9D9] p-4 sm:p-6 lg:p-8">

                <div
                    v-if="!orderlist || orderlist.length === 0"
                    class="flex min-h-62.5 flex-col items-center justify-center text-center"
                >
                    <p class="text-lg font-semibold text-gray-700 sm:text-xl">
                        No orders yet.
                    </p>
                    <p class="mt-2 text-sm text-gray-500 sm:text-base">
                        Your orders will appear here.
                    </p>
                </div>

                <div v-else class="flex flex-col gap-4">
                    <div
                        v-for="(order, index) in orderlist"
                        :key="order.id ?? index"
                        class="flex w-full flex-col gap-4 rounded-lg bg-white p-4 shadow-lg sm:flex-row sm:items-center sm:justify-between sm:gap-5 sm:px-5"
                    >
                        <div class="flex min-w-0 items-center gap-4">
                            <img
                                :src="order.img"
                                :alt="order.name"
                                class="h-16 w-16 shrink-0 rounded-md object-cover sm:h-17.75 sm:w-17.75"
                            >

                            <p class="wrap-break-word text-base font-semibold sm:text-lg">
                                {{ order.name }}
                            </p>
                        </div>

                        <div class="flex items-center justify-between gap-4 sm:justify-end">
                            <p class="text-base text-gray-600 sm:text-lg">
                                ₱ {{ order.price }}
                            </p>

                            <button
                                v-if="displayButton"
                                @click="cancel(index)"
                                class="h-9 w-24 shrink-0 cursor-pointer rounded-md bg-black px-3 text-sm text-white transition duration-300 hover:scale-105 hover:bg-amber-800 sm:w-31.25 sm:text-base"
                            >
                                Cancel
                            </button>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>