<script>
import ProductDetails from './ProductDetails.vue';

export default {
    props: {
        products: Object
    },
    data() {
        return {
            showDetailsModal: false,
            selectedProduct: []
        };
    },
    components: { ProductDetails },
    methods: {
        displaySelectedProduct(product) {
            this.selectedProduct = product;
            if(this.showDetailsModal){
                this.showDetailsModal = false;
            } else {
                this.showDetailsModal = true;
            }
        },
        closeModal() {
            this.showDetailsModal = false;
        }
    },
 
}
</script>
<template>
    <div>
        <li id="productList" v-for="product in products">
            <div id="inventory">
                <img id="inventoryImg" :src="product.ThumbnailURL" />
                <div id="productDetails">
                    <h2>{{product.Name}}</h2>
                    <div id="prices">
                        <h3>{{product.Price}}</h3>
                        <p v-if="product.Price !== product['Retail Price']">
                            {{product['Retail Price']}}
                        </p>
                    </div>
                </div>
                <div id="details">
                    <button id="getDetails" type="button" @click="displaySelectedProduct(product)"  style="margin-left: 75%;">View Details</button>
                </div>
            </div>
        </li>
        <div v-if="showDetailsModal">
          <ProductDetails :product="selectedProduct" @closeModal="closeModal()"/>
        </div>
    </div>
</template>