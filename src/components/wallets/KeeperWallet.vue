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
    <span>
      Отсканируй QR-код в приложении <b>TonKeeper</b> или <a :href="transferUrl"><b>воспользуйся ссылкой</b></a>
    </span>
    <span><a class="instruction" href="https://telegra.ph/Kak-smintit-Tesla-Fest-NFT-09-21">Инструкция</a></span>
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

.container > span {
  color: white;
}

.container a {
  color: inherit;
  text-decoration: underline;
}
a.instruction {
  color: #FF8562;
  text-decoration: underline;
}

</style>
