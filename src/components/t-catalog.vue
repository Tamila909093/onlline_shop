<template>
 <div class="t-catalog">
   <div class="t-catalog_list">
     <t-catalog-item
     v-for="product in PRODUCTS"
     :key="product.article"
     v-bind:product_data="product"
     @addToCart="addToCart"
     />
   </div>

 </div>
</template>

<script>
import tCatalogItem from './t-catalog-item'
import {mapActions, mapGetters} from 'vuex'

export default {
  name: "t-catalog",
  components: {
    tCatalogItem
  },
  props: {},
  data() {
    return {
    }
  },
  computed: {
    ...mapGetters([
        'PRODUCTS'
    ]),
  },
  methods: {
    ...mapActions([
        'GET_PRODUCTS_FROM_API',
        'ADD_TO_CART'
    ]),
    addToCart(data) {
      this.ADD_TO_CART(data)
    }
  },
  mounted() {
    this.GET_PRODUCTS_FROM_API()
    .then((response) => {
      if (response.data) {
        console.log('data arrived!', response.data)
      }
    })
  }
}
</script>

<style lang="scss" >
  .t-catalog {
    &_list {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
    }
  }
</style>