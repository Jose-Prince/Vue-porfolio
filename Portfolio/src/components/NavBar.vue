<script>
import NavButton from "./NavButton.vue"
export default {
	components: {
		NavButton,
	}
}
</script>

<template>
	<div class="nav-style">
		<h2 class="margin-name">
			José Alejandro Prince Martinez
		</h2>	
		<div class="buttons-display">
			<NavButton titlePage="About me" page="about"/>
			<NavButton titlePage="My projects" page="projects"/>
			<NavButton titlePage="Technologies" page="techs"/>
			<NavButton titlePage="Contact me" page="contact"/>
		</div>
	</div>
</template>

<style>
	.nav-style {
		color: #000;
		display: flex;
		justify-content: space-between;
		background-color: #FFF;
    	filter: drop-shadow(0 0 1mm rgb(0, 0, 0));
		padding-right: 25px;
	}

	.margin-name {
		padding-left: 30px
	}

	.buttons-display {
		display: flex;
	}
</style>
