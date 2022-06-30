<template>
	<div id="app">
		<a href="https://www.sbw-media.ch"><img class="logo" alt="sbw logo" src="../src/assets/title-image.svg" /></a>
		<h1 class="h1">VueJs Currency Exchange App M291</h1>
		<div class="container">
			<div class="container-one">
				<select name="first-currency" id="first-currency" @change="calculateResults()" v-model="currency_one">
					<option value="AED">AED</option>
					<option value="ARS">ARS</option>
					<option value="AUD">AUD</option>
					<option value="BGN">BGN</option>
					<option value="BRL">BRL</option>
					<option value="BSD">BSD</option>
					<option value="CAD">CAD</option>
					<option value="CHF">CHF</option>
					<option value="CLP">CLP</option>
					<option value="CNY">CNY</option>
					<option value="COP">COP</option>
					<option value="CZK">CZK</option>
					<option value="DKK">DKK</option>
					<option value="DOP">DOP</option>
					<option value="EGP">EGP</option>
					<option value="EUR">EUR</option>
					<option value="FJD">FJD</option>
					<option value="GBP">GBP</option>
					<option value="GTQ">GTQ</option>
					<option value="HKD">HKD</option>
					<option value="HRK">HRK</option>
					<option value="HUF">HUF</option>
					<option value="IDR">IDR</option>
					<option value="ILS">ILS</option>
					<option value="INR">INR</option>
					<option value="ISK">ISK</option>
					<option value="JPY">JPY</option>
					<option value="KRW">KRW</option>
					<option value="KZT">KZT</option>
					<option value="MXN">MXN</option>
					<option value="MYR">MYR</option>
					<option value="NOK">NOK</option>
					<option value="NZD">NZD</option>
					<option value="PAB">PAB</option>
					<option value="PEN">PEN</option>
					<option value="PHP">PHP</option>
					<option value="PKR">PKR</option>
					<option value="PLN">PLN</option>
					<option value="PYG">PYG</option>
					<option value="RON">RON</option>
					<option value="RUB">RUB</option>
					<option value="SAR">SAR</option>
					<option value="SEK">SEK</option>
					<option value="SGD">SGD</option>
					<option value="THB">THB</option>
					<option value="TRY">TRY</option>
					<option value="TWD">TWD</option>
					<option value="UAH">UAH</option>
					<option value="USD">USD</option>
					<option value="UYU">UYU</option>
					<option value="VND">VND</option>
					<option value="ZAR">ZAR</option>
				</select>
				<input type="number" name="input-one" id="input-one" v-model="amountOne" @input="calculateResults()" />
			</div>
			<div class="container-two">
				<button @click="switchValues()">Switch</button>
				<h4 id="baseValue">1 {{ currency_one }} = {{ rate }} {{ currency_two }}</h4>
			</div>
			<div class="container-there">
				<select id="currency-two" @change="calculateResults()" v-model="currency_two">
					<option value="AED">AED</option>
					<option value="ARS">ARS</option>
					<option value="AUD">AUD</option>
					<option value="BGN">BGN</option>
					<option value="BRL">BRL</option>
					<option value="BSD">BSD</option>
					<option value="CAD">CAD</option>
					<option value="CHF">CHF</option>
					<option value="CLP">CLP</option>
					<option value="CNY">CNY</option>
					<option value="COP">COP</option>
					<option value="CZK">CZK</option>
					<option value="DKK">DKK</option>
					<option value="DOP">DOP</option>
					<option value="EGP">EGP</option>
					<option value="EUR">EUR</option>
					<option value="FJD">FJD</option>
					<option value="GBP">GBP</option>
					<option value="GTQ">GTQ</option>
					<option value="HKD">HKD</option>
					<option value="HRK">HRK</option>
					<option value="HUF">HUF</option>
					<option value="IDR">IDR</option>
					<option value="ILS">ILS</option>
					<option value="INR">INR</option>
					<option value="ISK">ISK</option>
					<option value="JPY">JPY</option>
					<option value="KRW">KRW</option>
					<option value="KZT">KZT</option>
					<option value="MXN">MXN</option>
					<option value="MYR">MYR</option>
					<option value="NOK">NOK</option>
					<option value="NZD">NZD</option>
					<option value="PAB">PAB</option>
					<option value="PEN">PEN</option>
					<option value="PHP">PHP</option>
					<option value="PKR">PKR</option>
					<option value="PLN">PLN</option>
					<option value="PYG">PYG</option>
					<option value="RON">RON</option>
					<option value="RUB">RUB</option>
					<option value="SAR">SAR</option>
					<option value="SEK">SEK</option>
					<option value="SGD">SGD</option>
					<option value="THB">THB</option>
					<option value="TRY">TRY</option>
					<option value="TWD">TWD</option>
					<option value="UAH">UAH</option>
					<option value="USD">USD</option>
					<option value="UYU">UYU</option>
					<option value="VND">VND</option>
					<option value="ZAR">ZAR</option>
				</select>

				<input type="number" id="amount-two" placeholder="0" v-model="amountTwo" disabled />
			</div>
			<div class="container-four">
				<h4 id="lastlyUpdated">Lastly Updated:{{ data.time_last_update_utc }}</h4>
				<button class="download" @click="loggingResults">Herunterladen</button>
			</div>
		</div>
	</div>
