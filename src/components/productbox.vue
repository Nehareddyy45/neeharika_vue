<template>

  <div class="productbox">

    <div v-for="product in products" :key="product.id" >
      <product :product="product"/>
    </div>

  </div>

</template>

<script>

import product from "./product.vue"
export default{
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'productbox',
  components: {
    product
  },
  props: {
    products: JSON
  }

}

</script>

<style>

.productbox{

  background-color: rgba(33, 222, 138, 0.73);
  padding: 1em;
  color: #946565;
}
</style>