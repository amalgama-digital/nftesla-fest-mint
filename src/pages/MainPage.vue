<script setup>
import { ref } from "vue";

import ButtonMint from "../components/ButtonMint.vue";
import KeeperWallet from "../components/wallets/KeeperWallet.vue";
import PopupComponent from "../components/PopupComponent.vue";
import VideoBackground from "../components/VideoBackground.vue";
import HeaderComponent from "../components/HeaderComponent.vue";
import FooterComponent from "../components/FooterComponent.vue";

const providerUrl = "https://toncenter.com/api/v2/jsonRPC"

const contractAddress = "EQDjh6CTd-MUxh-E3VLtxELcVDs-FHztDpvOWqHkkp5C-hW1";
const collectionAddress = "EQCnXQ6HUs_VXXFUeiFWdjhdiy2FblDnJPVvr4GCqnt6aoiq";

const amount = 60;

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
      <button type="button" class="close" @click="closePopup">
      </button>
      <keeper-wallet
        :contract-address="contractAddress"
        :amount="amount"
      ></keeper-wallet>
    </popup-component>
    <div class="main">
      <HeaderComponent />
      <div class="text-container">
        <span>
          Возьми своего NFT-бурундука и стань обладателем новой <span style="color: red;">TESLA MODEL 3 PERFORMANCE</span>
        </span>
      </div>
      <div class="text-container">
        <span>
          Текущая цена <span class="price">60 TON</span>
        </span>
      </div>
      <ButtonMint @click="showPopup" />
      <footer-component
        :contract-address="collectionAddress"
        :provider-url="providerUrl"
      ></footer-component>
    </div>
  </div>
</template>

<style scoped>
@media only screen and (max-width: 810px) {
  .main {
    width: 100vw !important;
    height: 100vh !important;
    justify-content: center !important;
    gap: 2rem;
  }
}
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  height: 100vh;

  font-family: 'Montserrat', sans-serif;
  font-weight: 700;
}
.main {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;
  position: fixed;
  width: 65vw;
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
  width: 75%;
}

.text-container > span {
  display: inline-block;
  width: auto;
  max-width: 550px;
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
  width: 48px;
  height: 48px;
  top: .5rem;
  right: 1rem;
  color: red;
  border: none;
  text-decoration: underline;
  background-color: rgba(0, 0, 0, 0);
  background-image: url("/img/svg/close.svg");
  background-repeat: no-repeat;
  cursor: pointer;
}
</style>
