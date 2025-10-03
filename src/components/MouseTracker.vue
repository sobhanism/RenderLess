<template>
  <slot 
    :position="mousePosition"
  ></slot>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'



const mousePosition = ref({ x: 0, y: 0 })

const updateMousePosition = (event) => {
  mousePosition.value.x=event.clientX
  mousePosition.value.y=event.clientY
}
onMounted(() => {
  window.addEventListener('mousemove', updateMousePosition)
})

onUnmounted(() => {
  window.removeEventListener('mousemove', updateMousePosition)
})
</script>