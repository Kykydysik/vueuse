<script setup lang="ts">
import { useFavicon } from '@vueuse/core'
import { computed, shallowRef } from 'vue'

const type = shallowRef('vueuse')

const favicon = computed(() =>
  type.value === 'vue' ? 'vue.png' : 'favicon-32x32.png')

useFavicon(favicon, {
  baseUrl: '/',
  rel: 'icon',
})
</script>

<template>
  <div>
    Change favicon to
  </div>
  <button @click="type = 'vue'">
    Vue
  </button>
  <button @click="type = 'vueuse'">
    VueUse
  </button>
</template>
