<template>
<div>
    <h1>{{ count }}</h1>
    <button @click="divValue()">:</button>
    <button @click="lessValue()">-</button>
    <button @click="addValue()">+</button>
    <button @click="multValue()">x</button>
</div>
</template>

<script>

export default {
    name:"Cpt",
    props: {
        count: Number
    },
    methods: {
        divValue() {
            this.count/=2;
        },
        lessValue() {
            this.count--;
        },
        addValue() {
            this.count++;
        },
        multValue() {
            this.count*=2;
        },
    }
}
</script>

<style scoped>
    button:not(:last-child) {
        margin-right: 16px;
    }
</style>