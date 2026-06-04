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
      searchBar: '',
      checkOutItem: []
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
    checkOut(check) {
      this.checkOutItem.push({ ...check })
    }
    // removeCheckout(index){
    //   this.checkOutItem.splice(index, 1)
    // }

  }
}
</script>

<template>
  <Navbar @openAddModal="showAddProduct = true" @goTo="changePage" :cartCount="cart.length"
    @search-bar="handleSearch" />
  <HeroSec v-if="currentPage === 'Home'" :addingProduct="showAddProduct" @close-modal="showAddProduct = false"
    @add-to-cart="addItem" :bar="searchBar" />
  <AddCart v-if="currentPage === 'cart'" :cart="cart" @remove-item="(id) => cart = cart.filter(item => item.id !== id)" />
  <PurchaseHistory v-if="currentPage === 'history'" :history="checkOutItem" @checkThisout="checkOut" />
</template>
