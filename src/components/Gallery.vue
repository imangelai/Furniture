<script>
export default {
    data() {
        return {
            galleries: [
                {
                    id: 1,
                    img: 'https://i.pinimg.com/1200x/a9/6a/c4/a96ac4e1ee79954d950d1aeda68b5dd5.jpg'
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
                {
                    id: 6,
                    img: 'https://i.pinimg.com/736x/8e/0c/ec/8e0cec5f4eb74ddf1e9d68ab082811f5.jpg'
                },
                {
                    id: 7,
                    img: 'https://i.pinimg.com/1200x/97/41/ec/9741ec576d1289f1142bf57584fcfd4e.jpg'
                },
                {
                    id: 8,
                    img: 'https://i.pinimg.com/1200x/51/b6/61/51b661112d57410bc105db0b5abc4cc6.jpg'
                },
                {
                    id: 9,
                    img: 'https://i.pinimg.com/1200x/23/57/c4/2357c45ba6b2d57cb3e8c78d45d6fe0e.jpg'
                },
                {
                    id: 10,
                    img: 'https://i.pinimg.com/1200x/55/97/2c/55972cd16fdedc4a45664ed54432bf46.jpg'
                },
            ]

        }
    },
    methods: {

    }
}

</script>


<template>

    <div class="w-full px-4 py-8 mt-30">

        <div class="grid grid-cols-1 gap-4 sm:grid-cols-2 lg:grid-cols-5 sm:gap-5 lg:gap-6">

            <div v-for="gallery in galleries" :key="gallery.id" class="group relative overflow-hidden rounded-lg">
                <img :src="gallery.img" alt=""
                    class="h-72 w-full object-cover transition-transform duration-300 group-hover:scale-105 sm:h-80 md:h-96 lg:h-100 xl:h-130" />
            </div>

        </div>
    </div>

</template>