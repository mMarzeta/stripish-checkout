<script setup>
import BackButton from './buttons/BackButton.vue'

const companyName = 'Akademia Kodu'

</script>

<template>
  <div class="container">
    <div class="back-button">
      <BackButton :company-name="companyName"/>
    </div>
    <br>
    Pay {{ companyName }}
    <br>
    <h1>
      US$199.00
    </h1>
  </div>
</template>

<style scoped>
.container {
  margin-left: 90px;
}

.back-button {
  margin-top: 55px;
  margin-left: -30px;
}
</style>