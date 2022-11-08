<template>
	<section class="converter">
		<h1 class="converter__headline">Length <br>converter</h1>

		<div class="">
			<h3 class="converter__output-name" >Meters -></h3>
		</div>

		<div class="converter__input ">
			<input class="converter__input-meters valueField" type="number" placeholder="Type" v-model="valueInput">
		</div>

		<div class="converter__output ">
			<h3 class="converter__output-name">Feet</h3>
			<div class="converter__output valueField">{{ valueFeet }}</div>

			<h3 class="converter__output-name ">Inches</h3>
			<div class="converter__output valueField">{{ valueInches }}</div>

			<h3 class="converter__output-name ">Miles</h3>
			<div class="converter__output valueField">{{ valueMiles }}</div>
		</div>

	</section>
</template>

<script>
	export default {
		data() {
			return {
				valueInput: 0
			}
		},

		computed: {
			valueFeet() {
				return (this.valueInput * 3.281);
			},
		
			valueInches() {
				return (this.valueInput * 39.370);
			},

			valueMiles() {
				return (this.valueInput * 0.0006213);
			}
		}
	}

</script>


<style>
@import url('https://fonts.googleapis.com/css2?family=Bungee+Shade&family=Inter&display=swap');

@import url('https://fonts.googleapis.com/css2?family=Bungee+Hairline&display=swap');

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
		color: #000;
		font-size: 1.3rem;
		margin-top: 1rem;
	}

	.converter__input, .converter__output {
		display: flex;
		flex-direction: column;
		justify-content: center;
		width: 80%;

	} 

	.converter__output-name {
		margin: 0.6rem auto 0.1rem 0.5rem;
		color: #000;
		font-size: 1rem;
		font-family: 'Bungee Hairline', cursive;
		font-style: italic;
	}

	.valueField {
		width: 100%;
		margin: 0.2rem;
		margin-bottom: 0.8rem;
		padding: 0.3rem;
		background: #fff;
		border: 0.2rem solid #6f5643;
		border-radius: 0.5rem;
	}
</style> 