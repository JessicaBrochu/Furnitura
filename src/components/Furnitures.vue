<template>
    <div class="furnitures">
        <div v-for="furniture in furnitures" :key="furniture.id">
            <!-- <h3>{{furniture.name}}</h3> -->
            <Furniture @remove-furniture="$emit('remove-furniture', furniture.id)" :furniture="furniture"/>
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
        emits: ["remove-furniture"]
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