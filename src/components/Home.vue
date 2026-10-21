<script>
export default {
    data() {
        return {
            furnitures: [
                {
                    id: 1,
                    img: 'https://i.pinimg.com/736x/34/b3/42/34b342f3fab6e7dd7d16b3d0d4690aa3.jpg',
                    name: 'Sofas',
                },
                {
                    id: 2,
                    img: 'https://i.pinimg.com/736x/de/45/20/de45202b254126492763ea899f7b772a.jpg',
                    name: 'Bedroom',
                },
                {
                    id: 3,
                    img: 'https://i.pinimg.com/736x/8f/51/d3/8f51d357dd8b4e2a64207f034998f652.jpg',
                    name: 'Living room',
                },
                {
                    id: 4,
                    img: 'https://i.pinimg.com/1200x/4b/2b/71/4b2b7111c177693cf0f3491002d5d0a6.jpg',
                    name: 'Dining Room',
                },
            ],
        };
    },
    methods: {},
};
</script>

<template>
    <div class="w-full px-4 py-8 sm:px-6 md:px-8 lg:px-10 lg:py-10">

        <!-- Furniture Categories Section -->
        <section class="mb-16 sm:mb-20 lg:mb-28">

            <div class="mb-6 mt-25 space-y-3 sm:mb-8 sm:space-y-4">
                <h1 class="max-w-3xl text-2xl font-semibold leading-tight sm:text-3xl md:text-4xl lg:text-3xl">
                    Revitalize your living space with a fresh touch.
                </h1>

                <p class="text-base text-gray-600 sm:text-lg md:text-xl">
                    Our seasonal hits and everyday favorites find yours!
                </p>
            </div>

            <div class="grid grid-cols-1  sm:grid-cols-2 lg:grid-cols-4 ">

                <div v-for="furniture in furnitures" :key="furniture.id"
                
                    class="group relative cursor-pointer overflow-hidden rounded-lg">
                    <img :src="furniture.img" :alt="furniture.name"
                        class="h-72 w-full object-cover transition-transform duration-300 group-hover:scale-105 sm:h-80 md:h-96 lg:h-128 xl:h-144" />

                    <p
                        class="absolute left-3 top-3 z-10 rounded-md bg-white px-4 py-2 text-sm font-medium shadow-sm sm:left-4 sm:top-4 sm:px-5 sm:text-base">
                        {{ furniture.name }}
                    </p>
                </div>

            </div>
        </section>

        <!-- Create the Look Section -->
        <section class="mb-10">

            <div class="mb-6 space-y-3 sm:mb-8">
                <h2 class="text-xl font-semibold sm:text-2xl md:text-3xl">
                    Create the look
                </h2>

                <p class="max-w-3xl text-sm leading-relaxed text-gray-600 sm:text-base md:text-lg">
                    Explore inspiring spaces and shop the furniture and décor that bring each room together.
                </p>
            </div>

            <div class="grid grid-cols-1  sm:grid-cols-2 ">

                <div class="overflow-hidden rounded-lg">
                    <img src="https://i.pinimg.com/736x/ef/8b/0f/ef8b0f8fd65ec906855bf6b391c1b0cf.jpg"
                        alt="Inspiring interior design"
                        class="h-72 w-full object-cover cursor-pointer transition-transform duration-300 hover:scale-105 sm:h-80 md:h-96 lg:h-128" />
                </div>

                <div class="overflow-hidden rounded-lg">
                    <img src="https://i.pinimg.com/1200x/75/6e/05/756e05531a80f7d76d2ee99f52941262.jpg"
                        alt="Modern home furniture and décor"
                        class="h-72 w-full object-cover cursor-pointer transition-transform duration-300 hover:scale-105 sm:h-80 md:h-96 lg:h-128" />
                </div>

            </div>
        </section>

    </div>
</template>