<template>
    <div class="header">
        <a href="https://nftesla-fest.com/">
            <img src="/img/svg/logo_tf.svg" alt="">
        </a>
        <div class="links">
            <a id="telegram" href="https://t.me/NFTeslaFest"></a>
            <a id="instagram" href="https://instagram.com/teslafest.nft?igshid=YmMyMTA2M2Y="></a>
            <a id="email" href="mailto:admin@nftesla-fest.com">
                <img src="/img/svg/icon_mail.svg" alt="">
                <span class="hideable">admin@nftesla-fest.com</span>
            </a>
        </div>
    </div>
</template>

<style scoped>

@media only screen and (max-width: 1060px) {
    .links > a#email > .hideable {
        display: none !important;
    }
}

.header {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    width: 75%;
}
.links {
    display: flex;
    justify-content: end;
    gap: 15px;
    width: 65%;
}
.links > a {
    font-size: 16px;
    line-height: 30px;
    display: block;
    width: 34px;
    height: 34px;
    text-decoration: none;
    color: #f00;
    background-repeat: no-repeat;
}
.links > a#telegram {
    background-image: url("/img/svg/icon_tg.svg");
}
.links > a#instagram {
    background-image: url("/img/svg/icon_inst.svg");
}
.links > a#email {
    display: flex;
    justify-content: center;
    gap: .3rem;
    width: fit-content;
    max-width: 20rem;
}
.links > a#email > .hideable {
    display: inline-block;
}

.links > a#email {
    font-weight: 400;
}
</style>
