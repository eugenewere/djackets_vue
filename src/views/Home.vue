<template >
  <div class="home" >
    <section class="hero is-medium is-dark mb-6" >
      <div class="hero-body has-text-centered" >
        <p class="title mb-6" >Welcome to Djacket</p >
        <div class="subtitle" >
          The baddest jacket store in kenya online
        </div >
      </div >
    </section >
    <div class="column is-multiline" >
      <div class="column is-12" >
        <h2 class="is-size-2 has-text-centered" >
          Latest products
        </h2 >
      </div >
      <div class="row" >
        <ProductCard v-for="product in latestProducts" v-bind:key="product.id" :product="product" ></ProductCard >
      </div >
    </div >
  </div >
</template >

<script >
// @ is an alias to /src
import axios from 'axios'
// import ProductCard from '../components/ProductCard'

export default {
  name: 'Home',
  data() {
    return {
      latestProducts: []
    }
  },
  // components: {
  //   ProductCard
  // },
  mounted() {
    this.getLatestProperties();
  },
  methods: {
    getLatestProperties() {
      axios.get('/api/v1/latest_products/').then((response) => {
        console.log(response.data);
        this.latestProducts = response.data;
      }).catch((response) => {
        console.log(response.err)
      })
    }
  }
}
</script >
