<template>
    <div class="App">
        <div>My app</div>
        <BuyList
            listName="Aramys"
            :products="localProducts"
            @add-item="AddItemApp"
        />
        <BuyList
            listName="Giordano"
            :products="localProducts2"
        />
    </div>
</template>

<script>
    import BuyList from './BuyList.vue';

    export default {
        components: {
            BuyList,
        },

        props: {},
        
        data() {
            return {
                localProducts: [
                    { id: 1, name: 'Tomate cereja' },
                    { id: 2, name: 'Cebola' },
                ],
                localProducts2: [
                    { id: 3, name: 'Alho poró' },
                    { id: 4, name: 'Sardinha' },
                ],
            };
        },

        methods: {
            AddItemApp(item) {
                this.localProducts.push({ id: +new Date(), name: item });
            },
        },
    };
</script>
