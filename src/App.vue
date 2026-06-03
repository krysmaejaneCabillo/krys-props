<script>
import Navbar from './components/Navbar.vue';
import HeroSec from './components/HeroSec.vue';
import AddCart from './components/AddCart.vue';
import PurchaseHistory from './components/PurchaseHistory.vue';

export default {
  components: {
    Navbar,
    HeroSec,
    AddCart,
    PurchaseHistory

  },
  data() {
    return {
      showAddProduct: false,
      currentPage: 'Home',
      cart: [],
      purchaseItem: [],
      searchBar: ''
    }
  },
  methods: {
    addModal() {
      this.showAddProduct = true
    },
    changePage(page) {
      this.currentPage = page;
    },
    addItem(product) {
      this.cart.push({ ...product });
    },
    handleSearch(searchValue) {
      this.searchBar = searchValue
    },
    handleHistory(cartItem) {
      this.purchaseItem.push({ ...cartItem });
    }
  }
}
</script>

<template>
  <Navbar @openAddModal="showAddProduct = true" @goTo="changePage" :cartCount="cart.length" @search-bar="handleSearch" />
  <HeroSec v-if="currentPage === 'Home'" :addingProduct="showAddProduct" @close-modal="showAddProduct = false"
    @add-to-cart="addItem" :bar="searchBar" />
  <AddCart v-if="currentPage === 'cart'" :cart="cart" @history="handleHistory" />
  <PurchaseHistory v-if="currentPage === 'history'" :checkoutItem="purchaseItem" />
</template>
