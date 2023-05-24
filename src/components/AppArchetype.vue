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
<div class="container">
    <select name="archtype" id="">
        <option v-for="(archtype, index) in store.archetypeList" :key="index"
         value="Alien"> {{ store.archetypeList[index].archetype_name }}
        </option>
     
    </select>
</div>
</template>

>

<style lang="scss" scoped>
    select{
                padding-left: 1rem;
                padding-right: 0rem;
                padding-top: 0.5rem;
                padding-bottom: 0.5rem;
                font-size: 1.5rem;
                border: none;
                margin-top: 1rem;
                margin-left: 5rem;
                border-radius: 5px;
            }
</style>