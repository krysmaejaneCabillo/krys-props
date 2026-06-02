<script>
import Modal from '../Modal/Modal.vue';
export default {
    components: {
        Modal
    },
    props: {
        selectedProduct: {
            type: Object,
        },
        searchbar: {
            type : String
        }
    },
    data() {
        return {
            modalOpen: false,
            currentIndex: 0,
            products: [
                {
                    id: 1,
                    image: 'data:image/webp;base64,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',
                    name: 'Side Blazer Dress',
                    price: '149',
                    sku: 'sz2411265665417997'
                },
                {
                    id: 2,
                    image: 'data:image/webp;base64,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',
                    name: 'Work Ball Gown Dress',
                    price: '123',
                    sku: 'sz2411265665417996'
                },
                {
                    id: 3,
                    image: 'https://th.bing.com/th/id/OIP.OY8v5uX5KY1vKlpkyCvBZQHaJ2?w=208&h=277&c=7&r=0&o=7&dpr=1.3&pid=1.7&rm=3',
                    name: 'Maxi Woman Dress',
                    price: '499',
                    sku: 'sz2411265665417997'
                },
                {
                    id: 4,
                    image: 'https://th.bing.com/th/id/OIP.ZbFiL0R41rGgx0aGKI_pwQHaJ3?w=208&h=277&c=7&r=0&o=7&dpr=1.3&pid=1.7&rm=3',
                    name: 'Woman Dress',
                    price: '85',
                    sku: 'sz2411265665417997'
                },
                {
                    id: 5,
                    image: 'https://cdn.streetstylestore.com/2/2/3/4/1/4/223414-sss_vertical.jpg',
                    name: 'Trendy Woman Clothing',
                    price: '175',
                    sku: 'sz2411265665417997'
                },
                {
                    id: 6,
                    image: 'https://tse2.mm.bing.net/th/id/OIP.BqfQv5tePCTz0xubjih5nAHaHa?r=0&pid=ImgDet&w=182&h=182&c=7&dpr=1.3&o=7&rm=3',
                    name: 'Puff Sleeve Backless Floral Dress',
                    price: '85',
                    sku: 'sz2411265665417997'
                },
                {
                    id: 7,
                    image: 'https://th.bing.com/th/id/OIP.sf3h9-mW7vjlDPzP40Bz_QHaIW?w=208&h=235&c=7&r=0&o=7&dpr=1.3&pid=1.7&rm=3',
                    name: 'Floral Strapless Mini Dress',
                    price: '85',
                    sku: 'sz2411265665417997'
                },
                {
                    id: 8,
                    image: 'https://tse2.mm.bing.net/th/id/OIP.drrbcW1eCW3cqe-FQl6feAHaL2?r=0&pid=ImgDet&w=182&h=290&c=7&dpr=1.3&o=7&rm=3',
                    name: 'Coquette Dress',
                    price: '155',
                    sku: 'sz2411265665417997'
                },
                {
                    id: 9,
                    image: 'https://i.pinimg.com/originals/0a/dc/fe/0adcfe7ecb3dfc49e6d27ec3131b4445.png',
                    name: 'Knitted Vest Sweater',
                    price: '135',
                    sku: 'sz2411265665417997'
                },
                {
                    id: 10,
                    image: 'https://th.bing.com/th/id/OIP.0qxmqH7tYlkBqlqPiSJi2AHaJd?w=208&h=265&c=7&r=0&o=7&dpr=1.3&pid=1.7&rm=3https://i.pinimg.com/originals/0a/dc/fe/0adcfe7ecb3dfc49e6d27ec3131b4445.png',
                    name: 'Pastel Pink Fairy Dress',
                    price: '125',
                    sku: 'sz24521265665417997'
                },
                
                {
                    id: 11,
                    image: 'https://th.bing.com/th/id/OIP.4viJ-av_tBltW_egkRnm9QHaMs?w=190&h=327&c=7&r=0&o=7&dpr=1.3&pid=1.7&rm=3',
                    name: 'Vintage Ritro Old Fashion Dress',
                    price: '125',
                    sku: 'sz24521265665417997'
                },
                {
                    id: 12,
                    image: 'https://th.bing.com/th/id/OIP.1gcav3hNtrMzQ69itP7qXQHaLs?w=198&h=314&c=7&r=0&o=7&dpr=1.3&pid=1.7&rm=3',
                    name: 'Old Money Outfit',
                    price: '125',
                    sku: 'sz24521265665417997'
                },
                
            ],


        };
    },
    methods: {
        openModal(index) {
            this.currentIndex = index;
            this.modalOpen = true;

        },
        closeModal() {
            this.modalOpen = false;
        },
        addToCart(product) {
            this.$emit('add-to-cart', { ...product })
        }
    }
}


