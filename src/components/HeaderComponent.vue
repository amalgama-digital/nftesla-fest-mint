<template>
    <div class="header">
        <img src="/img/svg/logo_tf.svg" alt="">
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

@media only screen and (max-width: 1100px) {
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
    width: 60%;
}
.links > a {
    font-size: 18px;
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
    gap: .5rem;
    width: fit-content;
    max-width: 15rem;
}
.links > a#email > .hideable {
    display: inline-block;
}
</style>
