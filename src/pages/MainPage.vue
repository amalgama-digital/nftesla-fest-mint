<script setup>
import { ref } from "vue";

import ButtonMint from "../components/ButtonMint.vue";
import KeeperWallet from "../components/wallets/KeeperWallet.vue";
import PopupComponent from "../components/PopupComponent.vue";

// TODO: set to mainnet contract
// testing: kQAuPQ5pJHIT_yAlVGwrqp148LcmFgRSIIBQj8uQrSlxExOC
const contractAddress = "kQAuPQ5pJHIT_yAlVGwrqp148LcmFgRSIIBQj8uQrSlxExOC";

// TODO: set value
const amount = 0.07;

const popupShow = ref("hide");

function showPopup() {
  popupShow.value = true;
}

function closePopup() {
  popupShow.value = false;
}
</script>

<template>
  <div class="container">
    <popup-component :popup-show="popupShow">
      <button class="close" @click="closePopup">CLOSE</button>
      <keeper-wallet
        :contract-address="contractAddress"
        :amount="amount"
      ></keeper-wallet>
    </popup-component>
    <ButtonMint @click="showPopup" />
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  height: 100vh;
}
.close {
  display: block;
  position: absolute;
  top: 0;
  right: 1rem;
  color: red;
  border: none;
  padding: 0.8rem;
  text-decoration: underline;
  background: rgba(0, 0, 0, 0);
  cursor: pointer;
}
</style>
