<template>
  <div class="product-tile">
    Core Product Tile
    <!-- Product name and price with price filter -->
    {{ product.name}} - {{ product.price | price }} 
    <!-- Add to cart button. Pass whole product as prop -->
  </div>
</template>

<script>
import AddToCart from './AddToCart.vue'
import { thumbnail } from '../../lib/filters'

export default {
  name: 'product-tile',
  props: ['product'],
  components: { AddToCart },
  computed: {
    thumbnail () {
      return thumbnail(this.product.image, 310, 300)
    }
  }
}
</script>