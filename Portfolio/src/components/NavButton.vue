<script>
export default {
	props: {
		titlePage: String,
		page: String,
	},
	methods: {
		navigate() {
			this.$router.push({ path: `/${this.page}`})
		}
	}
}
</script>

<template>
	<div class="parallelogram" @click="navigate">
		{{ titlePage }}
	</div>
</template>

<style>
	.parallelogram {
		width: 100px;
		height: 100%;
		transform: skew(20deg);
		background: #555;
		cursor: pointer;
	}
</style>
