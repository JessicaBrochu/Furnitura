<template>
    <div class="furniture">
        <!-- <h3>{{furniture.name}}</h3> -->
                <Card style="width: 25em">
            <template #header>
                <img src="https://www.primefaces.org/wp-content/uploads/2020/02/primefacesorg-primevue-2020.png" style="height: 15rem" />
            </template>
            <template #title>
                {{furniture.name}}
            </template>
            <template #subtitle>
                {{furniture.price}}
            </template>
            <template #footer>
                <Button icon="pi pi-times" label="Remove" class="p-button-danger" style="margin-right: 11.1em" />
                <Button icon="pi pi-heart" class="p-button-rounded p-button-danger" />
                <Button icon="pi pi-heart" class="p-button-rounded p-button-danger p-button-outlined" />
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
}
</style>