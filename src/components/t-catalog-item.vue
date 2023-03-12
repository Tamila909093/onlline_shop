<template>
  <div class="t-catalog-item">
    <h4>item 1</h4>
    <img src="" alt="">
   <p> price 100</p>
   <p> add to cart</p>
    <t-cart></t-cart>

  </div>
</template>

<script>
import tCart from './t-cart'

export default {
  name: "t-catalog-item",
  components: {
    tCart
  },
  props: {},
  data() {
    return {}
  },
  computed: {}
}
</script>

<style lang="scss">
.t-catalog-item {
    display: flex;
    flex-direction: column;
    //padding: 8px;
    margin: 8px;
    align-items: center;
    border-radius: 4px;
    box-shadow: 1px 1px 11px #00000036;
    flex-basis: 25%;
    padding: $padding 5px;
    //& > * {
    //
    //}
}

</style>