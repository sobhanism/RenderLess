<template>
  <slot 
    :position="mousePosition"
  ></slot>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const mousePosition = ref({ x: 0, y: 0 })

const updateMousePosition = (event) => {
  mousePosition.value.x=event.clientX
  mousePosition.value.y=event.clientY
}
onMounted(() => {
  document.addEventListener('mousemove', updateMousePosition)
})

onUnmounted(() => {
  document.removeEventListener('mousemove', updateMousePosition)
})
</script>