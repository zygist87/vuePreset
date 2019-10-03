<template>
  <main>
    <AppHeader />
    <div>
      <slot />
    </div>
    <AppFooter />
  </main>
</template>

<script>
import AppFooter from './AppFooter'
import AppHeader from './AppHeader'

export default {
	name: 'Layout',
	components: {
		AppHeader,
		AppFooter
	}
}
</script>

<style>
</style>
