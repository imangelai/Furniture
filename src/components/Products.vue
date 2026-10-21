<script>
export default {
    props: ['addNew', 'addNapod', 'addNgani'],
    emits: [
        'to-shop',
        'to-shop1',
        'to-shop2',
        'toCategorize',
        'send-product',
        'send-i',
        'send-l',
        'send-j',
        'send-ii',
        'send-iii',
        'send-iiii',
        'open',
    ],

    data() {
        return {
            livings: [
                {
                    id: 1, img: 'https://i.pinimg.com/736x/db/0e/82/db0e82042694ca55a67d7dec10002e39.jpg',
                    name: 'Cozy Neutral Sofa Living Room',
                    price: 30000
                },
                {
                    id: 2, img: 'https://i.pinimg.com/1200x/1f/6d/16/1f6d16e8a29f6419338a1a0b60abcfaa.jpg',
                    name: 'Elegant Gray Sofa Living Room',
                    price: 35000
                },
                {
                    id: 3, img: 'https://i.pinimg.com/736x/49/d6/d0/49d6d03b4760bb002d678497d04f77c4.jpg',
                    name: 'Cozy Yellow Sofa Living Room',
                    price: 25000
                },
                {
                    id: 4, img: 'https://i.pinimg.com/1200x/7b/d4/25/7bd425b1f051d0793abe31ca11727267.jpg',
                    name: 'Cozy Blue Sofa Living Room',
                    price: 40000
                },
                {
                    id: 5, img: 'https://i.pinimg.com/736x/93/dd/4b/93dd4b1ffda1f7b81c0385c00abffb7e.jpg',
                    name: 'Wooden Small Table',
                    price: 5000
                },
                {
                    id: 6, img: 'https://i.pinimg.com/736x/28/ae/a1/28aea10ed7eb493dba4a91bf8111632c.jpg',
                    name: 'Elegant Brown Table',
                    price: 7000
                },
                {
                    id: 7, img: 'https://i.pinimg.com/1200x/84/dd/f5/84ddf5b542e2a0320047ab8c9eb96cfc.jpg',
                    name: 'Modern Minimalist White Table',
                    price: 8000
                },
                {
                    id: 8, img: 'https://i.pinimg.com/736x/da/bf/e5/dabfe596f59fcbdb9807271ae9d4d5cf.jpg',
                    name: 'Lavish Home Round Nesting Table',
                    price: 9000
                },
            ],

            dinings: [
                {
                    id: 1, img: 'https://i.pinimg.com/736x/a3/10/9a/a3109ade9e40d1c39fa3712d2c658cc0.jpg',
                    name: 'Oval Dining Table Set',
                    price: 30000
                },
                {
                    id: 2, img: 'https://down-ph.img.susercontent.com/file/sg-11134202-825ac-mfz2scm61xxk62.webp',
                    name: 'Solid Wood Dining Table Set',
                    price: 35000
                },
                {
                    id: 3, img: 'https://down-ph.img.susercontent.com/file/ph-11134201-81zti-mkhl1rndmoso12.webp',
                    name: 'New Chinese Style Dining Table',
                    price: 25000
                },
                {
                    id: 4, img: 'https://i.pinimg.com/736x/62/06/61/62066108f941b23fdeccb12579c985e0.jpg',
                    name: 'Two Seater Dining Table Set',
                    price: 40000
                },
                {
                    id: 5, img: 'https://down-ph.img.susercontent.com/file/sg-11134202-82596-mgbv4pkc4d8r6e.webp',
                    name: 'French Retro Style Dining Set',
                    price: 5000
                },
                {
                    id: 6, img: 'https://i.pinimg.com/736x/c0/69/b6/c069b61e54e483a83bdcc7c8a0cb5b7c.jpg',
                    name: 'Modern White Dining Table',
                    price: 7000
                },
                {
                    id: 7, img: 'https://i.pinimg.com/736x/e8/f8/2d/e8f82d81473a26ff39cbffa3f8ddc4d9.jpg',
                    name: 'Modern Warm Orange Table',
                    price: 8000
                },
                {
                    id: 8, img: 'https://i.pinimg.com/736x/d8/a1/65/d8a165129606a6ecaa9b54a7bde3698c.jpg',
                    name: 'Lavish Home Round Nesting Table',
                    price: 9000
                },
            ],

            beds: [
                {
                    id: 1, img: 'https://i.pinimg.com/736x/40/ec/71/40ec71efb944dd96b3d80137daedcae6.jpg',
                    name: 'Wooden Bed Dark Brown',
                    price: 35000
                },
                {
                    id: 2, img: 'https://i.pinimg.com/736x/77/7a/69/777a69ebd10f7eda67004eb839c5b67e.jpg',
                    name: 'Wooden Bed w/ 2 Compartment',
                    price: 35000
                },
                {
                    id: 3, img: 'https://i.pinimg.com/736x/69/68/90/696890978aa87edc7e7736b7308850bd.jpg',
                    name: 'Wooden Bed Ash Gray',
                    price: 25000
                },
                {
                    id: 4, img: 'https://i.pinimg.com/1200x/1d/40/5a/1d405a2ab0bef323f6b0214ec13f0315.jpg',
                    name: 'Wooden Bed w/ 1 Compartment',
                    price: 40000
                },
                {
                    id: 5, img: 'https://i.pinimg.com/1200x/75/6e/05/756e05531a80f7d76d2ee99f52941262.jpg',
                    name: 'Modern Style Bed Gray',
                    price: 5000
                },
                {
                    id: 6, img: 'https://i.pinimg.com/736x/96/dc/f3/96dcf3e2d04883c38960ccdc0e01854a.jpg',
                    name: 'Modern Style Bed Blue',
                    price: 7000
                },
                {
                    id: 7, img: 'https://i.pinimg.com/1200x/b3/9d/49/b39d49c63b296263a47767db7cb23da8.jpg',
                    name: 'Modern Style Bed Pink',
                    price: 8000
                },
                {
                    id: 8, img: 'https://i.pinimg.com/736x/49/b4/c1/49b4c150bbb62f4352f0491c351dd703.jpg',
                    name: 'Modern Style Bed Black',
                    price: 9000
                },
            ],

            dine: false,
            shopSec: true,
            kusina: false,
            kwarto: false,
        };
    },

    methods: {
        shopNow() {
            this.dine = true;
            this.kusina = false;
            this.kwarto = false;
            this.shopSec = false;
            this.$emit('toCategorize', 'living');
        },

        shopNa() {
            this.kusina = true;
            this.dine = false;
            this.kwarto = false;
            this.shopSec = false;
            this.$emit('toCategorize', 'dining');
        },

        shopNapod() {
            this.kwarto = true;
            this.dine = false;
            this.kusina = false;
            this.shopSec = false;
            this.$emit('toCategorize', 'bedroom');
        },

        exit() {
            this.dine = false;
            this.shopSec = true;
        },

        exitbtn() {
            this.kusina = false;
            this.shopSec = true;
        },

        exitBtn() {
            this.kwarto = false;
            this.shopSec = true;
        },

        addToCartBtnLiving(i) {
            this.$emit('send-i', this.livings[i]);
            alert('Added to cart.');
        },

        addToCartBtnBed(i) {
            this.$emit('send-l', this.beds[i]);
            alert('Added to cart.');
        },

        addToCartBtnDining(i) {
            this.$emit('send-j', this.dinings[i]);
            alert('Added to cart.');
        },

        productModal() {
            this.$emit('open', true);
        },

        newCObtnLiving(i) {
            this.$emit('send-ii', this.addNew[i]);
            alert('Added to cart.');
        },

        newCObtnDining(i) {
            this.$emit('send-iii', this.addNapod[i]);
            alert('Added to cart.');
        },

        newCObtnBed(i) {
            this.$emit('send-iiii', this.addNgani[i]);
            alert('Added to cart.');
        },
    },
};
</script>

