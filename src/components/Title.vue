<template>
	<h2 class="ubuntu-B d-flex align-items-center mb-5 mt-4"> <span class="colorLine" :id="color"></span>{{title}}</h2>
</template>

<script>
export default {
	name: "Title",
	props:{
		title: String,
		color: String,
	},
	mounted() {
		let span = document.getElementById(this.color)
		if (this.color === 'blue'){
			span.classList.add('blue')

		} else if (this.color === 'yellow') {
			span.classList.add('yellow')

		} else {
			span.classList.add('pink')

		}
	}
}
</script>

<style scoped>
.colorLine{
	/*background-color: red;*/
	display: block;
	width: 0.5rem;
	height: 2rem;
	border-radius: 30px;
	margin-right: 1rem;
}

.blue{
	background-color: #00E9FA;
}

.yellow{
	background-color: #FFBF00;
}

.pink{
	background-color: #FF1D9B;
}

h2{
	font-size: 1.5rem;
}

</style>
