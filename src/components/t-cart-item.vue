<template>
  <div class="t-cart-item">
     <img class="t-cart-item__img" :src="require('../assets/images/' + cart_item_data.image)" alt="img">
    <div class="v-cart-item__info">
      <p>{{cart_item_data.name}}</p>
      <p>{{cart_item_data.price}}</p>
      <p>{{cart_item_data.article}}</p>
    </div>
    <div class="v-cart-item__quantity">
      <p>Qty:</p>
      {{cart_item_data.quantity}}
    </div>
    <button @click="deleteFromCart">Delete</button>
  </div>
</template>

<script>
// import tCart from './t-cart.vue'
export default {
  name: "t-cart-item",
  components: {
    // tCart
  },
  props: {
    cart_item_data: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  data() {
    return {}
  },
  computed: {},
  methods: {
    deleteFromCart() {
      this.$emit('deleteFromCart')
    }
  },
  mounted() {
      this.$set(this.cart_item_data, 'quantity', 1)
  }
}
</script>

<style lang="scss">

.t-cart-item {
  display: flex;
  flex-wrap: nowrap;
  justify-content: space-around;
  align-items: center;
  box-shadow: 1px 1px 11px #00000036;
  padding: 10px;
  margin: 10px;
  &__img {
    max-width: 50px;

  }
}

</style>