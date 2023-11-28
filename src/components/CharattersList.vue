<script> 

import { store } from '../store.js';
import AppCard from './AppCard.vue';

export default{
    data() {
        return {
            store: store,
        };
    },
    components: { AppCard }
};

</script>

<template>

    <div>
        <div class="container">
            <h1>card</h1>
            <div class="row" row-cols-5 g-4>
                <div class="col-3" v-for="(character, index) in store.cardsList">
                   <AppCard :character="character" :key="index" />
                </div>
            </div>
        </div>
    </div>

    

</template>

<style lang="scss" scoped>


</style>

