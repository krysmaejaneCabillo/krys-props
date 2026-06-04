<script>
import ConfirmationModal from '../Modal/ConfirmationModal.vue';

export default {
    components: {
        ConfirmationModal
    },
    props: {
        cart: {
            type: Array,

        },

    },
    emits: ['remove-item'],
    data() {
        return {

            confirmOpen: false,
            currentIndex: 0,
            confirmed: []

        };
    },

    methods: {
        removeItem(id) {
            this.$emit('remove-item', id)
        },
        openModal(index) {
            this.currentIndex = index;
            this.confirmOpen = true;
        },
    }
};
</script>

<template>

    <div class="bg-pink-50 min-h-screen font-sans">
        <!-- Main Content -->
        <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-6 sm:py-8">
            <!-- Progress Steps -->
            <div
                class="flex flex-wrap justify-center items-center gap-2 sm:gap-3 md:gap-5 mb-8 bg-white rounded-3xl shadow-sm py-4 px-3 sm:px-6 max-w-3xl mx-auto">
                <p
                    class="font-semibold text-pink-600 cursor-pointer transition-all hover:text-pink-700 hover:scale-105">
                    Cart </p>
                <p class="text-pink-300">></p>
                <p class="text-gray-500 cursor-pointer transition-colors hover:text-pink-500">Place Order </p>
                <p class="text-pink-300 hidden sm:block">></p>
                <p class="text-gray-500 cursor-pointer transition-colors hover:text-pink-500">Pay </p>
                <p class="text-pink-300 hidden sm:block">></p>
                <p class="text-gray-500 cursor-pointer transition-colors hover:text-pink-500">Order Complete </p>
            </div>

            <!-- Promotional Banners -->
            <div class="flex justify-center items-center">
                <div class="flex flex-col sm:flex-row gap-3 sm:gap-4 mb-8 max-w-4xl mx-auto">
                    <div
                        class="flex items-center gap-2 bg-green-50/80 backdrop-blur-sm text-green-800 border border-green-200 rounded-2xl px-3 py-2 shadow-sm hover:shadow-md transition-shadow w-full sm:w-auto">
                        <svg class="flex-shrink-0" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="20"
                            height="20" fill="none" viewBox="0 0 24 24">
                            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                d="M13 7h6l2 4m-8-4v8m0-8V6a1 1 0 0 0-1-1H4a1 1 0 0 0-1 1v9h2m8 0H9m4 0h2m4 0h2v-4m0 0h-5m3.5 5.5a2.5 2.5 0 1 1-5 0 2.5 2.5 0 0 1 5 0Zm-10 0a2.5 2.5 0 1 1-5 0 2.5 2.5 0 0 1 5 0Z" />
                        </svg>
                        <span class="text-xs sm:text-sm">Buy ₱36 more for <span class="font-bold">Free
                                Shipping!</span></span>
                        <span class="text-green-700 font-semibold ml-auto sm:ml-1 cursor-pointer hover:underline">Add
                            →</span>
                    </div>

                    <div
                        class="flex items-center gap-2 bg-rose-50/80 backdrop-blur-sm text-rose-800 border border-rose-200 rounded-2xl px-3 py-2 shadow-sm hover:shadow-md transition-shadow w-full sm:w-auto">
                        <svg aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="none"
                            viewBox="0 0 24 24">
                            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                d="M5 11.917 9.724 16.5 19 7.5" />
                        </svg>
                        <span class="text-xs sm:text-sm">Extra <span class="font-bold">18% OFF</span> after order</span>
                    </div>
                </div>
            </div>

            <!-- Main Grid -->
            <div class="flex justify-center items-center">
                <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 lg:gap-8 max-w-7xl mx-auto">
                    <!-- Cart Items Section -->
                    <div class="lg:col-span-2 space-y-5">
                        <!-- Empty Cart -->
                        <div v-if="cart.length === 0" class="text-center bg-white rounded-3xl shadow-sm py-16 px-4">
                            <div class="text-6xl mb-4">🛍️</div>
                            <p class="text-2xl sm:text-3xl font-bold text-pink-500 mb-2">Your cart is empty</p>
                            <p class="text-gray-500">Add some cute items to make it happy!</p>
                        </div>

                        <!-- Cart Items List -->
                        <div v-else>

                            <div
                                class="bg-rose-50/80 backdrop-blur-sm text-rose-800 border border-rose-200 rounded-sm text-xl font-bold px-3 py-2 shadow-sm hover:shadow-md transition-shadow w-full sm:w-auto mb-2">
                                <input type="checkbox" checked="checked">
                                <label class="container ml-2">All Item
                                    <span class="checkmark"></span>
                                </label>
                            </div>
                            <div class="bg-white rounded-3xl shadow-sm p-4 sm:p-5 mb-4 hover:shadow-md transition-all duration-300 border border-pink-100/50"
                                v-for="(item, index) in cart" :key="item.id">
                                <div class="flex flex-wrap sm:flex-nowrap items-center gap-4">
                                    <img @click="openModal(index)" :src="item.image" alt=""
                                        class="w-20 h-20 sm:w-24 sm:h-24 object-cover rounded-2xl shadow-sm hover:scale-105 transition-transform">
                                    <div class="flex-1 min-w-[150px]">
                                        <h3 class="font-semibold text-gray-800 text-lg mb-1">{{ item.name }}</h3>
                                        <p class="text-sm text-pink-500">Qty: {{ item.quantity }} × ${{ item.price }}
                                        </p>
                                    </div>
                                    <div
                                        class="font-bold text-gray-800 text-lg w-full sm:w-auto text-right sm:text-left">
                                        ${{ (item.price * item.quantity).toFixed(2) }}
                                    </div>
                                    <button @click="removeItem(item.id)"
                                        class="text-rose-400 hover:text-rose-600 w-8 h-8 flex items-center justify-center rounded-full hover:bg-rose-50 transition-colors text-xl font-bold ml-auto sm:ml-0">
                                        ×
                                    </button>
                                </div>

                                <!-- Order Summary Section -->

                            </div>
                        </div>
                    </div>



                    <!-- Payment Methods -->
                    <div class="bg-white rounded-3xl shadow-sm p-5 sm:p-6 border border-pink-100/50 h-fit">
                        <h2 class="font-bold text-xl text-pink-500 mb-4">We Accept</h2>
                        <div class="grid grid-cols-6 sm:grid-cols-6 gap-2 sm:gap-3">
                            <img src="//img.ltwebstatic.com/images3_pi/2024/06/25/54/17193084623789a558f934389f07b55391e120d31a.webp"
                                class="rounded-lg hover:scale-110 transition-transform shadow-sm" alt="Payment method">
                            <img src="//img.ltwebstatic.com/images2_pi/2018/06/06/15282719811871317559.webp"
                                class="rounded-lg hover:scale-110 transition-transform shadow-sm" alt="Payment method">
                            <img src="//img.ltwebstatic.com/images3_pi/2021/03/09/161528368123dd7a35ad8708b0dfc74b3630526891.webp"
                                class="rounded-lg hover:scale-110 transition-transform shadow-sm" alt="Payment method">
                            <img src="//img.ltwebstatic.com/images3_pi/2025/02/26/5f/1740552723c023d4dd4f85c2e9eaae9e4b06b64b83.webp"
                                class="rounded-lg hover:scale-110 transition-transform shadow-sm" alt="Payment method">
                            <img src="//img.ltwebstatic.com/images2_pi/2018/06/06/15282732983375743706.webp"
                                class="rounded-lg hover:scale-110 transition-transform shadow-sm" alt="Payment method">
                            <img src="//img.ltwebstatic.com/images2_pi/2018/06/06/1528273036537082707.webp"
                                class="rounded-lg hover:scale-110 transition-transform shadow-sm" alt="Payment method">
                            <img src="//img.ltwebstatic.com/images2_pi/2018/06/06/15282731342688549608.webp"
                                class="rounded-lg hover:scale-110 transition-transform shadow-sm" alt="Payment method">
                            <img src="//img.ltwebstatic.com/images2_pi/2018/06/06/1528273241354964734.webp"
                                class="rounded-lg hover:scale-110 transition-transform shadow-sm" alt="Payment method">
                            <img src="//img.ltwebstatic.com/images3_pi/2023/01/17/1673934516ab4978470be637393a0825fa0d2dab38.webp"
                                class="rounded-lg hover:scale-110 transition-transform shadow-sm" alt="Payment method">
                            <img src="//img.ltwebstatic.com/images3_pi/2021/06/18/16239951302ccd8394442a589591f651d83003e5e0.webp"
                                class="rounded-lg hover:scale-110 transition-transform shadow-sm" alt="Payment method">
                            <img src="//img.ltwebstatic.com/images3_pi/2023/10/23/0a/16980396186012819c03a750ddb746c24e6d927d6a.webp"
                                class="rounded-lg hover:scale-110 transition-transform shadow-sm" alt="Payment method">
                            <img src="//img.ltwebstatic.com/images3_pi/2021/01/15/1610701410b3781f00695b77b833e6b6a5e38331a3.webp"
                                class="rounded-lg hover:scale-110 transition-transform shadow-sm" alt="Payment method">
                        </div>
                    </div>
                </div>
            </div>
        </main>
    </div>
    <ConfirmationModal v-if="confirmOpen" :check="cart[currentIndex]" @closeThyModal="confirmOpen = false" />
</template>