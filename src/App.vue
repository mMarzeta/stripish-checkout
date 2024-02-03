<script setup>
import Basket from './components/Basket.vue'
import Checkout from './components/Checkout.vue'
</script>

<template>
  <div class="container-fluid">
    <div class="row align-items-center">
      <div class="col col-main-dark">
        <Basket/>
      </div>
      <div class="col col-main-light">
        <Checkout/>
      </div>
    </div>
  </div>
</template>
<style scoped>

</style>
