<script>
import Navbar from './components/Navbar.vue';
import HeroSec from './components/HeroSec.vue';
import AddCart from './components/AddCart.vue';

export default {
  components: {
    Navbar,
    HeroSec,
    AddCart
  },
  data() {
    return {
      showAddProduct: false,
      currentPage: 'Home',
      cart: [],
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
      this.showAddProduct = true
    },
    changePage(page) {
      this.currentPage = page;
    },
    addItem(product) {
      this.cart.push({ ...product });
    }
  }
}
</script>

<template>
  <Navbar @openAddModal="showAddProduct = tru" @goTo="changePage" :cartCount="cart.length" @search-bar="filteredProducts" />
  <HeroSec v-if="currentPage === 'Home'" :addingProduct="showAddProduct" @closeThisModal="showAddProduct = false"
    @add-to-cart="addItem" />
  <AddCart v-if="currentPage === 'cart'" :cart="cart" />
</template>
