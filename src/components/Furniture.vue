<template>
    <div class="furniture">
        <!-- <h3>{{furniture.name}}</h3> -->
                <Card>
            <template #header>
                <img :src="furniture.url" alt="Furniture" />
            </template>
            <template #title>
                {{furniture.name}}
            </template>
            <template #subtitle>
                {{furniture.price}}
            </template>
            <template #footer>
                <Button 
                    @click="onRemove(furniture.id)"
                    icon="pi pi-times" 
                    label="Remove" 
                    class="p-button-danger" 
                />
                <Button 
                    @click="$emit('add-favorite', furniture.id)"
                    icon="pi pi-heart" 
                    :class="[
                    furniture.isFavorite ? '' : 'p-button-outlined',
                    'p-button-rounded',
                    'p-button-danger'
                    ]"
                />
            </template>
        </Card>
    </div>
</template>

<script>
    export default {
        props: {
            furniture: Object
        },
        components: {},
        methods: {
            onRemove(id) {
                this.$emit("remove-furniture", id);
            },
        },
    }
</script>

<style>
.p-component img{
    height: 300px;
    object-fit: cover;
}
.p-card-title{
    font-family: 'Inter', sans-serif;
    font-size: 16px !important;
    font-weight: 400 !important;
    color: #6A6A6C;
    text-align: center;
    margin: 5px 0;
}
.p-card-subtitle{
    font-size: 22px;
    color: #2A2B30 !important;
    font-weight: 500 !important;
    text-align: center;
    margin: 5px 0;
}
.p-card-content{
    padding: 0 !important;
}
.p-card-footer{
    padding-top: 24px !important;
    display: flex;
    justify-content: space-between;
}
</style>