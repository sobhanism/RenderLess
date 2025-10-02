<template>
  <slot></slot>
  </template>
  <script setup>
  import { onMounted, onUnmounted, provide, ref } from 'vue';
  const mouseTracker=ref({x:0,y:0})
  const updateMouseTracker = (event) => {
    mouseTracker.value.x=event.clientX
    mouseTracker.value.y=event.clientY
  }
  onMounted(() => {
    window.addEventListener('mousemove', updateMouseTracker)
  })
  onUnmounted(() => {
    window.removeEventListener('mousemove', updateMouseTracker)
  })
  provide('mouseTracker',mouseTracker)
  </script>