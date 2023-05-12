<template>
  <div class="sidebar">
    <!-- Sidebar -->
    <aside class="sidebar__sidebar">...</aside>

    <!-- Main -->
    <main class="sidebar__main">
      <borderLiquid></borderLiquid>
      <mySwitch></mySwitch>
      <Siderbar_first></Siderbar_first>
      <DragBlock></DragBlock>
    </main>
</div>
</template>

<script setup>
import borderLiquid from "./components/border/border-liquid"
import mySwitch from "./components/checkbox/mySwitch.vue"
import Siderbar_first from "./components/sidebar/Sidebar_first.vue"
import DragBlock from "./components/drag/dragBlock.vue"


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
    overflow: hidden;
 
}
</style>
