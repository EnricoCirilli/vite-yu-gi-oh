<script>

import axios from 'axios';

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
};
</script>

<template>
 <h1>HELLO</h1>
 <ul>
  <li v-for="character in characters">{{  character.name }}</li>
 </ul>
</template>

<style lang="scss">
 @use "./style/general.scss";

</style>
