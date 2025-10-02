<template>
    <div>
        <h2>موقعیت موس در حالت provide: {{ mousePosition.x }}, {{ mousePosition.y }}</h2>
    </div>
    </template>
    <script setup >
    import { inject, ref } from 'vue';
    const mousePosition = inject('MouseTracker', ref({x:0,y:0}));
    </script>