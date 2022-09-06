<script setup>
import { onMounted, ref } from "vue";

import QRCode from "qrcode";

const props = defineProps(["url"]);
const canvas = ref(undefined);

onMounted(() => {
  QRCode.toCanvas(canvas.value, props.url, {
    scale: 5,
    errorCorrectionLevel: "Q",
    color: {
      dark: "#ff0000ff",
      light: "#000000ff",
    },
  });
});
</script>

<template>
  <canvas ref="canvas"></canvas>
</template>

<style scoped>
canvas {
  border: 2px solid red;
  border-radius: 8px;
}
</style>
