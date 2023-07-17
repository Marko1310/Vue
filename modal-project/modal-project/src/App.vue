<template>
	<div>
		<h1>{{ title }}</h1>
		<div v-if="showModal">
			<Modal :header="header" :text="text" theme="sale" @close="toggleModal" />
		</div>
	</div>
	<button @click.alt="toggleModal">Show Modal (alt)</button>
</template>

<script>
import Modal from './components/Modal.vue';

export default {
	name: 'App',
	components: {Modal},
	data() {
		return {
			title: 'My firsy Vue app :)',
			header: 'Sign up for the Giveaway',
			text: 'Grab the prize',
			showModal: false,
		};
	},
	methods: {
		handleClick() {
			console.log(this.$refs.name);
			this.$refs.name.classList.add('active');
			this.$refs.name.focus();
		},
		toggleModal() {
			this.showModal = !this.showModal;
		},
	},
};
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
h1 {
	border-bottom: 1px solid #ddd;
	display: inline-block;
	padding-bottom: 10px;
}
</style>
