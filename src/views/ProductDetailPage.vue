<template>
<div id="page-wrap">
  <div id="img-wrap">
    <img v-bind:src="productProperty.imageUrl">
  </div>
  <div id="product-details">
    <h1>{{ productProperty.name }}</h1>
    <h3 id="price">${{ productProperty.price }}</h3>
    <p>Average Rating: {{ productProperty.rating }}</p>
    <button id="add-to-cart">Add to Cart</button>
    <h4>Description</h4>
    <p>{{ productProperty.description }}</p>
  </div>
</div>
</template>

<script>
  import { products } from '../fake-data'
  export default {
    name: 'ProductDetailPage',
    data () {
      return {
        // only pass through single product
        // vue provides data points in components, they all start with $
        productProperty: products.find((p)=> p.id === this.$route.params.id)
      }
    }
  };
</script>

<style scoped>
  #page-wrap {
    margin-top: 16px;
    padding: 16px;
    max-width: 600px;
  }

  #img-wrap {
    text-align: center;
  }

  img {
    width: 400px;
  }

  #product-details {
    padding: 16px;
    position: relative;
  }

  #add-to-cart {
    width: 100%;
  }

  #price {
    position: absolute;
    top: 24px;
    right: 16px;
  }
</style>