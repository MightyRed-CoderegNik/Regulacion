<template>
  <div id="app">
    <ItemList :items="items" />
  </div>
</template>

<script>
import ItemList from './components/ItemList.vue';

export default {
  name: 'App',
  components: {
    ItemList
  },
  data() {
    return {
      items: [
        { id: 1, name: 'Item 1', price: 10, isVisible: true },
        { id: 2, name: 'Item 2', price: 20, isVisible: true },
        { id: 3, name: 'Item 3', price: 30, isVisible: true }
      ]
    };
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: #f0f0f0;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.item-list {
  background-color: #ffffff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.item-list h1 {
  margin-bottom: 20px;
}
</style>
