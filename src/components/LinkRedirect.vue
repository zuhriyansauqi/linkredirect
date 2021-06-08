<template>
  <div class="link-redirect">
    {{ loadingText }}
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()

let loadingText = ref('Please wait ...')

setTimeout(() => {
  const { link } = route.query
  if (link) {
    window.location.href = link
  }
}, 3000)
</script>
