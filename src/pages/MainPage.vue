<script setup>
import { ref } from "vue";

import ButtonMint from "../components/ButtonMint.vue";
import KeeperWallet from "../components/wallets/KeeperWallet.vue";
import PopupComponent from "../components/PopupComponent.vue";
import VideoBackground from "../components/VideoBackground.vue";
import HeaderComponent from "../components/HeaderComponent.vue";

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
    <VideoBackground />
    <popup-component :popup-show="popupShow">
      <button class="close" @click="closePopup">CLOSE</button>
      <keeper-wallet
        :contract-address="contractAddress"
        :amount="amount"
      ></keeper-wallet>
    </popup-component>
    <div class="main">
      <HeaderComponent />
      <div class="text-container">
        <span>
          Испытай удачу и <span style="color: red;">стань обладателем</span> новенькой <span style="color: red;">TESLA</span>
        </span>
      </div>
      <div class="text-container">
        <span>
          Текущая цена <span class="price">65$</span>
        </span>
      </div>
      <ButtonMint @click="showPopup" />
    </div>
    <!-- FooterVue -->
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
.main {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;
  position: fixed;
  width: 750px;
  height: 560px;
  border: 1px solid #161616;
  border-radius: 10px;

  background-color: #000;
}

.text-container {
  color: #fff;
  font-weight: 700;
  font-size: 32px;
  line-height: 39px;
}

.text-container > span {
  display: inline-block;
  width: 550px;
  overflow: hidden;
}
.price {
  background-color: #f00;
  border-radius: 10px;
  padding: 0px 10px;
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
