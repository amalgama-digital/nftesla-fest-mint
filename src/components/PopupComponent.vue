<script setup>
import { ref, watch } from "vue";
const props = defineProps(["popupShow"]);

const popupClasses = {
  show: "popup-show",
  hide: "popup-hide",
};
const popupClass = ref("popup-hide");

watch(
  () => props.popupShow,
  () => {
    popupClass.value = props.popupShow ? popupClasses.show : popupClasses.hide;
  }
);
</script>

<template>
  <div :class="['popup', popupClass]">
    <div class="popup__content">
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
.popup {
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: rgba(250, 250, 250, 0.11);
  backdrop-filter: blur(2px);

  position: absolute;
  width: 100%;
  height: 100%;

  z-index: 1;
}

.popup__content {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;

  height: 80vh;
  width: 70vw;

  background-color: black;
  border-radius: 8px;
}
.popup-show {
  visibility: visible;
}
.popup-hide {
  visibility: hidden;
}
</style>
