<template>
  <div class="product-view">
    <div
      v-if="isRequesting"
      class="loading"
    >
      Loading..............
    </div>
    <div v-else>
      <ProductBox
        v-for="product in products"
        :key="product.id"
        :product="product"
        @click="starProduct"
      />
    </div>
  </div>
</template>

<script>
import ProductBox from '@/components/ProductBox'
import { FETCH_PRODUCTS } from '@/store/modules/Products/action-types'
import { REQUESTING } from '@/store/modules/Products/status-types'
import { createNamespacedHelpers } from 'vuex'
const { mapActions, mapGetters } = createNamespacedHelpers('Products')
export default {
	name: 'ProductView',
	components: {
		ProductBox
	},
	computed: {
		...mapGetters({
			products: 'products',
			status: 'status'
		}),
		isRequesting () {
			return this.status === REQUESTING
		}
	},
	created () {
		this.fetchProducts()
	},
	methods: {
		...mapActions({
			fetchProducts: FETCH_PRODUCTS
		}),
		// ...mapMutations({
		// 	setStarOnProduct: STAR_PRODUCT
		// }),
		starProduct (product) {
			this.setStarOnProduct(product.id)
		}
	}
}
</script>

<style lang="scss">
	.loading {
		color: darkgreen;
	}
</style>
