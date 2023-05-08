<template>
  <div class="sidebar">
    <!-- Sidebar -->
    <aside class="sidebar__sidebar">...</aside>

    <!-- Main -->
    <main class="sidebar__main">
      <borderLiquid></borderLiquid>
      <mySwitch></mySwitch>
    </main>
</div>
</template>

<script setup>
import borderLiquid from "./components/border/border-liquid"
import mySwitch from "./components/checkbox/mySwitch.vue"


</script>

<style>
.sidebar {
    display: flex;
}

.sidebar__sidebar {
    width: 30%;
    background-color: #7f8fa6;
}

.sidebar__main {
    /* Take the remaining width */
    flex: 1;

    /* Make it scrollable */
    overflow: auto;
 
}
</style>
