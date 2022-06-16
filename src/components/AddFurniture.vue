<template>
  <div class="form">
    <form @submit="onSubmit" class="p-formgroup-inline">
      <div class="form_flex">
        <div class="p-field">
            <label for="name" class="p-sr-only">Name</label>
            <InputText v-model="name" id="name" type="text" placeholder="Name" />
            <!-- {{ this.name }} -->
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
  name: "AddPet",
  data() {
    return {
      name: "",
      age: "",
      url: "",
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();
      const newPet = {
        // id: Math.random(),
        name: this.name,
        age: this.age,
        url: this.url,
        isFavorite: false,
      };
      //   console.log("new pet", newPet);
      this.$emit("add-pet", newPet);
      this.name = "";
      this.age = "";
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