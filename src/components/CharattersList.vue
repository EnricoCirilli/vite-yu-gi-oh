<script> import { store } from '../store.js';
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
            <div class="row" row-cols-5 g-4>
                <div class="col-3" v-for="character in store.characters">
                   <AppCard :character="character" :key="character"/>
                </div>
            </div>
        </div>
    </div>

    

</template>

<style lang="scss" scoped>


</style>