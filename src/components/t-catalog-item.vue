<template>
  <div class="t-catalog-item">
    <img class="t-catalog-item__img" :src="require('../assets/images/' + product_data.image)" alt="img">
    <h4 class="t-catalog-item__name">{{product_data.name}}</h4>
    <p class="t-catalog-item__price" > Price: {{product_data.price}} $</p>
    <p class="t-catalog-item__category" > {{product_data.category}}</p>
    <button
        class="t-catalog-item__btn btn"
        @click="sendDataToParent">
       <t-cart />
      Add to Cart</button>

  </div>
</template>

<script>
import tCart from './t-cart'

export default {
  name: "t-catalog-item",
  components: {
    tCart
  },
  props: {
    product_data: {
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
    sendDataToParent() {
      this.$emit('sendArticle', this.product_data.article)
    }
  }
}
</script>

<style lang="scss">

.t-catalog-item {
    display: flex;
    flex-basis: 25%;
    flex-direction: column;
    margin: 8px;
    align-items: center;
    border-radius: 4px;
    box-shadow: 1px 1px 11px #00000036;
    padding: 8px;
    & > * {
      padding: 8px 5px;
    }
  &__img {
    max-width: 100px;
  }
}

</style>