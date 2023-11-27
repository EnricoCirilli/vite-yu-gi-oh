<script>

import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import CharattersList from './components/CharattersList.vue';


export default{
  data(){
    return{
      characters: [],
    };
  },
  created(){
    //chiamata api delle cards
    axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0").then((resp) => {
   console.log(resp);
   this.characters = resp.data.data;
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

</template>

<style lang="scss">
 @use "./style/general.scss";

</style>
