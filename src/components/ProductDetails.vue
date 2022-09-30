<script>
export default {
  props: { product: Object },
  methods: {
    closeModal(){
      this.$emit('closeModal')
    }
  }
}
</script>
<template>
  <div id="productModal">
    <div id="close">
      <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
        stroke="currentColor" id="closeButton" @click="closeModal()">
        <path stroke-linecap="round" stroke-linejoin="round"
          d="M9.75 9.75l4.5 4.5m0-4.5l-4.5 4.5M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
      </svg>
    </div>
    <div id="productBody">
      <div id="details">
        <img :src="product.PictureURL" />
        <div id="productInformation">
          <div id="topRow">
            <div id="category">
              <p> {{product.Category}} </p>
            </div>
            <div id="rating">
              Rating {{product.RatingAvg}} / Number of ratings {{product.RatingCount}}
            </div>
          </div>
          <div id="brandInformation">
            <h1> {{product.Name}} {{product.Brand}} {{product.Color}}</h1>
            <div id="priceInformation">
              Price
              <h3> {{product.Price}}</h3>
              Retail
              <p> {{product['Retail Price']}}</p>
            </div>
          </div>
          <div id="brandDescription">
            {{product.Description}}
          </div>
          <div id="addtionalInformation">
            In Stock {{product.Stock}}
            <span v-if="product.Badges">Badges {{product.Badges}}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
