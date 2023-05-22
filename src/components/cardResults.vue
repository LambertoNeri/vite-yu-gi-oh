<script>
    import { store } from '../store';

    export default {
  
        data() {
            return {
                store,
            };
        },   
    };
</script>

<template>
    <div v-for="(card, index) in store.cardList" :key="index" class="single-card">
        <img :src="store.cardList[index].card_images[0].image_url" alt="">
        <div class="card-text">
            <span class="name">{{ store.cardList[index].name.toUpperCase() }}</span>
            <span class="archetype"> {{ store.cardList[index].archetype }}  </span>
        </div> 
    </div>
</template>



<style lang="scss" scoped>
    .single-card{
        width: 250px;
        max-height: 600px;
        img{
            width: 100%;
        }
        .card-text{
            height: 240px;
            display: flex;
            justify-content: space-between;
            flex-direction: column;
            background-color: #D48F38;
            align-items: center;
            padding-top: 1.5rem;
            padding-bottom: 1.5rem;

            .name{
                color: white;
                font-size: 1.3rem;
                max-width: 80%;
                text-align: center;
            }

            .archetype{
                font-size: 1.3rem;
                max-width: 80%;
                text-align: center;
            }
        }
    }
</style>