</template>

<script setup>
import jsonData from './log.json'

</script>

<script>


export default {
	components: {},
	data() {
		return {
			jsondata: jsonData,
			data: [],
			currency_one: "USD",
			currency_two: "EUR",
			rate: "",
			amountOne: 1,
			amountTwo: 0,
			inputObject: [this.currency_one, this.amountOne],
			outputObject: [this.currency_two, this.amountTwo]
		};
	},

	
	methods: {
		calculateResults() {
			fetch(
				`https://v6.exchangerate-api.com/v6/b7227636d1ec56740d65ea2c/latest/${this.currency_one
				}`
			)
				.then((res) => res.json())	
				.then((data) => {
					this.data = data;
					this.rate = data.conversion_rates[this.currency_two];
					this.amountTwo = this.amountOne * this.rate.toFixed(2);
				});
				
		},
		loggingResults() {
			this.calculateResults();
			if (this.amountOne && this.amountTwo == 0) return;
				const inputObject = {
					currency: this.currency_one,
					input: this.amountOne,
				}
				const outputObject = {
					currency: this.currency_two,
					output: this.amountTwo,
				}
				
			const time = new Date().toLocaleString('en-GB', { timeZone: 'UTC' });
			
			this.download([inputObject, outputObject], time + '-currency-log-json.txt', 'text/plain');

		},

		switchValues() {
			const temp = this.currency_one;
			this.currency_one = this.currency_two;
			this.currency_two = temp;
			this.calculateResults();
		},
		download(content, fileName) {
			var a = document.createElement("a");
			var file = new Blob([JSON.stringify(content)], {type: 'application/json'});
			a.href = URL.createObjectURL(file);
			a.download = fileName;
			a.click();
		}

	},

	mounted() {
		this.calculateResults();
		if(localStorage.inputObject ) {
			this.inputObject = localStorage.inputObject
			console.log("saved in local storage")
		}else {
			this.outputObject = localStorage.outputObject
		}
		},
	watch: {
		Object_data(newinput, newoutput) {
			localStorage.inputObject = newinput;
			localStorage.outputObject = newoutput;
		}
	},

};
</script>

<style lang="sass">
@import url('https://fonts.googleapis.com/css2?family=Oswald:wght@200;300;400&family=Roboto:ital,wght@0,100;0,400;0,500;1,100&display=swap')
html 
	background: #FFFFFF
#app
	margin-top: 50px
	display: flex 
	flex-direction: column 
	align-content: center 
	align-items: center 
	font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif 
	width: 100% 
	height: 100% 
h1 
	font-family: 'Oswald', Extra
	color: #0d3b66
	font-weight: 900 
	font-size: 30px
	text-transform: uppercase
	
	background-image: linear-gradient(-225deg, #231557 0%, #44107a 29%, #ff1361 67%, #fff800 100%)
	background-size: auto auto
	background-clip: border-box
	background-size: 200% auto
	color: #fff

	background-clip: text

	text-fill-color: transparent
	-webkit-background-clip: text
	-webkit-text-fill-color: transparent
	animation: textclip 2s linear infinite

	display: inline-block

	@keyframes textclip 
		to 
			background-position: 200% center
img 
	width: 150px 
.container 
	width: 50% 
	height: 100% 
	display: flex 
	flex-direction: column 
	align-items: center 
	justify-content: center 
	text-align: center 
.container-two 
	display: flex 
	align-content: center 
	align-items: center 
	justify-content: center 
	width: 50% 
	justify-content: space-evenly 
.container-two > h4 
	font-family: 'Roboto'
	font-weight: 500
.container-four > h4 
	font-family: 'Roboto'
button 
		border-radius: 15px
		padding: 8px 
		font-size: 18px 
		background: #0D3B66
		color: #fff 
		height: 10% 
		border: none 
		outline: none 
		cursor: pointer
select 
	padding: 5px 
	margin: 5px 
	border: 1px solid rgba(0, 0, 0, 0.5) 
	outline: none 
input 
	padding: 5px 
	font-size: 18px 
	border: 1px solid rgba(0, 0, 0, 0.5) 
	outline: none 
#lastlyUpdated 
	font-weight: 100 
#baseValue 
	font-weight: 500 
.download
	width: 80%
</style>
