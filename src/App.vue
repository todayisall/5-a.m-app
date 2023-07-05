<script setup lang="ts">
import Clock from "@/components/Clock/index.vue";
import PunchIn from "@/components/PunchIn/index.vue";
</script>

<template>
  <div class="container">
    <div class="clock-wrap">
      <Clock />
    </div>
    <div class="punch-wrap">
      <PunchIn />
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100vh;
  gap: 32px;
}

.clock-wrap,.punch-wrap {
  width: 100%;
  text-align: center;
}

</style>