<template>
    <!-- LIVING ROOM PAGE -->
    <div v-if="dine" class="w-full mt-10 px-4 py-6 pt-28 sm:px-6 md:px-8 lg:px-10 lg:pt-32">
        <div class="mb-6 flex items-start justify-between gap-4 sm:items-center">
            <div class="flex flex-col gap-3">
                <h1 class="text-xl font-serif italic sm:text-2xl md:text-3xl">
                    Living Room Furniture
                </h1>

                <button @click="productModal"
                    class="w-fit rounded-md cursor-pointer bg-yellow-900 px-5 py-2.5 text-sm font-semibold text-white transition hover:bg-yellow-800">
                    Add Product
                </button>
            </div>

            <button @click="exit" aria-label="Close living room" class="p-2 font-bold text-gray-500 cursor-pointer hover:text-black">
                ✕
            </button>
        </div>

        <p class="mb-4 mt-6 text-lg font-bold text-red-500">NEW PRODUCTS!</p>

        <div class="grid grid-cols-1 gap-5 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4">
            <div v-for="(living, index) in addNew" :key="living.id ?? index" class="flex min-w-0 justify-center">
                <div
                    class="flex h-full w-full max-w-sm flex-col gap-3 overflow-hidden rounded-lg bg-slate-200 shadow-lg">
                    <img :src="living.img" :alt="living.name" class="aspect-square cursor-pointer w-full object-cover" />
                    <div class="flex flex-1 flex-col px-3">
                        <p class="text-lg font-serif italic">{{ living.name }}</p>
                        <p class="mt-1 text-gray-600">₱ {{ living.price }}</p>
                    </div>
                    <button @click="newCObtnLiving(index)"
                        class="mx-3 mb-3 rounded-md bg-amber-900 px-5 py-2 text-white transition cursor-pointer hover:bg-amber-800">
                        Add to cart
                    </button>
                </div>
            </div>
        </div>

        <hr class="my-8" />

        <div class="grid grid-cols-1 gap-5 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4">
            <div v-for="(living, index) in livings" :key="living.id" class="flex min-w-0 justify-center">
                <div
                    class="flex h-full w-full max-w-sm flex-col gap-3 overflow-hidden rounded-lg bg-slate-200 shadow-lg">
                    <img :src="living.img" :alt="living.name" class="aspect-square cursor-pointer w-full object-cover" />
                    <div class="flex flex-1 flex-col px-3">
                        <p class="text-lg font-serif italic">{{ living.name }}</p>
                        <p class="mt-1 text-gray-600">₱ {{ living.price }}</p>
                    </div>
                    <button @click="addToCartBtnLiving(index)"
                        class="mx-3 mb-3 rounded-md bg-amber-900 px-5 py-2 text-white transition cursor-pointer hover:bg-amber-800">
                        Add to cart
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- DINING ROOM PAGE -->
    <div v-if="kusina" class="w-full mt-10 px-4 py-6 pt-28 sm:px-6 md:px-8 lg:px-10 lg:pt-32">
        <div class="mb-6 flex items-start justify-between gap-4 sm:items-center">
            <div class="flex flex-col gap-3">
                <h1 class="text-xl font-serif italic sm:text-2xl md:text-3xl">
                    Dining Room Furniture
                </h1>

                <button @click="productModal"
                    class="w-fit rounded-md bg-yellow-900 px-5 py-2.5 text-sm font-semibold text-white transition cursor-pointer hover:bg-yellow-800">
                    Add Product
                </button>
            </div>

            <button @click="exitbtn" aria-label="Close dining room"
                class="p-2 font-bold text-gray-500 cursor-pointer hover:text-black">
                ✕
            </button>
        </div>

        <p class="mb-4 mt-6 text-lg font-bold text-red-500">NEW PRODUCTS!</p>

        <div class="grid grid-cols-1 gap-5 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4">
            <div v-for="(dining, index) in addNapod" :key="dining.id ?? index" class="flex min-w-0 justify-center">
                <div
                    class="flex h-full w-full max-w-sm flex-col gap-3 overflow-hidden rounded-lg bg-slate-200 shadow-lg">
                    <img :src="dining.img" :alt="dining.name" class="aspect-square cursor-pointer w-full object-cover" />
                    <div class="flex flex-1 flex-col px-3">
                        <p class="text-lg font-serif italic">{{ dining.name }}</p>
                        <p class="mt-1 text-gray-600">₱ {{ dining.price }}</p>
                    </div>
                    <button @click="newCObtnDining(index)"
                        class="mx-3 mb-3 rounded-md bg-amber-900 px-5 py-2 text-white transition cursor-pointer hover:bg-amber-800">
                        Add to cart
                    </button>
                </div>
            </div>
        </div>

        <hr class="my-8" />

        <div class="grid grid-cols-1 gap-5 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4">
            <div v-for="(dining, index) in dinings" :key="dining.id" class="flex min-w-0 justify-center">
                <div
                    class="flex h-full w-full max-w-sm flex-col gap-3 overflow-hidden rounded-lg bg-slate-200 shadow-lg">
                    <img :src="dining.img" :alt="dining.name" class="aspect-square cursor-pointer w-full object-cover" />
                    <div class="flex flex-1 flex-col px-3">
                        <p class="text-lg font-serif italic">{{ dining.name }}</p>
                        <p class="mt-1 text-gray-600">₱ {{ dining.price }}</p>
                    </div>
                    <button @click="addToCartBtnDining(index)"
                        class="mx-3 mb-3 rounded-md bg-amber-900 px-5 py-2 text-white transition cursor-pointer hover:bg-amber-800">
                        Add to cart
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- BEDROOM PAGE -->
    <div v-if="kwarto" class="w-full mt-10 px-4 py-6 pt-28 sm:px-6 md:px-8 lg:px-10 lg:pt-32">
        <div class="mb-6 flex items-start justify-between gap-4 sm:items-center">
            <div class="flex flex-col gap-3">
                <h1 class="text-xl font-serif italic sm:text-2xl md:text-3xl">
                    Bedroom Furniture
                </h1>

                <button @click="productModal"
                    class="w-fit rounded-md bg-yellow-900 px-5 py-2.5 text-sm font-semibold text-white transition cursor-pointer hover:bg-yellow-800">
                    Add Product
                </button>
            </div>

            <button @click="exitBtn" aria-label="Close bedroom" class="p-2 font-bold text-gray-500 cursor-pointer hover:text-black">
                ✕
            </button>
        </div>

        <p class="mb-4 mt-6 text-lg font-bold text-red-500">NEW PRODUCTS!</p>

        <div class="grid grid-cols-1 gap-5 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4">
            <div v-for="(bed, index) in addNgani" :key="bed.id ?? index" class="flex min-w-0 justify-center">
                <div
                    class="flex h-full w-full max-w-sm flex-col gap-3 overflow-hidden rounded-lg bg-slate-200 shadow-lg">
                    <img :src="bed.img" :alt="bed.name" class="aspect-square cursor-pointer w-full object-cover" />
                    <div class="flex flex-1 flex-col px-3">
                        <p class="text-lg font-serif italic">{{ bed.name }}</p>
                        <p class="mt-1 text-gray-600">₱ {{ bed.price }}</p>
                    </div>
                    <button @click="newCObtnBed(index)"
                        class="mx-3 mb-3 rounded-md bg-amber-900 px-5 py-2 text-white transition cursor-pointer hover:bg-amber-800">
                        Add to cart
                    </button>
                </div>
            </div>
        </div>

        <hr class="my-8" />

        <div class="grid grid-cols-1 gap-5 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4">
            <div v-for="(bed, index) in beds" :key="bed.id" class="flex min-w-0 justify-center">
                <div
                    class="flex h-full w-full max-w-sm flex-col gap-3 overflow-hidden rounded-lg bg-slate-200 shadow-lg">
                    <img :src="bed.img" :alt="bed.name" class="aspect-square cursor-pointer w-full object-cover" />
                    <div class="flex flex-1 flex-col px-3">
                        <p class="text-lg font-serif italic">{{ bed.name }}</p>
                        <p class="mt-1 text-gray-600">₱ {{ bed.price }}</p>
                    </div>
                    <button @click="addToCartBtnBed(index)"
                        class="mx-3 mb-3 rounded-md bg-amber-900 px-5 py-2 text-white transition cursor-pointer hover:bg-amber-800">
                        Add to cart
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- SHOP LANDING PAGE -->
    <div v-if="shopSec" class="mt-24 w-full px-4  sm:mt-28 sm:px-6 md:px-8 lg:mt-32 lg:px-10">

        <!-- Living Room -->
        <section class="grid min-h-112 grid-cols-1 overflow-hidden rounded-lg md:min-h-128 md:grid-cols-2">
            <img src="https://i.pinimg.com/1200x/54/87/9c/54879c47780728226c91bec288db177b.jpg"
                alt="Living room furniture"
                class="h-64 w-full object-cover rounded-lg transition duration-500 hover:scale-103 cursor-pointer sm:h-80 md:h-full" />

            <div class="flex flex-col justify-center gap-5 bg-zinc-100 px-5 py-8 sm:px-8 md:gap-8 md:px-10 lg:px-12">
                <h1 class="text-3xl font-semibold sm:text-4xl lg:text-5xl">
                    Living Room
                </h1>

                <p class="max-w-xl leading-relaxed text-zinc-500 sm:text-base lg:text-lg">
                    Elevate your space with timeless furniture designed for comfort, functionality, and modern living.
                </p>

                <button @click="shopNow"
                    class="w-fit rounded-md px-2 py-2 text-left text-base transition hover:font-semibold cursor-pointer hover:text-yellow-900 sm:text-lg">
                    SHOP NOW ➔
                </button>
            </div>
        </section>

        <!-- Bedroom -->
        <section class="grid min-h-112 grid-cols-1 overflow-hidden rounded-lg md:min-h-128 md:grid-cols-2">
            <div
                class="order-2 flex flex-col justify-center gap-5 bg-zinc-100 px-5 py-8 sm:px-8 md:order-1 md:gap-8 md:px-10 lg:px-12">
                <h1 class="text-3xl font-semibold sm:text-4xl lg:text-5xl">
                    Bedroom
                </h1>

                <p class="max-w-xl leading-relaxed text-zinc-500 sm:text-base lg:text-lg">
                    Create a restful retreat with beautifully crafted beds, storage, and essentials designed for comfort
                    and relaxation.
                </p>

                <button @click="shopNapod"
                    class="w-fit rounded-md px-2 py-2 text-left text-base transition hover:font-semibold cursor-pointer hover:text-yellow-900 sm:text-lg">
                    SHOP NOW ➔
                </button>
            </div>

            <img src="https://i.pinimg.com/1200x/a2/02/34/a20234d4d84783fcae8086d2c2ed4f0a.jpg" alt="Bedroom furniture"
                class="order-1 h-64 w-full object-cover transition cursor-pointer duration-300 rounded-lg hover:scale-103 sm:h-80 md:order-2 md:h-full" />
        </section>

        <!-- Dining Room -->
        <section class="grid min-h-112 grid-cols-1 overflow-hidden rounded-lg md:min-h-128 md:grid-cols-2">
            <img src="https://i.pinimg.com/1200x/a3/c7/82/a3c782d20a33e84821b3c83bae1a66cb.jpg"
                alt="Dining room furniture"
                class="h-64 w-full object-cover rounded-lg transition cursor-pointer duration-500 hover:scale-103 sm:h-80 md:h-full" />

            <div class="flex flex-col justify-center gap-5 bg-zinc-100 px-5 py-8 sm:px-8 md:gap-8 md:px-10 lg:px-12">
                <h1 class="text-3xl font-semibold sm:text-4xl lg:text-5xl">
                    Dining Room
                </h1>

                <p class="max-w-xl leading-relaxed text-zinc-500 sm:text-base lg:text-lg">
                    Elevate every dining experience with refined furniture that blends functionality, durability, and
                    modern style.
                </p>

                <button @click="shopNa"
                    class="w-fit rounded-md px-2 py-2 text-left text-base transition hover:font-semibold cursor-pointer hover:text-yellow-900 sm:text-lg">
                    SHOP NOW ➔
                </button>
            </div>
        </section>

    </div>
</template>