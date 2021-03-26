<template>
  <div id="addForm">
    <form @submit.prevent="handleAdd">
      <div class="form-group">
        <label for="id">Id</label>
        <input v-model="product.id" type="text" class="form-control" id="id" />
      </div>
      <div class="form-group">
        <label for="categoryId">Category</label>
        <input
          v-model="product.categoryId"
          type="text"
          class="form-control"
          id="categoryId"
          required
        />
      </div>
      <div class="form-group">
        <label for="productName">Product Name</label>
        <input
          v-model="product.productName"
          type="text"
          class="form-control"
          id="productName"
          required
        />
      </div>
      <div class="form-group">
        <label for="quantityPerUnit">Description</label>
        <input
          v-model="product.quantityPerUnit"
          type="text"
          class="form-control"
          id="quantityPerUnit"
          required
        />
      </div>
      <div class="form-group">
        <label for="unitPrice">Unit Price</label>
        <input
          v-model="product.unitPrice"
          type="text"
          class="form-control"
          id="unitPrice"
          required
        />
      </div>

      <div class="form-group">
        <label for="unitsInStock">Stock</label>
        <input
          v-model="product.unitsInStock"
          type="text"
          class="form-control"
          id="unitsInStock"
          required
        />
      </div>
      <button type="submit" class="btn btn-sm btn-success">Submit</button>
    </form>
  </div>
</template>
<script>
export default {
  name: "product-add",
  data() {
    return {
      product: {
        id: "",
        categoryId: "",
        productName: "",
        quantityPerUnit: "",
        unitPrice: "",
        unitsInStock: "",
      },
    };
  },
  methods: {
    handleAdd() {
      this.$emit("add:product", this.product);
    },
  },
};
</script>
<style scoped>
#addForm {
  margin: 100px;
}
</style>