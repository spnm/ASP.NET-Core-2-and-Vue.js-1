
<template>
    <div class="products">
        <h1>Products</h1>
        <div class="list">
            <div class="item" v-for="product in products" :key="product.slug">
                <h3 @click="select(product)">{{ product.name }}</h3>
                <img :src="product.thumbnail" :alt="product.name" @click="select(product)" />
                <p @click="select(product)">{{ product.shortDescription }}</p>
                <p @click="select(product)">{{ product.price }}</p>
                <hr />
            </div>
        </div>
        <product-details class="details"  v-if="selectedProduct" :product="selectedProduct"/>
    </div>
</template>

<script>
import ProductDetails from './Details.vue'
export default {
    name: "product-list",
    components: {
        ProductDetails
    },
    data() {
        return {
            products: [
            //products omitted for brevity
            {
                name: "Samsung s8",
                slug: "S8",
                thumbnail: "http://placehold.it/200x300",
                shortDescriptio:"bestiesojfeasio jaidja wi",
                price: 12.23,
                description: "Lorem pawdiaueosj dj awdlijaw dijw"},
            {
                name: "Samsung s9", 
                slug: "S9",
                thumbnail: "http://placehold.it/200x300",
                shortDescriptio:"asdadasbestiesodwjfeasio jaidja wi",
                price: 12.23,
                description: "sadasdLdasdadasdasadorem pawdiaueosj dj awdlijaw dijw"
            }
            ],
            selectedProduct: null
        };
    },
    methods: {
        select(product) {
            this.selectedProduct = product;
        }
    }
};
</script>

<style>
* {
    box-sizing: border-box !important;
}
.products {
    padding: 20px;
    max-width: 1200px;
    margin: 0 auto;
}
.list,.details {
    width: 50%;
    float:left;
}
.list .item {
    width: 50%;
    float:left;
    padding: 20px 10px 20px 0;
}
.list img,
.list h3,
.list p {
    cursor:pointer;
}
.list img {
    width: 100px;
}
</style>
