<template>
  <div class="container">

    <Header siteName="Stunj Organic products"
            authorName="Neeharika reddy"/>

    <productbox :products="products"  />

  </div>
</template>
<script>


import Header from './components/Header.vue'
import productbox from './components/productbox.vue'

export default {
  name: 'App',
  components: {

    Header,
    productbox
  },

  data(){
    return {
      products: []
    }
  },
  methods: {
    async fetchproducts(){
      const url='https://nehareddyfinalproject.herokuapp.com/api';
      return new Promise((resolve, request)=>{
        try {
          fetch(url).then((res)=> {return res.json()}).then((res)=>{
            resolve(
                res.map(pos=>({
                  ...pos
                }))
            )
          });
        }catch (err){
          request(err);
        }
      })
    }
  },

  async created(){
    this.products = await this.fetchproducts()
    console.log(this.products);
  }
}
</script>

<style>


@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 10;
  padding: 10;
}

body {
  font-family: 'Montserrat', sans-serif;
}
.container {
  max-width: 1500px;
  margin: 40px auto;
  overflow: auto;
  min-height: 500px;
  border: 0.3em solid red;
  padding: 30px;
  border-radius: 5px;
}

div{
  margin-bottom: 0.5em;
}



</style>


