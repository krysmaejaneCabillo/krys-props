20260601 13:15:14 || <script>
export default {
    props: {
        selectedProduct: {
            type: Object,
            // required: true,
            // default: () => ({
            //     name: '',
            //     price: 0,
            //     sku: '',
            //     description: '',
            //     features: [],
            //     image: ''
            // })
        }
    },
    data() {
        return {
            quantity: 1 
        };
    },

    methods: {
        closeModal() {
            this.$emit('close-modal');
        },
        confirmPurchase() {
            this.$emit('add-to-cart', {
                ...this.selectedProduct,
                quantity: this.quantity
            });
            this.closeModal()
        }
    }
};
</script>

<template>
    <div class="fixed inset-0 bg-black/50 backdrop-blur-sm flex items-center justify-center z-50 p-3 sm:p-4 overflow-y-auto">
        <!-- Modal Container -->
        <div class="bg-gradient-to-b from-amber-50 to-orange-50 rounded-2xl max-w-3xl w-full my-4 sm:my-6 shadow-2xl border-2 border-amber-100/50 transform transition-all">
            <div class="p-4 sm:p-5 md:p-6 relative">
                <!-- Decorative Corner Elements -->
                <div class="absolute top-3 left-3 text-amber-200">
                    <svg width="24" height="24" fill="currentColor" viewBox="0 0 24 24">
                        <path d="M12 2L14.5 7H20L16 11L17.5 17L12 13.5L6.5 17L8 11L4 7H9.5L12 2Z"/>
                    </svg>
                </div>
                <div class="absolute top-3 right-3 text-amber-200">
                    <svg width="24" height="24" fill="currentColor" viewBox="0 0 24 24">
                        <path d="M12 2L14.5 7H20L16 11L17.5 17L12 13.5L6.5 17L8 11L4 7H9.5L12 2Z"/>
                    </svg>
                </div>

                <div class="flex flex-wrap -mx-3 relative z-10">
                    <!-- Images Section -->
                    <div class="w-full md:w-1/2 px-3 mb-5 md:mb-0">
                        <div class="relative group">
                            <div class="absolute -inset-1 bg-gradient-to-r from-amber-200 to-orange-200 rounded-xl blur opacity-60 group-hover:opacity-80 transition duration-300"></div>
                            <div class="relative bg-white p-3 rounded-xl shadow-md border border-amber-100">
                                <img 
                                    :src="selectedProduct.image" 
                                    alt="Product" 
                                    class="w-full h-auto rounded-lg object-cover max-h-[300px] mx-auto"
                                >
                                <!-- Small heart icon on image -->
                                <div class="absolute top-5 right-5 bg-white/80 backdrop-blur-sm p-2 rounded-full shadow-sm">
                                    <svg width="18" height="18" fill="#f59e0b" viewBox="0 0 24 24">
                                        <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/>
                                    </svg>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Details Section -->
                    <div class="w-full md:w-1/2 px-3">
                        <h2 class="text-2xl sm:text-3xl font-bold text-amber-900 mb-2 leading-tight">
                            {{ selectedProduct.name }}
                        </h2>
                        
                        <p class="text-amber-700/70 text-sm mb-3 flex items-center gap-1.5">
                            <svg width="14" height="14" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M5 4h3l2 4h8a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2z"/>
                            </svg>
                            SKU: {{ selectedProduct.sku }}
                        </p>

                        <div class="mb-4 bg-white/60 backdrop-blur-sm p-3 rounded-lg shadow-sm border border-amber-100/50">
                            <span class="text-2xl sm:text-3xl font-bold text-amber-800 mr-2">
                                ${{ selectedProduct.price }}
                            </span>
                            <span class="text-amber-600 text-sm">USD</span>
                        </div>

                        <p class="mb-4 text-amber-800/80 text-sm sm:text-base leading-relaxed">
                            {{ selectedProduct.description }}
                        </p>

                        <!-- Quantity Selector -->
                        <div class="mb-5">
                            <label class="block text-sm font-medium text-amber-900 mb-2 flex items-center gap-1.5">
                                <svg width="16" height="16" fill="currentColor" viewBox="0 0 24 24">
                                    <path d="M19 3h-1V2c0-.55-.45-1-1-1s-1 .45-1 1v1H8V2c0-.55-.45-1-1-1s-1 .45-1 1v1H5c-1.11 0-1.99.9-1.99 2L3 19c0 1.1.89 2 2 2h14c1.11 0 2-.9 2-2V5c0-1.1-.89-2-2-2zm0 16H5V8h14v11z"/>
                                </svg>
                                Quantity:
                            </label>
                            <div class="flex items-center">
                                <button 
                                    @click="quantity = Math.max(1, quantity - 1)"
                                    class="w-9 h-9 flex items-center justify-center bg-amber-100 hover:bg-amber-200 text-amber-800 rounded-l-lg transition shadow-sm border border-amber-200"
                                >
                                    −
                                </button>
                                <input 
                                    type="number" 
                                    min="1" 
                                    v-model="quantity"
                                    class="w-14 h-9 text-center border-y border-amber-200 bg-white focus:outline-none focus:ring-1 focus:ring-amber-400 text-amber-900 font-medium"
                                >
                                <button 
                                    @click="quantity += 1"
                                    class="w-9 h-9 flex items-center justify-center bg-amber-100 hover:bg-amber-200 text-amber-800 rounded-r-lg transition shadow-sm border border-amber-200"
                                >
                                    +
                                </button>
                            </div>
                        </div>

                        <!-- Action Buttons -->
                        <div class="flex flex-col sm:flex-row gap-3 mb-5">
                            <button 
                                @click="confirmPurchase"
                                class="flex-1 flex cursor-pointer items-center justify-center gap-2 bg-gradient-to-r from-amber-500 to-amber-600 hover:from-amber-600 hover:to-amber-700 text-white py-2.5 px-4 rounded-xl transition-all shadow-md hover:shadow-lg transform hover:-translate-y-0.5"
                            >
                                <svg width="18" height="18" fill="currentColor" viewBox="0 0 24 24">
                                    <path d="M7 18c-1.1 0-1.99.9-1.99 2S5.9 22 7 22s2-.9 2-2-.9-2-2-2zM1 2v2h2l3.6 7.59-1.35 2.45c-.16.28-.25.61-.25.96 0 1.1.9 2 2 2h12v-2H7.42c-.14 0-.25-.11-.25-.25l.03-.12.9-1.63h7.45c.75 0 1.41-.41 1.75-1.03l3.58-6.49c.08-.14.12-.31.12-.48 0-.55-.45-1-1-1H5.21l-.94-2H1zm16 16c-1.1 0-1.99.9-1.99 2s.89 2 1.99 2 2-.9 2-2-.9-2-2-2z"/>
                                </svg>
                                Add to Cart
                            </button>
                            
                            <button 
                                class="flex-1 flex cursor-pointer items-center justify-center gap-2 bg-amber-50 hover:bg-amber-100 text-amber-800 py-2.5 px-4 rounded-xl transition-all shadow-sm border border-amber-200/50"
                            >
                                <svg width="18" height="18" fill="currentColor" viewBox="0 0 24 24">
                                    <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/>
                                </svg>
                                Wishlist
                            </button>
                        </div>

                        <!-- Close Button -->
                        <button 
                            class="text-sm text-amber-600 hover:text-amber-800 transition flex items-center gap-1.5 mt-2 cursor-pointer" 
                            @click="closeModal"
                        >
                            <svg width="14" height="14" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M19 6.41L17.59 5 12 10.59 6.41 5 5 6.41 10.59 12 5 17.59 6.41 19 12 13.41 17.59 19 19 17.59 13.41 12z"/>
                            </svg>
                            Close
                        </button>
                    </div>
                </div>

                <!-- Bottom Decoration -->
                <div class="flex justify-center mt-4 pt-2">
                    <div class="flex gap-2">
                        <svg width="16" height="16" fill="#fcd34d" viewBox="0 0 24 24">
                            <path d="M12 2L14.5 7H20L16 11L17.5 17L12 13.5L6.5 17L8 11L4 7H9.5L12 2Z"/>
                        </svg>
                        <svg width="16" height="16" fill="#fbbf24" viewBox="0 0 24 24">
                            <path d="M12 2L14.5 7H20L16 11L17.5 17L12 13.5L6.5 17L8 11L4 7H9.5L12 2Z"/>
                        </svg>
                        <svg width="16" height="16" fill="#f59e0b" viewBox="0 0 24 24">
                            <path d="M12 2L14.5 7H20L16 11L17.5 17L12 13.5L6.5 17L8 11L4 7H9.5L12 2Z"/>
                        </svg>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>