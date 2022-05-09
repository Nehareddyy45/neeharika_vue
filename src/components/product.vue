<template>


  <div>
    <h2>{{ product.productName }}</h2>
    <h2>{{ product.price }}</h2>
    <h2>{{ product.howToUse }}</h2>
    <h2> {{ product.ingredients }}</h2>
    <h2> {{ product.uses }}</h2>



  </div>
</template>

<script>

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'product',
  props: {
    product: JSON
  }
}
</script>

<style scoped>

h4 {
  margin: 2px;
}

div {
  background-color: #a1d4fd;
  color: black;
  padding: 1em;
}

.red {
  background-color: orangered !important;

}


</style>