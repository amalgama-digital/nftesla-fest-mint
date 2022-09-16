<template>
    <div class="video-container">
        <div class="blur"></div>
        <video autoplay muted loop>
            <source
                src="https://dl.dropbox.com/s/xba19mevkx546rf/Tesla%20Model%203%20Ad_converted%20%281%29.mp4?dl=0"
                type="video/mp4"
            >
        </video>
    </div>
</template>

<style scoped>
    .video-container {
        display: block;
        position: fixed;
        top: 0;
        left: 0;
    }
    .video-container .blur {
        background-color: rgba(0, 0, 0, .7);
        width: 100%;
        height: 100%;
        position: fixed;
    }

    video {
        min-width: 100vw;
        min-height: 100vh;
    }
</style>
