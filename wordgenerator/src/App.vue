<template>
  <main>
    <h1>Word limit is: {{ limit }}</h1>

	<input type="range" 
	min="1"
	max="50"
	:value="limit"
	v-on:change="handleSlideChange"
	>
	<button @click="generateWords">Generate Words</button>

	<div v-if="words" class="card">
		<p> {{ words }} </p>
	</div>
	
  </main>
</template>

<script>

import arrayOfWords from './utils/words';

export default {
  name: 'App',
	data(){
		return {
			limit: 0,
			words: null
		}
	},
  methods: {
	handleSlideChange(e){
			this.limit = e.target.value
		},
	generateWords(){
		this.words = arrayOfWords.slice(0, this.limit).join(' ')
	}
  }
}
</script>

<style >
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;900&display=swap');

* {
	box-sizing: border-box;
	margin: 0;
	padding: 0;
}
html {
	font-family: 'Roboto', sans-serif;
}
main {
	min-height: 100vh;
	width: 100%;
	background-image: url('./assets/lco-wg.jpg');
	background-position: center;
	background-size: cover;
	display: flex;
	justify-content: center;
	flex-direction: column;
	align-items: center;
}
h1 {
	font-size: 55px;
	margin: 25px 0;
	color: #fdb827;
	text-transform: uppercase;
	font-weight: 900;
	text-align: center;
}
p {
	font-size: 20px;
	margin: 20px 0;
	color: #8d3daf;
}

button {
	padding: 15px 50px;
	margin: 20px 0;
	font-size: 18px;
	text-transform: uppercase;
	border-radius: 25px;
	outline: none;
	border: none;
	background-color: #ff4646;
	color: #fff;
	transition: all 0.5s ease;
	cursor: pointer;
}
button:hover {
	transform: scale(1.04);
	color: #f8dc81;
}
.card {
	width: 50%;
	background-color: #fff;
	padding: 20px;
	border-radius: 25px;
	margin: 20px 0;
}

input {
	width: 250px;
}
</style>