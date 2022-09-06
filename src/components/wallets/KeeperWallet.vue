<script setup>
import QrCode from "./keeper/QrCode.vue";
const props = defineProps(["contractAddress", "amount"]);

const amount = toNanoTon(props.amount);
const text = "mint";

const transferApiUrl = `https://app.tonkeeper.com/transfer`;
const query = `amount=${amount}&text=${text}`;
const transferUrl = `${transferApiUrl}/${props.contractAddress}?${query}`;

function toNanoTon(tons) {
  return tons * Math.pow(10, 9);
}
</script>

<template>
  <div class="container">
    <qr-code :url="transferUrl"></qr-code>
    <a :href="transferUrl">Scan QR code or <b>open with TonKeeper</b></a>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 1rem;

  font-size: 16px;
}

.container > a {
  color: white;
  text-decoration: none;
}
</style>
