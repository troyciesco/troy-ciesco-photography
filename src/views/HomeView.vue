<script setup lang="ts">
import Images from "../components/Images.vue"
// import TheWelcome from '@/components/TheWelcome.vue'
</script>

<template>
	<main>
		<!-- <TheWelcome /> -->
		<h1>Troy Ciesco<br />Wildlife Photography</h1>
		<Images />
	</main>
</template>

<style lang="scss">
main {
	max-width: 1600px;
	margin: 0 auto;

	& h1 {
		text-align: center;
	}
}
</style>
