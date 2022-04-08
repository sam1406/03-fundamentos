<template>
    <h2>{{costomTitle}} </h2>
    <p>{{count}} <sup>2</sup> = {{squareValue}} </p>

    <button @click="decrement()">-</button>
    <button @click="increment()">+</button>
</template>

<script>
export default {
    props:{
        title: {
            type: String,
            default: 'Counter'
        },
        start: {
            type: Number,
            default: 1,
            validator: function(value) {
                return value > 100;
            }
        }
    },
    data() {
        return {
            count: this.start
        }
    },
    methods: {
        increment() {
            this.count++
        },
        decrement() {
            this.count--
        },
        getSquareValue() {
            return this.count * this.count
        }
    },
    computed: {
        squareValue() {
            return this.count * this.count
        },
        costomTitle() {
            return this.title ? this.title : 'Counter';
        }
    }
}
</script>

<style>

</style>