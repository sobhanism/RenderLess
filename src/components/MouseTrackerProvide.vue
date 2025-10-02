<template>
  <slot></slot>
  </template>
  <script setup>
  import { onMounted, onUnmounted, provide, ref } from 'vue';
  const MouseTracker=ref({x:0,y:0})
  const updateMousePosition = (event) => {
    MouseTracker.value.x=event.clientX
    MouseTracker.value.y=event.clientY
  }
  onMounted(() => {
    document.addEventListener('mousemove', updateMousePosition)
  })
  onUnmounted(() => {
    document.removeEventListener('mousemove', updateMousePosition)
  })
  provide('MouseTracker',MouseTracker)
  </script>