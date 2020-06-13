<template>
<div>
    <div class="arrowLeft" @click="precSlide()">
        ←
    </div>

    <div class="container">
        <img v-for="img in images" v-bind:key="img.map((el, i) => {return i})"/>
    </div>

    <div class="arrowRight" @click="nextSlide()">
        →
    </div>
</div>
</template>

<script>

export default {
    name:"Slides",
    active: false,
    props: {
        index: Number
    },
    data() {
        return {
            images: [
                '../assets/slide1.jpg',
                '../assets/slide2.jpg',
                '../assets/slide3.jpg',
                '../assets/slide4.jpg',
                '../assets/slide5.jpg',
            ]
        }
    },
    methods: {
        precSlide() {
            console.log("back")
        },
        nextSlide() {
            return this.index
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
        width: 100%;
        object-fit: cover;
    }
    .arrowLeft, .arrowRight {
        height: 720px;
        width: 260px;
        background: #101010;
        color: white;
        font-weight: bold;
        font-size: 32px;
        cursor: pointer;
    }
</style>