<template>
 <div class="t-catalog">
   <div class="t-catalog_list">
     <t-catalog-item
     v-for="product in products"
     :key="product.article"
     v-bind:product_data="product"
     @sendArticle="showChildArticleConsole"
     />

   </div>

 </div>
</template>

<script>
import tCatalogItem from './t-catalog-item'
export default {
  name: "t-catalog",
  components: {
    tCatalogItem
  },
  props: {},
  data() {
    return {
      products: [
        {
          image: "1.jpg",
          name: "T-shirt 1",
          price: 2100.234234234,
          article: "T1",
          available: true,
          category: "Men"
        },
        {
          image: "2.jpg",
          name: "T-shirt 2",
          price: 3150.12312412,
          article: "T2",
          available: true,
          category: "Women"
        },
        {
          image: "3.jpg",
          name: "T-shirt 3",
          price: 4200.51524,
          article: "T3",
          available: false,
          category: "Women"
        }
      ]
    }
  },
  computed: {},
  methods: {
    showChildArticleConsole(data) {
      console.log(data)
    }
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