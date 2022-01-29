<template >
  <div class="column is-3" >
        <div class="box" >
          <figure class="image mb-4" >
            <img :src="product.image" :alt="product.name" >
          </figure >
          <h3 class="is-size-4" >
            {{ product.name }}
          </h3 >
          <p class="is-size-6 has-text-grey" >KES {{ product.price }}</p >
          View Details
        </div >
      </div >
</template >

<script >
export default {
  name: "ProductCard",
  props:{
    product:{
      required: true,
      type: Object,
    },

  }
}
</script >

<style scoped >
.image {
  margin-top: -1.125rem;
  margin-left: -1.125rem;
  margin-right: -1.125rem;
}
</style >