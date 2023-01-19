<script>
    import Card from './Card.vue';
    import { store } from '../store';

    export default {
        name: 'CardList',
        data(){
            return{
                store,
            }
        },
        components: {
            Card,
        }
    }
    
</script>

<template lang="">

    <div class="background-orange p-5">
        <div class="card-list-container container-fluid d-flex justify-content-between flex-wrap p-4 bg-white">
            <Card v-for="(card, index) in store.cards.data"  :card="card" :key="index"/>
        </div>
    </div>

</template>

<style lang="scss">
    @use '../styles/general.scss';
    @use '../styles/partials/variables.scss' as *;

    .background-orange{
        background-color: $orange;

        .card-list-container{
        gap: 10px;
        }
    }
    
</style>