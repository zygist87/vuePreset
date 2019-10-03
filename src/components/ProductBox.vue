<template>
  <div>
    <HeartIcon />
    <img
      :src="product.image"
      alt="product"
    >
    <h1>{{ product.name }}</h1>
    <p>{{ product.description }}</p>
    <p>{{ product.price }}</p>
  </div>
</template>

<script>
import HeartIcon from './HeartIcon'
export default {

	name: 'ProductBox',
	components: {
		HeartIcon
	},
	props: {
		product: {
			type: Object,
			default: () => ({
				id: null,
				image: null,
				dascription: null,
				name: null,
				body: null,
				title: null,
				userId: null,
				price: null,
				stared: false
			})
		}
	}
}
</script>

<style>
</style>
