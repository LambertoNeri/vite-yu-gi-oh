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

</style>