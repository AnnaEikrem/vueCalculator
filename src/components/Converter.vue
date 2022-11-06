<template>
	<section class="converter">
		<h1 class="converter__headline">Length converter</h1>

		<div>
			<h3>Meters --> Imperial measures</h3>
		</div>

		<div class="converter__input">
			<input class="converter__input-meters" type="number" placeholder="m" v-model="valueInput">
		</div>

		<div class="converter__output">
			<h3 class="converter__output-name">Inches</h3>
			<h3 class="converter__output-name">Miles</h3>
			<h3 class="converter__output-name">Inches</h3>

			
		</div>

	</section>
</template>

<script>

</script>


<style>
@import url('https://fonts.googleapis.com/css2?family=Bungee+Shade&family=Inter&display=swap');

	.converter {
		height: 100%;
		width: 50%;
		background: #d2a24c;
		
		padding: 0.75rem;
		font-size: 0.8rem;
	}

	.converter__headline {
		text-align: center;
		font-family: 'Bungee Shade', cursive;
		color: #3e3126;
		font-size: 1.1rem;
		margin-top: 1rem;
	}

	/* .converter__name {
		color: red;
		width: 100%;
		display: flex;
		justify-content: left;
	} */
/* 
	.converter__output {
		width: 80%;
		height: 2rem;
		padding: 1rem;
		margin: 2rem 2rem 1rem 1.5rem;
		border: 0.2rem solid #6f5643;
		background: #fff;
		border-radius: 0.5rem;
	}*/
</style> 