<template>
  <div
    style="height: 500px; width: 500px; background: red; margin: auto; position: relative"
    ref="container"
  >
    <DraggableContainer>
      <DraggableResizer>
        <img
          alt="Vue logo"
          src="./assets/logo.png"
          ref="target"
          @click="x"
          width="200"
          height="200"
        />
      </DraggableResizer>
      <DraggableResizer>
        <img
          alt="Vue logo"
          src="./assets/logo.png"
          ref="target"
          @click="x"
          width="200"
          height="200"
        />
      </DraggableResizer>
    </DraggableContainer>

    {{ left }}
  </div>
</template>
<script setup lang="ts">
  import { DraggableResizer, DraggableContainer } from "../components";
  import "../components/index.scss";
  import { useState } from "vue3-normal-library";

  const [left, setLeft] = useState(0);

  const x = () => {
    setLeft(left.value + 1);
  };
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
