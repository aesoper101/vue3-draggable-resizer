<template>
  <div
    style="height: 500px; width: 500px; background: red; margin: auto; position: relative"
    ref="container"
  >
    {{ r }}
    <DraggableContainer>
      <DraggableResizer v-model:r="r">
        <img alt="Vue logo" src="./assets/logo.png" ref="target" width="200" height="200" />
      </DraggableResizer>
      <DraggableResizer>
        <img alt="Vue logo" src="./assets/logo.png" ref="target" width="200" height="200" />
      </DraggableResizer>
    </DraggableContainer>
  </div>
</template>
<script setup lang="ts">
  import { DraggableResizer, DraggableContainer } from "../components";
  import "../components/index.scss";
  import { ref } from "vue";

  const r = ref(0);
</script>
<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
