<template>
    <div v-if="isVisible" class="item">
        <h3>{{ item.name }}</h3>
        <p>₱{{ item.price }}</p>
        <button @click="addToCart">Add to Cart</button>
    </div>
</template>
  
<script>
export default {
    name: 'Item',
    props: {
        item: {
            type: Object,
            required: true
        },
        isVisible: {
            type: Boolean,
            default: true
        }
    },
    methods: {
        addToCart() {
            this.$emit('add-to-cart', this.item);
            console.log(`Added to cart: ${this.item.name} - ₱${this.item.price}`);
        }
    }
}
</script>
  
<style scoped>
.item {
    border: 1px solid #ddd;
    padding: 10px;
    margin: 10px 0;
    background-color: #fff;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

button {
    padding: 10px 15px;
    border: none;
    background-color: #007bff;
    color: white;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}
</style>
