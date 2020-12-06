<template>
	<div class="projectSquare d-flex flex-column justify-content-end align-items-start mb-5" :style="{ backgroundImage: `url(${imgUrl})`}">
		<div class="blackFiltre"></div>
		<h3 class="text-left w-75 ml-4 mb-4"><span class="bg-line">{{ title }}</span></h3>
		<router-link role="button" :to="link" class="align-self-end buttonVoirPlus text-dark" :title="'Voir plus - ' + title">
			Voir plus
		</router-link>
	</div>
</template>

<script>
export default {
	name: "ImgProject",
	props: {
		title: String,
		imgUrl: String,
		link: String,
	}
}
</script>

<style scoped>
.projectSquare {
  position: relative;
  background-size: cover;
  background-position: center;
  height: 45vh;
  width: 40%;
  min-width: 18rem;
}

.bg-line {
	color: black !important;
	background-color: white !important;
	box-shadow: 1rem 0 0 white, 0em 0 0 white !important;
	line-height: 1.5;
}

.buttonVoirPlus, h3 {
	z-index: 10;
}

.buttonVoirPlus {
	font-size: 0.9rem;
}

.buttonVoirPlus, .buttonVoirPlus:hover, .buttonVoirPlus:focus {
	background-color: white;
	border: none;
	border-radius: 0px;
	font-weight: bold;
	margin-right: 2rem;
	margin-bottom: 2rem;
	padding: 0.2rem 0.5rem;
}

</style>
