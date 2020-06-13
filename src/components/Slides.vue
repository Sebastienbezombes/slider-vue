<template>
<div>
    <div class="arrowLeft" @click="precSlide()">←</div>

    <div class="container">
        <img v-for="img in images" :key="img.index" :src="img.source" v-show="img.index === i"/>
    </div>

    <div class="arrowRight" @click="nextSlide()">→</div>
</div>
</template>

<script>

export default {
    name:"Slides",
    data: () => ({
        i: 1,
        images: [
            {index: 1, source:require('../assets/slide1.jpg')},
            {index: 2, source:require('../assets/slide2.jpg')},
            {index: 3, source:require('../assets/slide3.jpg')},
            {index: 4, source:require('../assets/slide4.jpg')},
            {index: 5, source:require('../assets/slide5.jpg')},
        ],
    }),
    methods: {
        precSlide() {
            this.i--;
            this.index = this.i;
            this.index < 1 ? this.i = 5 : '';
        },
        nextSlide() {   
            this.i++;
            this.index = this.i;
            this.index > 5 ? this.i = 1 : '';
        }
    }
}
</script>

<style scoped>
    div {
        height: 100vh;
        width: 100vw;
        display: flex;
        justify-content: center;
        align-items: center;
        background: #232423;
    }
    .container {
        height: 720px;
        width: 1280px;
        background: red;
        overflow: hidden;
        border-radius: 6px;
    }
    img {
        width: 1280px;
        height: 720px;
    }
    .arrowLeft, .arrowRight {
        height: 720px;
        width: 260px;
        background: #101010;
        color: white;
        font-weight: bold;
        font-size: 32px;
        cursor: pointer;
        user-select: none;
    }
</style>