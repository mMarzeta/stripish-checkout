<script setup>
import {library} from '@fortawesome/fontawesome-svg-core'
import {faArrowLeft} from '@fortawesome/free-solid-svg-icons'
import {FontAwesomeIcon} from '@fortawesome/vue-fontawesome'
import {ref} from 'vue'

library.add(faArrowLeft)

const showLogo = ref(false)
defineProps({
  companyName: {
    type: String,
    default: 'Company'
  }
})

const handleMouseOver = () => {
  showLogo.value = true
}

const handleMouseOut = () => {
  showLogo.value = false
}

</script>

<template>
  <a href="/" @mouseover="handleMouseOver" @mouseout="handleMouseOut">
    <FontAwesomeIcon class="back-icon" :class="{ active: showLogo}" :icon="['fas', 'arrow-left']"/>
    <Transition mode="out-in">
      <span v-if="showLogo" class="back-text">
        Back
      </span>
      <span v-else class="back-text">
        <img src="@/components/icons/sample-logo.png" alt="Logo" class="back-logo">
        {{ companyName }}
      </span>
    </Transition>
  </a>
</template>

<style lang="scss" scoped>
@import '@/assets/scss/_variables.scss';

a {
  display: inline-block;
  text-decoration: none;
  color: $button-back-light;
  width: 200px;
  height: 35px;
}

a:hover {
  color: $button-back-hover;
}

.back-icon {
  margin-right: 10px;
  color: $text-light;
}

.active {
  margin-left: -2px;
}

.back-logo {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  object-fit: cover;
  margin-top: -5px
}

.v-enter-active,
.v-leave-active {
  transition: opacity 0.1s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

.back-text {
  color: $text-light-active;
}
</style>