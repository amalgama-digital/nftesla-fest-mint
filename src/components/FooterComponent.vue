<script setup>
import { onMounted, ref } from 'vue';

import TonWeb from 'tonweb';

const props = defineProps([
    'contractAddress',
    'providerUrl'
]);

const tonweb = new TonWeb(new TonWeb.HttpProvider(props.providerUrl));

const collection = new TonWeb.token.nft.NftCollection(
    tonweb.provider,
    {address: props.contractAddress}
);

const items = ref(0);

onMounted(
    async () => {
        const total = 8888;
        const cd = await collection.getCollectionData();
        items.value = total - cd.nextItemIndex;

        setInterval( async () => {
            const cd = await collection.getCollectionData();
            items.value = total - cd.nextItemIndex;
        }, 5000);
    }
);

</script>

<template>
    <div class="footer">
        <div class="item-count">
            <img src="/img/svg/icon_nft_line.svg" alt="">
            <span>{{ items }} <span style="color: #f00">из 8888</span></span>
        </div>
        <div class="sponsors">
            <a href="https://tesla-n.ru/">
                <img src="/img/png/partners_tsln.png" alt="">
            </a>
            <a href="https://trading-club.info/">
                <img src="/img/png/partners_tc.png" alt="">
            </a>
            <a href="https://ton.org/">
                <img src="/img/png/partners_ton.png" alt="">
            </a>
        </div>
    </div>
</template>

<style scoped>
@media screen and (max-width: 760px) {
    .footer {
        flex-direction: column !important;
        gap: 10px;
    }
}
.footer {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    width: 75%;
}

.item-count {
    display: flex;
    align-items: center;
    gap: .7rem;
    color: #fff;
}

.sponsors {
    display: flex;
    justify-content: end;
    align-items: center;
    gap: 20px;
    width: 60%;
}

a > img {
    max-width: 100%;
    max-height: 78px;
}

</style>
