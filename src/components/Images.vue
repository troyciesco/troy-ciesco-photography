<script setup lang="ts">
import Modal from "./Modal.vue"
import { ref } from "vue"

const showModal: any = ref(false)
const selectedImage = ref("")

const handleShowModal = (imageToDisplay?: string) => {
	if (showModal.value === true) {
		showModal.value = false
		selectedImage.value = ""
	} else {
		showModal.value = true
		selectedImage.value = imageToDisplay as string
	}
}

const images = [
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1659474093/troy-ciesco-photography/peeper.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1659474093/troy-ciesco-photography/mourning-dove.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1659474075/troy-ciesco-photography/butterfree.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1659474093/troy-ciesco-photography/red-necked-grebe.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1659474093/troy-ciesco-photography/great-blue-heron.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1659474070/troy-ciesco-photography/20220730-DSC_0399.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1659474060/troy-ciesco-photography/20220724-DSC_0203-2.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1658173447/troy-ciesco-photography/20220710-DSC_0001.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1658173453/troy-ciesco-photography/20220709-DSC_0022-2.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1659474030/troy-ciesco-photography/20220724-DSC_0108.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1658173452/troy-ciesco-photography/20220718-DSC_0176.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1658173450/troy-ciesco-photography/20220711-DSC_0102.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1658528936/troy-ciesco-photography/20220719-DSC_0031.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1659474056/troy-ciesco-photography/20220724-DSC_0192.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1659474092/troy-ciesco-photography/mono-goose.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1658173448/troy-ciesco-photography/DSC_0010-4.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1658173451/troy-ciesco-photography/20220711-DSC_0047.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1658528936/troy-ciesco-photography/20220719-DSC_0046.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1658173452/troy-ciesco-photography/20220717-DSC_0084.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1658173454/troy-ciesco-photography/20220717-DSC_0093.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1658173456/troy-ciesco-photography/20220717-DSC_0164.jpg",
	"https://res.cloudinary.com/tmciesco/image/upload/q_auto:good/v1658173455/troy-ciesco-photography/20220717-DSC_0123.jpg"
]
</script>

<template>
	<div class="masonry-container">
		<div class="masonry-columns">
			<template v-for="image in images">
				<img @click="handleShowModal(image)" class="masonry-brick" :src="image" alt="" />
			</template>
		</div>
	</div>
	<Teleport to="body">
		<modal :show="showModal" :imageToDisplay="selectedImage" @close="handleShowModal"> </modal>
	</Teleport>
</template>

<style>
/* Container */
.masonry-container {
	--column-count-small: 1;
	--column-count-medium: 2;
	--column-count-large: 3;
	--column-gap: 1rem;
	padding: var(--column-gap);
}

/* Columns */
.masonry-columns {
	column-gap: var(--column-gap);
	column-count: var(--column-count-small);
	column-width: calc(1 / var(--column-count-small) * 100%);
}

@media only screen and (min-width: 640px) {
	.masonry-columns {
		column-count: var(--column-count-medium);
		column-width: calc(1 / var(--column-count-medium) * 100%);
	}
}

@media only screen and (min-width: 800px) {
	.masonry-columns {
		column-count: var(--column-count-large);
		column-width: calc(1 / var(--column-count-large) * 100%);
	}
}

/* Bricks */
.masonry-brick {
	width: 100%;
	height: auto;
	margin: var(--column-gap) 0;
	display: block;
}

.masonry-brick:first-child {
	margin: 0 0 var(--column-gap);
}
</style>
