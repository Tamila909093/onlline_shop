<template>
  <div class="t-cart">
    <h1>Cart</h1>
    <t-cart-item
       v-for="(item, index) in cart_data"
       :key="item.article"
       :cart_item_data="item"
       @deleteFromCart="deleteFromCart(index)"
    />
<!--<div class="btn">-->
<!-- <a href="t-cart.vue">cart </a>-->
<!--</div>-->
  </div>
</template>

<script>
import tCartItem from './t-cart-item.vue'
import {mapActions} from "vuex";
export default {
  name: "t-cart",
  components: {
    tCartItem
  },
  props: {
    cart_data: {
      type: Array,
      default() {
        return []
      }
    }
  },
  data() {
    return {}
  },
  computed: {},
  methods: {
    ...mapActions([
      'DELETE_FROM_CART'
    ]),
    deleteFromCart(index) {
      this.DELETE_FROM_CART(index)
    }
  }
}
</script>

<style lang="scss" >

</style>