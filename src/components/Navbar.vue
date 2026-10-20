<script>
export default {
    emits: ['GoTo', 'open'],

    data() {
        return {
            searchQuery: '',
            selectedCategory: '',
            mobileMenuOpen: false,
        };
    },

    methods: {
        navi(page) {
            this.$emit('GoTo', page);
            this.mobileMenuOpen = false;
        },

        searchFurniture() {
            this.$emit('open', this.searchQuery);
        },

        goToCategory() {
            if (this.selectedCategory) {
                this.$emit('GoTo', 'Products');
                this.mobileMenuOpen = false;
            }
        },
    },
};
</script>

<template>
    <nav class="fixed top-0 z-40 w-full">

        <!-- Main Header -->
        <div class="w-full bg-yellow-900 px-4 py-3 sm:px-6 lg:px-8 xl:px-12">

            <div class="mx-auto flex max-w-[1600px] flex-wrap items-center justify-between gap-3">

                <!-- Logo -->
                <div class="shrink-0">
                    <img src="https://i.pinimg.com/736x/8b/30/18/8b3018954cdc4f0f11e1a382c0e9dd38.jpg"
                        alt="Furniture Store Logo"
                        class="h-12 w-12 rounded-full object-cover sm:h-14 sm:w-14 lg:h-16 lg:w-16" />
                </div>

                <!-- Desktop Search and Categories -->
                <div class="hidden flex-1 items-center justify-center gap-3 lg:flex xl:gap-5">

                    <!-- Categories -->
                    <div class="flex h-10 w-40 shrink-0 items-center rounded-md bg-white px-3 xl:w-48">
                        <select v-model="selectedCategory" @change="goToCategory" aria-label="Select furniture category"
                            class="w-full cursor-pointer bg-transparent text-sm font-semibold outline-none">
                            <option value="">CATEGORIES</option>
                            <option value="Living Room">Living Room</option>
                            <option value="Bedroom">Bedroom</option>
                            <option value="Dining Room">Dining Room</option>
                        </select>
                    </div>

                    <!-- Search -->
                    <form @submit.prevent="searchFurniture" class="flex min-w-0 max-w-xl flex-1 items-center gap-2">
                        <div class="flex h-10 min-w-0 flex-1 items-center rounded-md bg-white px-3">

                            <svg class="h-5 w-5 shrink-0 fill-gray-600" xmlns="http://www.w3.org/2000/svg"
                                viewBox="0 0 640 640" aria-hidden="true">
                                <path
                                    d="M480 272C480 317.9 465.1 360.3 440 394.7L566.6 521.4C579.1 533.9 579.1 554.2 566.6 566.7C554.1 579.2 533.8 579.2 521.3 566.7L394.7 440C360.3 465.1 317.9 480 272 480C157.1 480 64 386.9 64 272C64 157.1 157.1 64 272 64C386.9 64 480 157.1 480 272zM272 416C351.5 416 416 351.5 416 272C416 192.5 351.5 128 272 128C192.5 128 128 192.5 128 272C128 351.5 192.5 416 272 416z" />
                            </svg>

                            <input v-model="searchQuery" type="search" placeholder="Search furniture"
                                aria-label="Search furniture"
                                class="h-10 w-full min-w-0 rounded-md px-3 text-sm outline-none" />
                        </div>

                        <button type="submit"
                            class="h-10 shrink-0 rounded-md border border-white px-4 text-sm text-white transition duration-300 hover:scale-105 hover:bg-white hover:text-yellow-900 xl:px-6">
                            Search
                        </button>
                    </form>
                </div>

                <!-- Cart and Orders -->
                <div class="flex shrink-0 items-center gap-2 sm:gap-3">

                    <button @click="navi('Cart')" type="button"
                        class="flex h-10 items-center justify-center gap-1.5 rounded-md bg-yellow-600 px-2.5 transition duration-300 hover:scale-105 hover:bg-yellow-400 sm:gap-2 sm:px-4">
                        <svg class="h-5 w-5 shrink-0 fill-white sm:h-6 sm:w-6" xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 640 640" aria-hidden="true">
                            <path
                                d="M331.8 504.4C331.1 487.5 339.7 471.7 354.2 463C368.7 454.4 386.7 454.5 401.2 463.2C415.6 471.9 424.1 487.8 423.3 504.7C424 521.6 415.4 537.4 400.9 546.1C386.4 554.7 368.4 554.6 353.9 545.9C339.5 537.2 331 521.3 331.8 504.4zM169.4 458.9C152.6 458.2 136.7 466.7 128.1 481.2C119.5 495.7 119.6 513.7 128.3 528.1C137 542.6 152.9 551 169.7 550.2C186.5 550.9 202.4 542.4 211 527.9C219.6 513.4 219.5 495.4 210.8 481C202.1 466.5 186.2 458.1 169.4 458.9zM461.1 188.9C158.9 188.9 81.9 176.1 0 89.7C34.4 141.4 53.3 238.6 373.1 233.9C706.4 228.9 503.1 320 443.9 422.8C630.6 256.1 763.3 188.9 461.1 188.9z" />
                        </svg>

                        <span class="text-xs font-semibold text-white sm:text-sm">
                            CART
                        </span>
                    </button>

                    <button @click="navi('Order')" type="button"
                        class="flex h-10 items-center justify-center rounded-md bg-yellow-600 px-2.5 text-xs font-semibold text-white transition duration-300 hover:scale-105 hover:bg-yellow-400 sm:px-4 sm:text-sm">
                        MY ORDER
                    </button>

                    <!-- Mobile Menu Toggle -->
                    <button @click="mobileMenuOpen = !mobileMenuOpen" type="button"
                        class="flex h-10 w-10 items-center justify-center rounded-md border border-white text-white transition hover:bg-yellow-700 lg:hidden"
                        :aria-expanded="mobileMenuOpen" aria-label="Toggle navigation menu">
                        <svg v-if="!mobileMenuOpen" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none"
                            viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16" />
                        </svg>

                        <svg v-else xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24"
                            stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
                        </svg>
                    </button>
                </div>

                <!-- Mobile Search -->
                <form @submit.prevent="searchFurniture" class="flex w-full items-center gap-2 lg:hidden">
                    <div class="flex h-10 min-w-0 flex-1 items-center rounded-md bg-white px-3">
                        <svg class="h-5 w-5 shrink-0 fill-gray-600" xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 640 640" aria-hidden="true">
                            <path
                                d="M480 272C480 317.9 465.1 360.3 440 394.7L566.6 521.4C579.1 533.9 579.1 554.2 566.6 566.7C554.1 579.2 533.8 579.2 521.3 566.7L394.7 440C360.3 465.1 317.9 480 272 480C157.1 480 64 386.9 64 272C64 157.1 157.1 64 272 64C386.9 64 480 157.1 480 272zM272 416C351.5 416 416 351.5 416 272C416 192.5 351.5 128 272 128C192.5 128 128 192.5 128 272C128 351.5 192.5 416 272 416z" />
                        </svg>

                        <input v-model="searchQuery" type="search" placeholder="Search furniture"
                            aria-label="Search furniture"
                            class="h-10 w-full min-w-0 rounded-md px-3 text-sm outline-none" />
                    </div>

                    <button type="submit"
                        class="h-10 shrink-0 rounded-md border border-white px-4 text-sm text-white transition hover:bg-white hover:text-yellow-900">
                        Search
                    </button>
                </form>

            </div>
        </div>

        <!-- Desktop Navigation -->
        <div class="hidden h-12 items-center justify-center bg-white shadow-lg lg:flex">
            <div class="flex h-full w-full max-w-[1400px] items-center justify-evenly gap-4 px-6">

                <button @click="navi('Home')"
                    class="whitespace-nowrap text-base transition hover:text-yellow-700 xl:text-lg">
                    Home
                </button>

                <button @click="navi('About')"
                    class="whitespace-nowrap text-base transition hover:text-yellow-700 xl:text-lg">
                    About Us
                </button>

                <button @click="navi('Contact')"
                    class="whitespace-nowrap text-base transition hover:text-yellow-700 xl:text-lg">
                    Contact Us
                </button>

                <button @click="navi('Products')"
                    class="whitespace-nowrap text-base transition hover:text-yellow-700 xl:text-lg">
                    Shop
                </button>

                <button @click="navi('Products')"
                    class="whitespace-nowrap text-base transition hover:text-yellow-700 xl:text-lg">
                    Featured Products
                </button>

                <button @click="navi('Gallery')"
                    class="whitespace-nowrap text-base transition hover:text-yellow-700 xl:text-lg">
                    Gallery
                </button>

            </div>
        </div>

        <!-- Mobile Navigation Menu -->
        <div v-if="mobileMenuOpen"
            class="max-h-[calc(100vh-8rem)] overflow-y-auto border-t border-yellow-800 bg-white px-4 py-4 shadow-xl lg:hidden">

            <!-- Mobile Categories -->
            <div class="mb-4">
                <label for="mobile-category" class="mb-2 block text-sm font-semibold text-gray-700">
                    Categories
                </label>

                <select id="mobile-category" v-model="selectedCategory" @change="goToCategory"
                    class="h-11 w-full rounded-md border border-gray-300 bg-white px-3 text-sm outline-none focus:border-yellow-700">
                    <option value="">Select a category</option>
                    <option value="Living Room">Living Room</option>
                    <option value="Bedroom">Bedroom</option>
                    <option value="Dining Room">Dining Room</option>
                </select>
            </div>

            <div class="flex flex-col">

                <button @click="navi('Home')"
                    class="border-b border-gray-100 px-3 py-3 text-left text-base transition hover:bg-yellow-50 hover:text-yellow-800">
                    Home
                </button>

                <button @click="navi('About')"
                    class="border-b border-gray-100 px-3 py-3 text-left text-base transition hover:bg-yellow-50 hover:text-yellow-800">
                    About Us
                </button>

                <button @click="navi('Contact')"
                    class="border-b border-gray-100 px-3 py-3 text-left text-base transition hover:bg-yellow-50 hover:text-yellow-800">
                    Contact Us
                </button>

                <button @click="navi('Products')"
                    class="border-b border-gray-100 px-3 py-3 text-left text-base transition hover:bg-yellow-50 hover:text-yellow-800">
                    Shop
                </button>

                <button @click="navi('Products')"
                    class="border-b border-gray-100 px-3 py-3 text-left text-base transition hover:bg-yellow-50 hover:text-yellow-800">
                    Featured Products
                </button>

                <button @click="navi('Gallery')"
                    class="px-3 py-3 text-left text-base transition hover:bg-yellow-50 hover:text-yellow-800">
                    Gallery
                </button>

            </div>
        </div>

    </nav>
</template>