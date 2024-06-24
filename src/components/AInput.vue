<template>
    <div class="container">

        <input  type="text" placeholder="search" @focus="focus">
        <div class="options-container">
            <ul v-if="focused" class="options-col">
                <li v-for="city in cities" class="options-row">{{ city.city }}</li>
            </ul>
        </div>

    </div>
</template>

<script setup>

import citiesData from '@/data/cities.js'

import { ref } from 'vue'

const cities = ref(citiesData)
const focused = false

</script>

<style scoped>
* {
    box-sizing: border-box;
}
.container {
    display: flex;
    flex-direction: column;

    width: 100%;
    overflow: hidden;
}

input {
    font-size: 1.6rem;

    padding: .7rem;
    max-width: 100%;

    border: 1px solid #cccccc;
    border-radius: 15px;  

    background: #fafafa;

    transition: all .3s ease;
}

input:focus {
    background: #fff;
    border-radius: 15px 15px 0 0;

    border-color: pink;
}

.options-container {
    overflow: hidden;
    border-radius: 0 0 15px 15px;
   
}

.options-col {
    border: 1px solid #cccccc;
    border-radius: 0 0 15px 15px;
    max-height: 30rem;


    list-style-type: none;
    overflow: auto;
    margin: 0;
    padding: 0;

    font-size: 1.4rem;
    color: #777;

    background: #fafafa
}

.options-row {
    padding: .2rem .7rem;
}

.options-row:hover {
    background: #ededed;
}

</style>