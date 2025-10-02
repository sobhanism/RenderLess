<template>
    <div>
        <h2>موقعیت موس در حالت provide: {{ mouseTracker.x }}, {{ mouseTracker.y }}</h2>
    </div>
    </template>
    <script setup >
    import { inject } from 'vue';
    const mouseTracker = inject('mouseTracker');
    </script>