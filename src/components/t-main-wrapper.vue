<template>
  <div class="t-main-wrapper">
    <h2> {{title}}</h2>
    <t-catalog />

    <t-cart
        v-if="CART.length"
        :cart_data="CART"


    />

  </div>
</template>

<script>
    import tCatalog from './t-catalog'
    import {mapGetters} from "vuex";
    import tCart from './t-cart'

    export default {
      name: 't-main-wrapper',
      components: {
        tCatalog,
        tCart
      },                             // child for this components
      props: {},                     // прилетает в компонент из родителя
      data() {                       // персональные данные нашего компонента
        return {                     // всегда возвращает
          title: 'Catalog'
        }
      },
      computed: {
        ...mapGetters([
            'CART'
        ])
      },                  // вычислительные свойства компонента
      methods: {},                   // click, modal, animation , то что отлавливает действия пользователя
      watch: {},                     // следить за изменением и  что-то делать
      mounted() {}                 // hook  когда компонент полностью загрузится

    }
</script>

<style lang="scss" >
    .t-main-wrapper {
      max-width: 1220px;
      margin: 0 auto;
    }
</style>