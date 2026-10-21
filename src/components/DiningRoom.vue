<script>
export default {
    props: ['sendtoKusina'],

    data() {
        return {
           
        }
    }, methods: {

    }
}
</script>

<template>
    <div class="px-10 py-5">
        <div class="h-fit">
            <h1 class="text-2xl font-serif italic px-3">Dining Room Furnitures</h1>

            <div class="grid grid-cols-4 gap-5 mt-5">
                <div v-for="dining in sendtoKusina" :key="dining.id" class="flex justify-center">
                    <div class="shadow-lg bg-slate-200 w-80 h-fit flex flex-col gap-3">
                        <img :src="dining.img" alt="" class="w-80 h-80 rounded-md ">

                        <div class="flex flex-col px-3">
                            <p class="text-lg font-serif italic">{{ dining.name }}</p>
                            <p class="text-gray-600">₱ {{ dining.price }}</p>
                        </div>
                        <button class="px-5 py-2 bg-amber-900 text-white rounded-md hover:bg-amber-800 hover:scale-103 cursor-pointer duration-300">Add to cart</button>
                    </div>
                </div>
            </div>

        </div>
    </div>
</template>