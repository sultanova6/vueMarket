<template>
    <div class="v-catalog-item">
        <img class="v-catalog-item__image" :src=" require('../assets/images/' + product_data.image)" alt="img">
        <p class="v-catalog-item__name +">{{product_data.name}}</p>
        <p class="v-catalog-price">Prcie: {{product_data.price}}</p>
        <button 
          class="v-catalog-add_to_cart_btn btn" 
          @click="sendDataToParent"
        >Add to cart
        </button>
    </div>
</template>

<script>

 export default {
    name: 'v-catalog-item',
    props: {
        product_data: {
            type: Object,
            default() {
                return {}
            }
        }
    },
    data() {
        return{}
    },
    computed: {},
    methods: {
      sendDataToParent() {
        this.$emit('sendArticle', this.product_data.article)
      }
    }
 }
</script>

<style lang="scss">
  .v-catalog-item {
    flex-basis: 25%;
    box-shadow: 0 0 8px 0 #e0e0e0;
    padding: $padding*2;
    margin-bottom: $margin*2;

    &__image {
      width: 100px;
    }
  }
</style>