<template>
  <div>
    <button @click="$emit('click', product)">
      {{ product.stared ? 'unfavourite' : 'favourite' }}
    </button>

    <span v-if="product.stared"> STARED! </span><br>
  </div>
</template>

<script>
export default {
	name: 'HeartIcon'

}
</script>

<style>
</style>
