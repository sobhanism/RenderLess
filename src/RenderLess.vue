<template>
  <div id="renderless">   
    <div>
    <MouseTracker v-slot="{ position }">
      <div class="mouse-info">
        <h2>موقعیت فعلی موس:</h2>
        <p>X: {{ position.x }}</p>
        <p>Y: {{ position.y }}</p>
      </div>
    </MouseTracker>
  </div>
  <div class="provide-example">
    <MouseTrackerProvide>
      <ChildeProvideComponent />
    </MouseTrackerProvide>  
  </div>
 <div>
  </div>
  
 </div>
</template>

<script setup>
 import MouseTracker from './components/MouseTracker.vue'
import MouseTrackerProvide from './components/MouseTrackerProvide.vue'
import ChildeProvideComponent from './components/ChildeProvideComponent.vue'
</script>

<style>
#renderless {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 20px;
  min-height: 100vh;
  position: relative;
}

.mouse-info {
  background: #f0f0f0;
  border-radius: 8px;
  padding: 20px;
  margin: 20px auto;
  max-width: 300px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.mouse-info h2 {
  color: #333;
  margin-bottom: 15px;
}

.mouse-info p {
  margin: 5px 0;
  font-size: 18px;
  font-weight: bold;
  color: #666;
}
.provide-example {
   background: #c135ac;
  border-radius: 8px;
  padding: 20px;
  margin: 20px auto;
  max-width: 300px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  color: white;
}

</style>
