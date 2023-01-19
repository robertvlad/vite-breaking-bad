<script>
  import AppHeader from './components/AppHeader.vue';
  import CardList from './components/CardList.vue';
  import axios from 'axios';
  import { store } from './store';
  export default {
    components: {
      AppHeader,
      CardList,
    },
    data(){
        return{
            store,
            cardsList: [],
        }
    },
    created(){
        this.createCard();
    },
    methods: {
        createCard(){
            axios.get(store.api).then((reponse) => {
                    store.cards = reponse.data ;
            })
        }
    }
  }
</script>

<template lang="">

    <AppHeader />
    <CardList />

</template>

<style lang="scss">
  @use './styles/partials/variables.scss' as *;

</style>