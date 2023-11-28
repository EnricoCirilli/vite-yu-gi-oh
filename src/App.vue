<script>
//importare componenti
import axios from "axios";
import AppHeader from './components/AppHeader.vue';
import { store } from "./store.js";
import CharattersList from "./components/CharattersList.vue";
import AppSelect from "./components/AppSelect.vue";



//dichiarare componenti
export default {
  data() {
    return {
      store: store
    };
  },
  created() {
   
    axios
      .get(this.store.apiUrl, {
        params: {
          num: 20,
          offset: 0
        },
      })
      .then((resp) => {
        //console.log(resp);
        this.store.cardsList = resp.data.data;
        console.log(this.store.cardsList);
      })
  },
  components: {
    AppHeader,
    AppSelect,
    CharattersList,
  
},
  methods: {
    handleSelect() {
      axios.get(this.store.apiUrl, {
        params: {
          archetype: this.store.selectedOption,
          num: 20,
          offset: 0
        }
      }).then((resp) => {
        this.store.cardsList = resp.data;
      })
    }
  },
};
</script>

<template>
  <!-- utilizzare componenti-->
  <AppHeader />
  <AppSelect @showCards="handleSelect" />
  <CharattersList />
</template>

<style lang="scss">
@use "./style/general.scss";
</style>