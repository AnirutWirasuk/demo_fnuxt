<template>
  <div class="container">
    <div class="card-deck mb-3 text-center">
      <Boxproduct 
      v-for="product in listproduct" 
      :key="product.id"
      :name="product.name"
      :price="product.price"
       />
    </div>
  </div>
</template>

<script>
import Boxproduct from '~/components/Boxproduct.vue'

export default {
  components: {
    Boxproduct
  },
  data() {
    return {
      listproduct: [
        {
          id: 1,
          name: 'test product',
          price: 200
        },
        {
          id: 2,
          name: 'test product',
          price: 300
        }
      ]
    }
  }
}
</script>

<style>
.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
