<script>
export default {
    props: ['toCategories', 'categori'],
    emits: ['close', 'addMe', 'addMe2bed', 'addMe2dining', 'select'],

    data() {
        return {
            product: '',
            name: '',
            price: 0,
            category: ['living', 'bedroom', 'dining']
        }
    },

    methods: {
        closeModal() {
            this.$emit('close', false)
        },

        addProduct() {
            if (!this.product.trim() || !this.name.trim() || Number(this.price) <= 0) {
                alert('Please fill in all fields with valid information.')
                return
            }

            this.$emit(
                'addMe',
                {
                    name: this.name,
                    img: this.product,
                    price: Number(this.price)
                },
                this.categori
            )

            alert('Added Successfully')
            this.closeModal()
            this.$emit('select', this.categori)
        }
    }
}
</script>

<template>
    <!-- Background Overlay -->
    <div @click="closeModal"
        class="fixed inset-0 z-50 flex h-dvh w-full items-center justify-center bg-black/40 p-4 backdrop-blur-sm"></div>

    <!-- Modal Container -->
    <div class="fixed inset-0 z-[60] flex h-dvh w-full items-center justify-center overflow-y-auto p-4 sm:p-6">
        <div class="my-auto flex max-h-[90dvh] w-full max-w-lg flex-col overflow-y-auto rounded-xl bg-white p-4 shadow-2xl sm:p-6 md:p-8"
            @click.stop>
            <!-- Modal Content -->
            <div class="flex flex-col gap-5">

                <!-- Title -->
                <h1 class="text-center text-xl font-semibold text-orange-800 sm:text-2xl">
                    Add Product
                </h1>

                <!-- Image Input -->
                <input v-model="product"
                    class="w-full min-w-0 rounded-lg border border-gray-300 px-4 py-3 text-base outline-none transition focus:border-orange-400 focus:ring-2 focus:ring-orange-200 sm:text-lg"
                    type="text" name="productImage" placeholder="Image URL" />

                <!-- Product Name Input -->
                <input v-model="name"
                    class="w-full min-w-0 rounded-lg border border-gray-300 px-4 py-3 text-base outline-none transition focus:border-orange-400 focus:ring-2 focus:ring-orange-200 sm:text-lg"
                    type="text" name="productName" placeholder="Product name" />

                <!-- Product Price Input -->
                <input v-model="price"
                    class="w-full min-w-0 rounded-lg border border-gray-300 px-4 py-3 text-base outline-none transition focus:border-orange-400 focus:ring-2 focus:ring-orange-200 sm:text-lg"
                    type="number" name="productPrice" min="0" step="0.01" placeholder="Product price" />

                <!-- Product Category -->
                <input :value="categori"
                    class="w-full min-w-0 rounded-lg border border-gray-300 bg-gray-100 px-4 py-3 text-base text-gray-600 outline-none sm:text-lg"
                    type="text" name="productCategory" placeholder="Product category" readonly />

                <!-- Action Buttons -->
                <div class="flex w-full flex-col-reverse gap-3 pt-2 sm:flex-row sm:justify-end">
                    <button @click="closeModal" type="button"
                        class="w-full cursor-pointer rounded-full bg-blue-900/10 px-6 py-3 text-base font-semibold text-blue-950 transition duration-300 hover:bg-blue-900/20 sm:w-auto sm:text-lg">
                        Cancel
                    </button>

                    <button @click="addProduct" type="button"
                        class="w-full cursor-pointer rounded-full bg-orange-400/30 px-8 py-3 text-base font-semibold text-orange-700 transition duration-300 hover:bg-orange-400/50 sm:w-auto sm:text-lg">
                        Add Product
                    </button>
                </div>

            </div>
        </div>
    </div>
</template>