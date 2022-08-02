<script setup lang="ts">
const props = defineProps({
	show: Boolean,
	imageToDisplay: String
})
</script>

<template>
	<Transition name="modal">
		<div v-if="show" class="modal-mask">
			<div class="modal-wrapper">
				<div class="modal-container">
					<!-- <div class="modal-header">
						<slot name="header">default header</slot>
					</div> -->

					<div class="modal-body">
						<slot name="body"><img :src="imageToDisplay" alt="" /></slot>
					</div>

					<div class="modal-footer">
						<slot name="footer">
							<button class="modal-default-button" @click="$emit('close')">Close</button>
						</slot>
					</div>
				</div>
			</div>
		</div>
	</Transition>
</template>

<style lang="scss">
.modal-mask {
	position: fixed;
	z-index: 9998;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	background-color: rgba(0, 0, 0, 0.5);
	transition: opacity 0.3s ease;
}

.modal-wrapper {
	height: 100%;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
}

.modal-container {
	width: 1500px;
	max-width: 90%;
	height: 80vh;
	margin: 0px auto;
	padding: 40px;
	background-color: #fff;
	border-radius: 2px;
	box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
	transition: all 0.3s ease;
}

.modal-header h3 {
	margin-top: 0;
	color: #42b983;
}

.modal-body {
	margin: 0;
	width: 100%;
	height: 100%;
	& img {
		width: inherit;
		height: inherit;
		object-fit: cover;
	}
}

.modal-footer {
	padding: 16px;
	background-color: #fff;
}

.modal-default-button {
	float: right;
}

/*
 * The following styles are auto-applied to elements with
 * transition="modal" when their visibility is toggled
 * by Vue.js.
 *
 * You can easily play with the modal transition by editing
 * these styles.
 */

.modal-enter-from {
	opacity: 0;
}

.modal-leave-to {
	opacity: 0;
}

.modal-enter-from .modal-container,
.modal-leave-to .modal-container {
	-webkit-transform: scale(1.1);
	transform: scale(1.1);
}
</style>
