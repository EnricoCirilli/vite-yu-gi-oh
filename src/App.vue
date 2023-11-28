<script>

import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import CharattersList from './components/CharattersList.vue';
import { store } from './store.js';

export default{
  data(){
    return{
      store : store,
    };
  },
  created(){
    //chiamata api delle cards
    axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0").then((resp) => {
   console.log(resp);
   this.store.characters = resp.data.data;
   
    });

  },
  components:{
    AppHeader,
    CharattersList,
},
};

</script>

<template>

<AppHeader />
<section>

 <select class="form-select form-select-lg mb-3" aria-label=".form-select-lg example">
  <option selected>Archetype</option>
  <option value="1">Alien</option>
  <option value="2">Ally</option>
  <option value="3">Ancient Gear</option>
</select>

</section>

<CharattersList />

</template>

<style lang="scss">
 @use "./style/general.scss";

</style>