</script>

<template>

    <body class="bg-gradient-to-b from-pink-50 to-purple-50 font-sans">

        <section class="p-4 md:p-8">
            <div class="max-w-7xl mx-auto space-y-6">

                <!-- Promos and Feature Banners -->
                <div class="grid grid-cols-1 md:grid-cols-4 lg:grid-cols-5 gap-4">
                    <!-- Left Side Promos -->
                    <div class="space-y-3 col-span-1 md:col-span-2 lg:col-span-1">
                        <a href="#"
                            class="block bg-[url('https://tse3.mm.bing.net/th/id/OIP.eGtIVmwghrxJ_CpbeZBiegHaDA?r=0&rs=1&pid=ImgDetMain&o=7&rm=3')] bg-cover no-repeat p-4 rounded-lg shadow-sm hover:shadow-md transition">
                            <p class="text-sm font-semibold text-gray-700">NEW ARRIVALS</p>
                        </a>
                        <a href="#"
                            class="block bg-[url('https://tse4.mm.bing.net/th/id/OIP.3NDpmV6AcXUwSuJpSJ5gswHaE8?r=0&pid=ImgDet&w=184&h=122&c=7&dpr=1.3&o=7&rm=3')] bg-cover no-repeat p-4 rounded-lg shadow-sm hover:shadow-md transition">
                            <p class="text-sm font-semibold text-gray-700">CLEARANCE SALE</p>
                        </a>
                        <a href="#"
                            class="block bg-[url('https://tse1.mm.bing.net/th/id/OIP.yeBh_7ASxZevADV8eLvNfgHaE8?r=0&pid=ImgDet&w=184&h=122&c=7&dpr=1.3&o=7&rm=3')] bg-cover no-repeat p-4 rounded-lg shadow-sm hover:shadow-md transition">
                            <p class="text-sm font-semibold text-gray-700">All under <span
                                    class="text-red-600 font-bold">$199</span></p>
                        </a>
                    </div>

                    <!-- Center Feature Banner -->
                    <div
                        class="col-span-1 md:col-span-2 lg:col-span-3 bg-[url('https://plus.unsplash.com/premium_photo-1661696747155-32fe676f9e78?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTk5fHxnaXJsJTIwbGFuZHNjYXBlJTIwYmVhY2h8ZW58MHx8MHx8fDA%3D')] bg-cover no-repeat p-4 rounded-lg shadow-sm">
                        <div class="flex flex-col sm:flex-row gap-4 items-center">
                            <div class="w-full sm:w-1/2 flex-shrink-0">
                                <h2 class="text-3xl font-extrabold text-white leading-tight">66 VACAY MODE</h2>
                                <p class="text-4xl font-bold text-white mt-2">UP TO <span
                                        class="text-5xl font-black">90%</span> OFF</p>
                                <button
                                    class="mt-4 px-6 py-2 bg-blue-600 text-white font-semibold rounded-full text-sm hover:bg-blue-800">SHOP
                                    NOW</button>
                            </div>
                            <div class="flex-grow flex items-center justify-center gap-2">
                                <div
                                    class="aspect-[3/4] w-32 bg-[url('https://images.unsplash.com/photo-1539008835657-9e8e9680c956?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTh8fGRyZXNzfGVufDB8fDB8fHww')] bg-cover no-repeat rounded-md relative flex items-center justify-center text-red-600 font-bold p-2 text-center text-xs">
                                    P225</div>
                                <div
                                    class="aspect-[3/4] w-32 bg-[url('https://images.unsplash.com/photo-1595950653106-6c9ebd614d3a?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8c2hvZXN8ZW58MHx8MHx8fDA%3D')] bg-cover no-repeat rounded-md relative flex items-center justify-center text-red-600 font-bold p-2 text-center text-xs">
                                    $361</div>
                                <button class="p-1 rounded-full bg-gray-100 hover:bg-gray-200"><svg
                                        class="w-4 h-4 text-gray-600" fill="none" stroke="currentColor"
                                        viewBox="0 0 24 24">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                            d="M9 5l7 7-7 7" />
                                    </svg></button>
                            </div>
                        </div>
                    </div>

                    <!-- Right Side Banners -->
                    <div class="space-y-3 col-span-1 md:col-span-2 lg:col-span-1">
                        <a href="#"
                            class="block  bg-[url('https://th.bing.com/th/id/OIP.Kl8zMN8T8r5W-Im1mOgneQHaJ3?w=208&h=277&c=7&r=0&o=7&dpr=1.3&pid=1.7&rm=3')] bg-cover no-repeat p-4 rounded-lg shadow-sm hover:shadow-md transition text-white">
                            <p class="text-sm font-bold ">K R Y S Brands</p>
                        </a>
                        <a href="#"
                            class="block bg-[url('https://th.bing.com/th/id/OIP.FzTFOZnghNXqgLOavlVRxwHaJ3?w=208&h=277&c=7&r=0&o=7&dpr=1.3&pid=1.7&rm=3')] bg-cover no-repeat p-4 rounded-lg shadow-sm hover:shadow-md transition text-white">
                            <p class="text-sm font-semibold">Aloruh</p>
                        </a>
                        <a href="#"
                            class="block bg-[url('https://th.bing.com/th/id/OIP.w-GKutuRQl4X2cq2FdmLpQHaJ3?w=208&h=277&c=7&r=0&o=7&dpr=1.3&pid=1.7&rm=3')] bg-cover no-repeat p-4 rounded-lg shadow-sm hover:shadow-md transition text-white">
                            <p class="text-sm font-semibold">Elenzga</p>
                        </a>
                    </div>
                </div>

                <div class=" p-4 rounded-lg shadow-sm">
                    <div class="overflow-x-auto">
                        <div
                            class="flex flex-nowrap md:grid md:grid-cols-4 lg:grid-cols-8 gap-6 md:gap-y-6 pt-4 min-w-[max-content] md:min-w-0">
                            <!-- Loop of categories -->
                            <a href="#" class="flex flex-col items-center gap-2 w-24 md:w-full group">
                                <div
                                    class="w-16 h-16 rounded-full bg-[url('https://th.bing.com/th/id/OIP.vOhBUmk2N6Hdo9sVisQpGwHaJ3?w=208&h=277&c=7&r=0&o=7&dpr=1.3&pid=1.7&rm=3')] bg-cover no-repeat flex items-center justify-center group-hover:bg-gray-300 transition-colors">
                                </div>
                                <p
                                    class="text-xs text-center text-gray-600 group-hover:text-gray-900 transition-colors">
                                    Women</p>
                            </a>
                            <a href="#" class="flex flex-col items-center gap-2 w-24 md:w-full group">
                                <div
                                    class="w-16 h-16 rounded-full bg-[url('https://img.ltwebstatic.com/v4/p/abccv/2026/04/22/77/177685253619bf210a55dcf6f48ffd12477f0b75ad_thumbnail_240x.webp')] bg-cover no-repeat group-hover:bg-gray-300">
                                </div>
                                <p class="text-xs text-center text-gray-600 group-hover:text-gray-900">Curve</p>
                            </a>
                            <a href="#" class="flex flex-col items-center gap-2 w-24 md:w-full group">
                                <div
                                    class="w-16 h-16 rounded-full bg-[url('https://img.ltwebstatic.com/v4/p/abccv/2026/05/13/b0/1778657360ba7e03fe9620eaaed3c935352f96d860_thumbnail_240x.webp')] bg-cover no-repeat group-hover:bg-gray-300">
                                </div>
                                <p class="text-xs text-center text-gray-600 group-hover:text-gray-900">Kids</p>
                            </a>
                            <a href="#" class="flex flex-col items-center gap-2 w-24 md:w-full group">
                                <div
                                    class="w-16 h-16 rounded-full bg-[url('https://img.ltwebstatic.com/v4/p/abccv/2026/04/16/e4/177634559311e4543404c0ef9820d172081aee8ddd_thumbnail_240x.webp')] bg-cover no-repeat group-hover:bg-gray-300">
                                </div>
                                <p class="text-xs text-center text-gray-600 group-hover:text-gray-900">Men</p>
                            </a>
                            <a href="#" class="flex flex-col items-center gap-2 w-24 md:w-full group">
                                <div
                                    class="w-16 h-16 rounded-full bg-[url('https://img.ltwebstatic.com/v4/p/abccv/2026/04/22/09/1776851748c2dc3968f20136e5b65d770e6d7c354d_thumbnail_240x.webp')] bg-cover no-repeat group-hover:bg-gray-300">
                                </div>
                                <p class="text-xs text-center text-gray-600 group-hover:text-gray-900">Sports & Outdoor
                                </p>
                            </a>
                            <a href="#" class="flex flex-col items-center gap-2 w-24 md:w-full group">
                                <div
                                    class="w-16 h-16 rounded-full bg-[url('https://img.ltwebstatic.com/images3_ccc/2024/09/24/b5/1727144603913866589eec5507ae8c5890638c9ff8_thumbnail_240x.webp')] bg-cover no-repeat group-hover:bg-gray-300">
                                </div>
                                <p class="text-xs text-center text-gray-600 group-hover:text-gray-900">Beauty & Health
                                </p>
                            </a>
                            <a href="#" class="flex flex-col items-center gap-2 w-24 md:w-full group">
                                <div
                                    class="w-16 h-16 rounded-full bg-[url('https://img.ltwebstatic.com/v4/p/abccv/2026/04/21/e7/1776771030405da62969ea5597bf732d5985267066_thumbnail_240x.webp')] bg-cover no-repeat group-hover:bg-gray-300">
                                </div>
                                <p class="text-xs text-center text-gray-600 group-hover:text-gray-900">Office &
                                    School...</p>
                            </a>
                            <a href="#" class="flex flex-col items-center gap-2 w-24 md:w-full group">
                                <div
                                    class="w-16 h-16 rounded-full bg-[url('https://img.ltwebstatic.com/v4/p/abccv/2026/04/22/99/1776852751ee07a5b261c06e82316cb604c534f21b_thumbnail_240x.webp')] bg-cover no-repeat group-hover:bg-gray-300">
                                </div>
                                <p class="text-xs text-center text-gray-600 group-hover:text-gray-900">Denim</p>
                            </a>

                        </div>
                    </div>

                </div>

            </div>
        </section>

        <section id="Projects" class="py-16">
            <div
                class="w-fit mx-auto grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 justify-items-center justify-center gap-y-12 gap-x-8 px-4">
                <div v-for="(product, index) in filterredProduct" :key="product.id"
                    class="bg-white rounded-2xl shadow-lg hover:shadow-2xl transition-all duration-300 transform hover:-translate-y-2 overflow-hidden border-2 border-pink-100">
                    
                    <div class="relative overflow-hidden">
                        <img @click="openModal(index)" :src="product.image" :alt="product.name"
                            class="cursor-pointer h-72 w-72 object-cover rounded-t-xl hover:scale-105 transition-transform duration-500" />
                        <div
                            class="absolute top-3 right-3 bg-pink-400 text-white text-xs font-bold px-3 py-1 rounded-full shadow-md">
                            sale
                        </div>
                    </div>

                    <!-- Product Info -->
                    <div class="px-5 py-4 w-72 bg-white">
                        <span class="text-gray-800 font-medium text-base block truncate">{{ product.name
                        }}</span>

                        <div class="flex items-center justify-between mt-3">
                            <p class="text-xl font-bold text-pink-600 cursor-auto">${{ product.price }}</p>

                            <!-- Cart Icon-->
                            <div @click="openModal(index)"
                                class="cursor-pointer hover:scale-110 transition-transform duration-200 bg-purple-100 p-2 rounded-full hover:bg-purple-200">
                                <svg aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="22" height="22"
                                    fill="none" viewBox="0 0 24 24" class="text-purple-600">
                                    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"
                                        stroke-width="2"
                                        d="M5 4h1.5L9 16m0 0h8m-8 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4Zm8 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4Zm-8.5-3h9.25L19 7h-1M8 7h-.688M13 5v4m-2-2h4" />
                                </svg>
                            </div>
                        </div>

                       
                        <div class="mt-3 flex items-center text-yellow-500">
                            <svg width="16" height="16" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 0l2.5 7.5h7.5l-6 4.5 2.5 7.5-6-4.5-6 4.5 2.5-7.5-6-4.5h7.5z" />
                            </svg>
                            <svg width="16" height="16" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 0l2.5 7.5h7.5l-6 4.5 2.5 7.5-6-4.5-6 4.5 2.5-7.5-6-4.5h7.5z" />
                            </svg>
                            <svg width="16" height="16" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 0l2.5 7.5h7.5l-6 4.5 2.5 7.5-6-4.5-6 4.5 2.5-7.5-6-4.5h7.5z" />
                            </svg>
                            <svg width="16" height="16" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 0l2.5 7.5h7.5l-6 4.5 2.5 7.5-6-4.5-6 4.5 2.5-7.5-6-4.5h7.5z" />
                            </svg>
                            <svg width="16" height="16" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 0l2.5 7.5h7.5l-6 4.5 2.5 7.5-6-4.5-6 4.5 2.5-7.5-6-4.5h7.5z" />
                            </svg>
                            <span class="text-gray-500 text-xs ml-1">(5.0)</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>


    </body>

    <Modal v-if="modalOpen" :selectedProduct="products[currentIndex]" @close-modal="closeModal"
        @add-to-cart="addToCart" />
</template>