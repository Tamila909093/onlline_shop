<template>
 <div class="t-catalog">
   <div class="t-catalog_list">
     <t-catalog-item />
     <t-catalog-item />

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
    return {}
  },
  computed: {}
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