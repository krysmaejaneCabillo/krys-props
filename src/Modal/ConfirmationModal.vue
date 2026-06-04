<script>
export default {
    props: {
        check: {
            type: Array,

        },


    },
    data() {
        return {
            subtotal: 0,
            shippingFee: 0,
            tax: 0,
            total: 0
        };
    },
    emits: ['checkThisout', "closeThyModal"],
    methods: {
        close(id) {
            this.$emit('closeThyModal', id)
        },
        purchase() {
            this.$emit('checkThisout', this.check)
            console.log(this.check);
            this.close()
        },

    }
}
</script>

<template>
    <div
        class="fixed inset-0 bg-black/50 backdrop-blur-sm flex items-center justify-center z-50 p-3 sm:p-4 overflow-y-auto">

        <div class="flex flex-cols">
            <div
                class="bg-white rounded-3xl shadow-sm p-4 sm:p-5 mb-4 hover:shadow-md transition-all duration-300 border border-pink-100/50 mt-30">
                <div class="flex flex-wrap sm:flex-nowrap items-center gap-4">
                    <img :src="check.image" alt="thumbnail"
                        class="w-20 h-20 sm:w-24 sm:h-24 object-cover rounded-2xl shadow-sm hover:scale-105 transition-transform">
                    <div class="flex-1 min-w-[150px]">
                        <h3 class="font-semibold text-gray-800 text-lg mb-1">{{ check.name }}</h3>

                    </div>
                    <div class="font-bold text-gray-800 text-lg w-full sm:w-auto text-right sm:text-left">
                        ${{ (check.price) }}
                    </div>
                    <button @click="close(check)"
                        class="text-rose-400 hover:text-rose-600 w-8 h-8 flex items-center justify-center rounded-full hover:bg-rose-50 transition-colors text-xl font-bold ml-auto sm:ml-0">
                        ×
                    </button>

                </div>
                <div class="space-y-5">
                    Summary Card
                    <div class="">
                        <div class="mb-6">
                            <h2 class="font-bold text-2xl text-pink-500 mb-1">Order Summary </h2>
                            <p class="text-sm text-gray-500">Final prices will update at checkout</p>
                        </div>

                        <div class="space-y-3 text-gray-700">
                            <div class="flex justify-between items-center py-1">
                                <span>Subtotal</span>
                                <span class="font-medium">${{ subtotal }}</span>
                            </div>
                            <div class="flex justify-between items-center py-1">
                                <span>Shipping Fee</span>
                                <span class="font-medium text-green-600">{{ shippingFee === "0.00" ?
                                    'Free'
                                    : '$' +
                                    shippingFee }}</span>
                            </div>
                            <div class="flex justify-between items-center py-1">
                                <span>Tax</span>
                                <span class="font-medium">${{ tax }}</span>
                            </div>
                            <div
                                class="border-t border-pink-100 pt-4 mt-2 flex justify-between font-bold text-xl text-pink-500">
                                <span>Total</span>
                                <span>${{ total }}</span>
                            </div>
                        </div>

                        Promo Code
                        <div class="mt-6">
                            <label class="block text-sm font-medium text-gray-600 mb-2">Promo Code
                                🎟️</label>
                            <div class="flex gap-2">
                                <input type="text"
                                    class="flex-1 px-4 py-2.5 border border-pink-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-pink-300 focus:border-pink-400 transition-all bg-pink-50/30"
                                    placeholder="Enter code">
                                <button
                                    class="px-5 py-2.5 bg-pink-100 text-pink-700 rounded-xl hover:bg-pink-200 transition-colors font-medium">
                                    Apply
                                </button>
                            </div>
                        </div>

                        Action Buttons
                        <div class="mt-7 space-y-3">
                            <button @click="purchase"
                                class="w-full py-3.5 bg-gradient-to-r from-pink-400 to-pink-500 text-white rounded-xl font-medium hover:from-pink-500 hover:to-pink-600 transition-all shadow-md hover:shadow-lg transform hover:-translate-y-0.5">
                                Proceed to Checkout
                            </button>
                            <a href="#"
                                class="block text-center text-pink-500 hover:text-pink-600 hover:underline transition-colors font-medium">
                                ← Continue Shopping
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </div>

    </div>

</template>