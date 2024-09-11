<template>
    <div class="item-list">
        <h1>Item List</h1>
        <ul>
            <li v-for="item in filteredItems" :key="item.id">
                <Item :item="item" @add-to-cart="handleAddToCart" />
            </li>
        </ul>
    </div>
</template>

<script>
import Item from './Item.vue';

export default {
    name: 'ItemList',
    components: {
        Item,
    },
    props: {
        items: {
            type: Array,
            required: true,
        },
    },
    computed: {
        filteredItems() {
            return this.items.filter(item => item.isVisible);
        },
    },
    methods: {
        handleAddToCart(item) {
            console.log(`Added to cart: ${item.name} - ₱${item.price}`);
        },
    },
};
</script>

<style scoped>
.item-list ul {
    list-style-type: none;
    padding: 0;
    margin: 0;
}

.item-list li {
    margin-bottom: 10px;
}
</style>
