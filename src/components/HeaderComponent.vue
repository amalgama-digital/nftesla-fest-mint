<template>
    <div class="header">
        <img src="/img/svg/logo_tf.svg" alt="">
        <div class="links">
            <a id="telegram" href="https://t.me/NFTeslaFest"></a>
            <a id="instagram" href="https://instagram.com/"></a>
            <a id="email" href="mailto:admin@nftesla-fest.com">
                <span class="hideable">admin@nftesla-fest.com</span>
            </a>
        </div>
    </div>
</template>

<style scoped>

@media only screen and (max-width: 460px) {
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
    gap: 20px;
    float: right;
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
    background-image: url("/img/svg/icon_mail.svg");
    background-position-x: left;
    width: 13.5rem;
    text-align: end;
}
.links > a#email > .hideable {
    display: inline-block;
}
</style>
