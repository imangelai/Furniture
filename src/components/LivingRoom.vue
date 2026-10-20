<script>
export default {
    props:['sendToShop'],
    
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
            <h1 class="text-2xl px-3 font-serif italic">Living Room Furnitures</h1>
        
            <div class="grid grid-cols-4 flex flex-col gap-5 mt-5">
                <div v-for="add in sendToShop" :key="add.id" class="flex justify-center">
                    <div class="shadow-lg bg-slate-200 w-80 h-fit flex flex-col gap-3">
                        <img :src="add.img" alt="" class="w-80 h-80 rounded-md">

                        <div class="flex flex-col px-3">
                            <p class="text-lg font-serif italic">{{ add.name }}</p>
                            <p class="text-gray-600">₱ {{ add.price }}</p>
                        </div>
                        <button class="px-5 py-2 bg-amber-900 text-white rounded-md hover:bg-amber-800 hover:scale-103 cursor-pointer duration-300">Add to cart</button>
                    </div>
                </div>
            </div>

        </div>
    </div>
</template>