<template>
    <div class="furniture">
        <!-- <h3>{{furniture.name}}</h3> -->
                <Card>
            <template #header>
                <img src="https://images.unsplash.com/photo-1540574163026-643ea20ade25?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80" />
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