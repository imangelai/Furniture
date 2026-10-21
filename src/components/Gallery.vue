<script>
export default {
    data() {
        return {
            gallery: [
                {
                    id: 1,
                    img: 'https://i.pinimg.com/1200x/35/f3/db/35f3dbafcb1fc22ad81ee16312582de9.jpg'
                },
                {
                    id: 2,
                    img: 'https://i.pinimg.com/736x/19/8b/d1/198bd13c452551b363aec111dac20c55.jpg'
                },
                {
                    id: 3,
                    img: 'https://i.pinimg.com/736x/46/25/8a/46258ab4d11af332c5ae3a5f36a9060b.jpg'
                },
                {
                    id: 4,
                    img: 'https://i.pinimg.com/736x/a2/4e/6e/a24e6e255d774356e5c035610609c317.jpg'
                },
                {
                    id: 5,
                    img: 'https://img.staticdj.com/watermark8cdf95da50bf2e7f2baa9828ad19e199_2056x.jpeg'
                },
            ]

        }
    },
    methods: {

    }
}

</script>


<template>

    <div class="w-full px-4 py-8">


        <div class="grid grid-cols-1 gap-4 sm:grid-cols-2 lg:grid-cols-4 sm:gap-5 lg:gap-6">

            <div v-for="gallery in galleries" :key="gallery.id" class="group relative overflow-hidden rounded-lg">
                <img :src="gallery.img" :alt="gallery.name"
                    class="h-72 w-full object-cover transition-transform duration-300 group-hover:scale-105 sm:h-80 md:h-96 lg:h-[32rem] xl:h-[36rem]" />
            </div>

        </div>
    </div>

</template>