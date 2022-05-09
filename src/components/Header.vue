<template>
<div>
    <h1> {{siteName}} </h1>
    <h4> {{authorName}}  </h4>
</div>
</template>

<script>

export default{
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Header',
    props:{
        siteName: String,
        authorName:String
    }
}

</script>

<style scoped>

div{
    text-align: center;
    background-color: rgb(73, 148, 185);
}

</style>