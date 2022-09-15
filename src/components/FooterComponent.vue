<template>
    <div class="footer">
        <div class="item-count">
            <img src="/img/svg/icon_nft_line.svg" alt="">
            <span>3888 <span style="color: #f00">из 8888</span></span>
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
