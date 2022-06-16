<template>
    <div class="furnitures">
        <div v-for="furniture in furnitures" :key="furniture.id">
            <!-- <h3>{{furniture.name}}</h3> -->
            <Furniture :furniture="furniture"/>
        </div>
    </div>
</template>

<script>
import Furniture from "./Furniture"

    export default {
        props: {
            furnitures: Array,
        },
        components: { Furniture },
    };
</script>

<style>
.furnitures{
    padding-top: 100px;
    display: grid;
    gap: 15px;
    grid-template-columns: repeat(3, 1fr);
}
</style>