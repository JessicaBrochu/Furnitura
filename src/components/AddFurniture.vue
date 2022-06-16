<template>
  <div class="form">
    <form @submit="onSubmit" class="p-formgroup-inline">
      <div class="form_flex">
        <div class="p-field">
            <label for="name" class="p-sr-only">Name</label>
            <InputText v-model="name" id="name" type="text" placeholder="Name" />
        </div>
        <div class="p-field">
            <label for="price" class="p-sr-only">Price</label>
            <InputText v-model="price" id="price" type="text" placeholder="Price" />
        </div>
        <div class="p-field">
            <label for="url" class="p-sr-only">URL</label>
            <InputText v-model="url" id="url" type="text" placeholder="Image URL" />
        </div>
      </div>
      <Button type="submit" label="Add furniture" />
    </form>
  </div>
</template>

<script>
export default {
  name: "AddFurniture",
  data() {
    return {
      name: "",
      price: "",
      url: "",
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();
      const newFurniture = {
        name: this.name,
        price: this.price,
        url: this.url,
        isFavorite: false,
      };
      this.$emit("add-furniture", newFurniture);
      this.name = "";
      this.price = "";
      this.url = "";
    },
  },
};
</script>

<style>
.p-formgroup-inline{
    padding-top: 50px;
    display: flex;
    justify-content: space-between;
}
.form_flex{
    display: flex;
}
.p-field{
    padding-right: 12px;
}
</style>