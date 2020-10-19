<template>
    <div class="BuyList">
        <span>Buy List {{listName}}</span>
        <div>
            <ul>
                <li
                    v-for="item in filteredList"
                    :key="item.id"
                    >{{item.name}}
                </li>
            </ul>
            <input v-model="itemName" />
            <button @click="addItem">Add item</button>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            listName: {
                type: String,
                default: '',
            },
            products: {
                type: Array,
                default: () => [],
            },
        },

        data() {
            return {
                itemName: '',
            };
        },

        mounted() {},

        methods: {
            filterFeijao() {},

            addItem() {
                this.$emit('add-item', this.itemName);
                this.itemName = '';
            },
        },

        computed: {
            filteredList() {
                return this.products;
            },
        },

        watch: {},
    }
</script>

<style>
    .BuyList {
        padding: 20px;
        border: 1px solid #ddd;
        margin-bottom: 20px;
    }

    .BuyList ul li {
        border-bottom: 1px solid #ddd;
        margin-bottom: 20px;
    }
</style>