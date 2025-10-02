<template>
  <slot></slot>
  </template>
  <script setup>
  import { onMounted, onUnmounted, provide, ref } from 'vue';
  const mouseTracker=ref({x:0,y:0})
  const updateMousePosition = (event) => {
    mouseTracker.value.x=event.clientX
    mouseTracker.value.y=event.clientY
  }
  onMounted(() => {
    window.addEventListener('mousemove', updateMousePosition)
  })
  onUnmounted(() => {
    window.removeEventListener('mousemove', updateMousePosition)
  })
  provide('mouseTracker',mouseTracker)
  </script>