<script>
export default {
    props: {
        cartCount: {
            type: Number,
            default: 0
        }
    },
    data() {
        return {
            searchBar: ''
        }
    },
    computed: {
        filteredProducts() {
            if (!this.searchBar.trim) {
                return this.products
            }
            const query = this.searchBar.toLowerCase().trim();
            return this.products.filter(product => 
                product.name.toLowerCase().includes(query)
            )
        }

    },
    methods: {
        addModal() {
            this.$emit('openAddModal')
        },
        navigate(page) {
            this.$emit('goTo', page)
        },
        search(){
            this.$emit(search-bar, this.searchBar )
        }
    }
}

</script>

<template>

    <div class="font-sans sticky top-0 z-1000">
        <!-- Announcement Bar -->
        <div class="bg-pink-100 text-amber-900 text-center py-2 px-4 text-[13px] font-medium">
            Free Shipping on Orders $1,500+ | 30-Day Easy Return
        </div>

        <!-- Main Navbar -->
        <header class=" bg-black border-b border-gray-200 shadow-sm">
            <div class="max-w-[1400px] mx-auto">
                <!-- Desktop & Tablet View -->
                <div class="hidden md:flex items-center justify-between px-4 lg:px-6 py-3">
                    <!-- Logo -->
                    <a @click="navigate('Home')" href="#" class="text-[28px] font-bold text-white tracking-wider">K R Y
                        S</a>

                    <!-- Main Categories -->
                    <nav class="flex items-center space-x-8 text-[14px] font-medium text-white">
                        <a href="#"
                            class="relative font-medium lg:text-[14px] text-white hover:text-pink-200 py-2 transition-all duration-300
                 after:content-[''] after:absolute after:w-full after:h-[2px] after:bg-gradient-to-r after:from-pink-50 after:to-pink-300 
                 after:left-0 after:bottom-0 after:scale-x-0 hover:after:scale-x-100 after:origin-left after:transition-transform after:duration-300">New
                            In</a>
                        <a href="#"
                            class="relative font-medium lg:text-[14px] text-white hover:text-pink-200 py-2 transition-all duration-300
                 after:content-[''] after:absolute after:w-full after:h-[2px] after:bg-gradient-to-r after:from-pink-50 after:to-pink-300 
                 after:left-0 after:bottom-0 after:scale-x-0 hover:after:scale-x-100 after:origin-left after:transition-transform after:duration-300">Women</a>
                        <a href="#"
                            class="relative font-medium lg:text-[14px] text-white hover:text-pink-200 py-2 transition-all duration-300
                 after:content-[''] after:absolute after:w-full after:h-[2px] after:bg-gradient-to-r after:from-pink-50 after:to-pink-300 
                 after:left-0 after:bottom-0 after:scale-x-0 hover:after:scale-x-100 after:origin-left after:transition-transform after:duration-300">Men</a>
                        <a href="#"
                            class="relative font-medium lg:text-[14px] text-white hover:text-pink-200 py-2 transition-all duration-300
                 after:content-[''] after:absolute after:w-full after:h-[2px] after:bg-gradient-to-r after:from-pink-50 after:to-pink-300 
                 after:left-0 after:bottom-0 after:scale-x-0 hover:after:scale-x-100 after:origin-left after:transition-transform after:duration-300">Kids</a>
                        <a href="#"
                            class="relative font-medium lg:text-[14px] text-white hover:text-pink-200 py-2 transition-all duration-300
                 after:content-[''] after:absolute after:w-full after:h-[2px] after:bg-gradient-to-r after:from-pink-50 after:to-pink-300 
                 after:left-0 after:bottom-0 after:scale-x-0 hover:after:scale-x-100 after:origin-left after:transition-transform after:duration-300">Home
                            &
                            Kitchen</a>
                        <a href="#"
                            class="relative font-medium lg:text-[14px] text-white hover:text-pink-200 py-2 transition-all duration-300
                 after:content-[''] after:absolute after:w-full after:h-[2px] after:bg-gradient-to-r after:from-pink-50 after:to-pink-300 
                 after:left-0 after:bottom-0 after:scale-x-0 hover:after:scale-x-100 after:origin-left after:transition-transform after:duration-300">Beauty</a>
                        <a href="#"
                            class="relative font-medium lg:text-[14px] text-white hover:text-pink-200 py-2 transition-all duration-300
                 after:content-[''] after:absolute after:w-full after:h-[2px] after:bg-gradient-to-r after:from-pink-50 after:to-pink-300 
                 after:left-0 after:bottom-0 after:scale-x-0 hover:after:scale-x-100 after:origin-left after:transition-transform after:duration-300">Curve
                            &
                            Plus</a>
                        <a href="#"
                            class="relative font-medium lg:text-[14px] text-white hover:text-pink-200 py-2 transition-all duration-300
                 after:content-[''] after:absolute after:w-full after:h-[2px] after:bg-gradient-to-r after:from-pink-50 after:to-pink-300 
                 after:left-0 after:bottom-0 after:scale-x-0 hover:after:scale-x-100 after:origin-left after:transition-transform after:duration-300">Sale</a>
                    </nav>

                    <!-- Search & Icons -->
                    <div class="flex items-center space-x-5">
                        <!-- Search Box -->
                        <div class="relative">
                            <input v-model="searchBar" type="text" placeholder="Search products, brands and styles"
                                class="bg-white rounded-full py-2.5 px-4 pl-10 w-[240px] lg:w-[320px] text-[14px] focus:outline-none border border-transparent focus:border-pink-300  focus:ring-2 transition-all">
                            <!-- Search SVG Icon -->
                            <svg class="w-5 h-5 text-shein.gray absolute left-3 top-1/2 -translate-y-1/2" fill="none"
                                stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                                <path d="M21 21l-4.35-4.35M17 11a6 6 0 1 1-12 0 6 6 0 0 1 12 0z" />
                            </svg>
                        </div>

                        <!-- Icons -->
                        <a href="#" class="text-white hover:text-pink-200 transition-colors">
                            <!-- User SVG -->
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                                <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2" />
                                <circle cx="12" cy="7" r="4" />
                            </svg>
                        </a>
                        <a href="#" class="text-white hover:text-pink-200 transition-colors">
                            <!-- Heart SVG -->
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                                <path
                                    d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z" />
                            </svg>
                        </a>
                        <a @click="navigate('cart')" href="#"
                            class="text-white hover:text-pink-200 transition-colors relative">
                            <!-- Cart SVG -->
                            <svg class="w-6 h-6" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24"
                                height="24" fill="none" viewBox="0 0 24 24">
                                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M5 4h1.5L9 16m0 0h8m-8 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4Zm8 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4Zm-8.5-3h9.25L19 7H7.312" />
                            </svg>

                            <span
                                class="absolute -top-2 -right-2 bg-pink-200 text-white text-[10px] font-bold rounded-full w-4 h-4 flex items-center justify-center">{{ cartCount }}</span>
                        </a>
                    </div>
                </div>

                <!-- Mobile View -->
                <div class="md:hidden">
                    <!-- Top Bar -->
                    <div class="flex items-center justify-between px-3 py-3">
                        <!-- Menu Icon -->
                        <button class="text-whitw">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                                <path d="M3 6h18M3 12h18M3 18h18" />
                            </svg>
                        </button>

                        <!-- Logo -->
                        <a @click="navigate('Home')" href="#" class="text-[22px] font-bold text-white tracking-wider">K
                            R Y S</a>

                        <!-- Icons -->
                        <div class="flex items-center space-x-4">
                            <a href="#" class="text-white">
                                <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="2"
                                    viewBox="0 0 24 24">
                                    <path d="M21 21l-4.35-4.35M17 11a6 6 0 1 1-12 0 6 6 0 0 1 12 0z" />
                                </svg>
                            </a>
                            <a href="#" class="text-white">
                                <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="2"
                                    viewBox="0 0 24 24">
                                    <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2" />
                                    <circle cx="12" cy="7" r="4" />
                                </svg>
                            </a>
                            <a href="#" @click="navigate('cart')" class="text-white relative">
                                <svg class="w-6 h-6" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24"
                                    height="24" fill="none" viewBox="0 0 24 24">
                                    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"
                                        stroke-width="2"
                                        d="M5 4h1.5L9 16m0 0h8m-8 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4Zm8 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4Zm-8.5-3h9.25L19 7H7.312" />
                                </svg>
                                <span
                                    class="absolute -top-2 -right-2 bg-pink-200 text-white text-[9px] font-bold rounded-full w-3.5 h-3.5 flex items-center justify-center">{{ cartCount }}</span>
                            </a>
                        </div>
                    </div>

                    <!-- Scrollable Categories -->
                    <div
                        class="overflow-x-auto scrollbar-hide px-3 pb-2 flex space-x-6 text-[13px] font-medium text-white whitespace-nowrap">
                        <a href="#" class="hover:text-pink-200 transition-colors text-uppercase">New In</a>
                        <a href="#" class="hover:text-pink-200 transition-colors text-uppercase">Women</a>
                        <a href="#" class="hover:text-pink-200 transition-colors text-uppercase">Men</a>
                        <a href="#" class="hover:text-pink-200 transition-colors text-uppercase">Kids</a>
                        <a href="#" class="hover:text-pink-200 transition-colors text-uppercase">Home</a>
                        <a href="#" class="hover:text-pink-200 transition-colors text-uppercase">Beauty</a>
                        <a href="#" class="hover:text-pink-200 transition-colors text-uppercase">Curve</a>
                        <a href="#" class="hover:text-pink-200 transition-colors text-uppercase">Shoes</a>
                        <a href="#" class="hover:text-pink-200 transition-colors text-uppercase">Bags</a>
                        <a href="#" class="hover:text-pink-200 transition-colors text-uppercase">Sale</a>
                    </div>
                </div>
            </div>
        </header>


    </div>

</template>