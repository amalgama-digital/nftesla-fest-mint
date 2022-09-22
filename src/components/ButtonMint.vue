<script setup></script>

<template>
  <button class="btn-mint">
    <img class="image" src="/img/svg/button_icon_nft.svg" alt="">
    MINT NFT
  </button>
</template>

<style>
.btn-mint {
  width: 76%;
  min-height: 70px;
  height: auto;
  cursor: pointer;
  text-align: center;
  background-color: rgb(255, 0, 0);
  color: white;
  border: none;
  border-radius: 40px;
  position: relative;
  font-size: 30px;
  line-height: 39px;
}

.btn-mint > .image {
  position: absolute;
  left: 10px;
  top: 10px;
  width: 48px;
}
</style>
