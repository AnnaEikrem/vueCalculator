<template>
	<section class="calculator">
		<h1 class="calculator__headline">Calculator</h1>

		<div class="calculator__outputs">
			{{ showingResult ? currentResult : currentInput }}
		</div>

		<div class="calculator__digits">
			<button @click="clearResult" class="calculator__button calculator__clear">C</button>

			<button @click="handleOperatorInput('/')" class="calculator__button calculator__operator">/</button>

			<button @click="handleDigitInput(7)" class="calculator__button">7</button>

			<button @click="handleDigitInput(8)" class="calculator__button">8</button>

			<button @click="handleDigitInput(9)" class="calculator__button">9</button>

			<button @click="handleOperatorInput('*')" class="calculator__button calculator__operator">*</button>

			<button @click="handleDigitInput(4)" class="calculator__button">4</button>

			<button @click="handleDigitInput(5)" class="calculator__button">5</button>

			<button @click="handleDigitInput(6)" class="calculator__button">6</button>

			<button @click="handleOperatorInput('-')" class="calculator__button calculator__operator">-</button>

			<button @click="handleDigitInput(1)" class="calculator__button">1</button>

			<button @click="handleDigitInput(2)" class="calculator__button">2</button>

			<button @click="handleDigitInput(3)" class="calculator__button">3</button>

			<button @click="handleOperatorInput('+')" class="calculator__button calculator__operator">+</button>

			<button @click="handleDigitInput(0)" class="calculator__button calculator__zero">0</button>

			<button @click="handleDigitInput('.')" class="calculator__button">,</button>

			<button @click="handleEqualsInput" class="calculator__button calculator__operator">=</button> 

		</div>
	</section>
</template>


<script>
	export default {
		data() {
			return {
				currentResult: 0,
				currentInput: '',
				currentOperator: null,
				showingResult: false,
			}
		}, 

		created() {
			window.addEventListener('keyup', this.handleKeyup);
		},

		computed: {
			currentInputAsNumber() {
				return Number(this.currentInput)
			},
		},

		methods: {
			calculateResult() {
				switch(this.currentOperator) {
					case '+':
						this.currentResult += this.currentInputAsNumber;
						break;
					case '-':
						this.currentResult -= this.currentInputAsNumber;
						break;
					case '/':
						this.currentResult /= this.currentInputAsNumber;
						break;
					case '*':
						this.currentResult *= this.currentInputAsNumber;
						break;
					default: 
						this.currentResult = this.currentInputAsNumber;
				}
			}, 

			clearResult() {
				this.currentResult = 0;
				this.currentInput = '';
				this.currentOperator = null;
				this.showingResult = false;
			},

			handleOperatorInput(operator) {
				this.calculateResult();
				this.currentOperator = operator;
				this.currentInput = '';
				this.showingResult = true;
			},

			handleDigitInput(digit) {
				this.currentInput += digit;
				this.showingResult = false;
			},
			
			handleEqualsInput() {
				this.calculateResult();
				this.showingResult = true;
			},

			handleKeyup(event) {
				switch(event.key) {
					case '0':
					case '1':
					case '2':
					case '3':
					case '4':
					case '5':
					case '6':
					case '7':
					case '8':
					case '9':
						this.handleDigitInput(event.key)
						break;
					case '+':
					case '-':
					case '/':
					case '*':
						this.handleOperatorInput(event.key)
						break;
					case '.':
					case ',':
						this.handleDigitInput('.')
						break;
					case '=':
					case 'Enter':
						this.handleEqualsInput()
						break;
					case 'Escape':
					case 'Backspace':
						this.clearResult()
						break;
				}
			}
		}
	}
</script>

	


<style>
@import url('https://fonts.googleapis.com/css2?family=Bungee+Shade&family=Inter&display=swap');

	.calculator {
		height: 100%;
		width: 50%;
		background: #d2a24c;
		padding: 0.75rem;
	}

	.calculator__headline {
		font-family: 'Bungee Shade', cursive;
		color: #000;
		margin-top: 1rem;
		font-size: 1.3rem;
		text-align: center;
	}

	.calculator__outputs {
		display: flex;
		align-items: center;
		justify-content: right;
		width: 80%;
		height: 2rem;
		padding: 1rem;
		margin: 2rem 2rem 1rem 1.5rem;
		border: 0.2rem solid #6f5643;
		background: #fff;
		border-radius: 0.5rem;

		overflow: hidden;
		text-overflow: ellipsis;
		white-space: nowrap;
	}

	.calculator__digits {
		width: 100%;
		height: 55%;
		display: grid;
		grid-template-columns: repeat(4, 25%);	
	}

	.calculator__button {
		width: 90%;
		height: 90%;
		padding: 0.1rem;
		margin: 0.2rem;
		font-size: 1rem;
		font-weight: bold;
		cursor: pointer;
		transition: 0.2s;
		border-radius: 0.25rem;
		background-color: #73bda8;
		border: 0.2rem solid #376659;
	}

	.calculator__zero {
		width: 95%;
		grid-column: span 2;
	}

	.calculator__clear {
		width: 95%;
		grid-column: span 3;
	}

	.calculator__button:hover {
		opacity: 60%;
	}

	.calculator__operator, .calculator__clear {
		background: #eca58b;
		border: 0.2rem solid rgb(242, 90, 90);
	}
</style>