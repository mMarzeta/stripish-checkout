<script setup>
import {library} from '@fortawesome/fontawesome-svg-core'
import {faArrowLeft} from '@fortawesome/free-solid-svg-icons'
import {FontAwesomeIcon} from '@fortawesome/vue-fontawesome'
import {ref} from 'vue'

library.add(faArrowLeft)

const showLogo = ref(false)

const handleMouseOver = () => {
  showLogo.value = true
}

const handleMouseOut = () => {
  showLogo.value = false
}

</script>

<template>
  <a href="/" @mouseover="handleMouseOver" @mouseout="handleMouseOut">
    <FontAwesomeIcon class="backIcon" :class="{ active: showLogo}" :icon="['fas', 'arrow-left']"/>
    <transition name="fade" mode="out-in">
      <span v-if="showLogo" class="backText">
        Back
      </span>
      <span v-else class="backText">
        <img src="@/components/icons/sample-logo.png" alt="Logo" class="backLogo">
        Logo
      </span>
    </transition>
  </a>
  <br>
</template>

<style lang="scss" scoped>
@import '@/assets/scss/_variables.scss';

a {
  text-decoration: none;
  color: $button-back-light;
}

a:hover {
  color: $button-back-hover;
}

.backIcon {
  margin-right: 10px;
}

.fade-enter-active {
  transition: opacity 0.15s;
}

.fade-leave-active {
  transition: opacity 0s;
}

.fade-enter, .fade-leave-to {
  opacity: 0;
}

.active {
  margin-left: -10px;
}

.backLogo {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  object-fit: cover;
}
</style>