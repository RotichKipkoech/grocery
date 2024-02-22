<template>
  <div id="app">
    <h1>Grocery System</h1>
    <div>
      <input v-model="newItem" placeholder="Enter a new item" />
      <button @click="addItem">Add Item</button>
    </div>
    <ul>
      <li v-for="(item, index) in groceryList" :key="index">
        {{ item }}
        <button @click="removeItem(index)">Remove</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newItem: "",
      groceryList: [],
    };
  },
  methods: {
    addItem() {
      if (this.newItem.trim() !== "") {
        this.groceryList.push(this.newItem.trim());
        this.newItem = "";
      }
    },
    removeItem(index) {
      this.groceryList.splice(index, 1);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

input {
  padding: 5px;
  margin-right: 10px;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 5px 0;
}
</style>
