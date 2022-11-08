<template>
	<div class="container">
		<Calculator/>
		<Converter/>
		<hr class="line red">
		<hr class="line yellow">
		<hr class="line blue">
	</div>
</template>

<script>
	import Calculator from '../components/Calculator.vue'
	import Converter from '../components/Converter.vue'

	export default {
		components: {
			Calculator,
			Converter
		}
	}
</script>


<style>
	* {
		box-sizing: border-box;
		padding: 0;
		margin: 0;
		font-size: 20px;
	}

	/* body {
		width: 100%;
		display: flex;
		justify-content: center;
	} */

	.container {
		position: relative;
		width: 80%;
		height: 80vh;
		display: flex;
		flex-direction: row;
		justify-content: center;
		margin: 3rem;
		border-radius: 0.3rem;
		border: 0.5rem solid #6f5643;
	}

	.red {
		background: rgb(242, 90, 90);
		position: absolute;
		width: 40%;
		height: 0.6rem;
		bottom: 2.2rem;
		left: 0;
		border: none;
		border-radius: 0 10px 10px 0;
		z-index: 10;
	}

	.yellow {
		background: rgb(219, 201, 48);
		position: absolute;
		width: 40%;
		height: 0.6rem;
		bottom: 1.3rem;
		left: 0;
		border: none;
		border-radius: 0 10px 10px 0;
		z-index: 10;
	}

	.blue {
		background: rgb(92, 92, 180);
		position: absolute;
		width: 40%;
		height: 0.6rem;
		bottom: 0.5rem;
		left: 0;
		border: none;
		border-radius: 0 10px 10px 0;
		z-index: 10;
	}
	
</style>