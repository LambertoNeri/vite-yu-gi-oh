<script>
    import { store } from '../store'
    import cardResults from './cardResults.vue'
    export default {
        components: {
            cardResults,
        },
        data() {
            return {
                store,
            };
        },   
    }
</script>

<template>
<main>
    <div class="bg">
        <div class="container">
            <select name="archtype" id="">
                <option value="Alien">Alien</option>
                <option value="Alien">Dragon</option>
                <option value="Alien">Pincolo</option>
            </select>
            <div class="white-bg">
                <div class="black-bg">
                    <span class="found">Found {{ store.cardList.length }} cards</span>
                </div>
                <div class="card-section">
                    <div class="card-container">
                        <cardResults/>
                    </div>
                </div>
                    
            </div>

        </div>
      
    </div>
</main>
</template>



<style lang="scss" scoped>
    .bg{
        background-color: #D48F38;
        
        .container{
            height: 100%;
            max-width: 1500px;
            margin-inline: auto;
            select{
                padding-left: 1rem;
                padding-right: 6rem;
                padding-top: 0.5rem;
                padding-bottom: 0.5rem;
                font-size: 1.5rem;
                border: none;
                margin-top: 1rem;
                margin-left: 5rem;
                border-radius: 5px;
           }
           .black-bg{
                background-color: #212529;
                max-width: 90%;
                margin-inline: auto;
                height: 10vh;
                display: flex;
                align-items: center;
                color: white;
                padding-left: 2rem;
                font-size: 2rem;
            }
           .white-bg{
                max-width: 90%;
                margin-inline: auto;
                height: 100%;
                background-color: white;
                margin-top: 3rem;
                padding-top: 4.5rem;
                .card-section{
                    display: flex;
                    flex-direction: column;
                    gap: 0rem;
                    max-width: 90%;
                    margin-inline: auto;  
                    .found{
                        color: white;
                        font-size: 2rem;
                        margin-left: 2rem;
                    }
                    .card-container{
                        display: flex;
                        flex-wrap: wrap;
                        gap: 1.5rem;
                    }
                }
                        
           }
        }
       
       
    }

</style>