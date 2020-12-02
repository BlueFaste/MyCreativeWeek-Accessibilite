<template>
	<div class="projectSquare text-white d-flex flex-column justify-content-end align-items-start" :id="projetTitle"  :style="{ backgroundImage: `url(${imgUrl})`}" tabindex="0">
		<div class="blackFiltre" v-if="filterBlack"></div>
		<div class="whiteFiltre" v-else></div>
		<h3 class="text-left w-75">{{projetTitle}}</h3>
		<div class="d-flex w-100">
		<span :class="`projectTag ${ecole}`">{{ecoleRewrite}}</span>
		<span :class="`projectTag ${formation}`">{{formationRewrite}}</span>
		</div>
		<b-button class="align-self-end buttonVoirPlus text-dark">Voir plus</b-button>
	</div>
</template>

<script>


export default {
	name: "ProjectDiplay",
	props:{
		projetTitle : String,
		imgUrl: String,
		ecole: String,
		formation: String,
		filterBlack: Boolean,
	},
	mounted() {
		const arrayEcole = this.ecole.split("_")
		const arrayFormation = this.formation.split("_")


		for (const word in arrayEcole){
			this.ecoleRewrite = this.ecoleRewrite + arrayEcole[word] + ' '
		}
		for (const word in arrayFormation){
			this.formationRewrite = this.formationRewrite + arrayFormation[word] + ' '
		}
	},
	data(){
		return{
			ecoleRewrite: "",
			formationRewrite: "",
		}
	}
}
</script>

<style scoped>
.projectSquare{
	position: relative;
	background-size: cover;
	background-position: center;
	height: 21.8vw;
	width: 33%;
}

.projectTag, .buttonVoirPlus, h3{
	z-index: 10;
}
.projectTag:first-child, h3{
	z-index: 10;
	margin-left: 10% !important;
}

h3{
	font-size: 1.2rem;
}

.projectTag{
	border-radius: 20px;
	padding: 0.2rem 0.7rem;
	margin: 1rem 0.5rem;
}

.buttonVoirPlus, .buttonVoirPlus:hover, .buttonVoirPlus:focus{
	background-color: white;
	border: none;
	border-radius: 0px;
	font-weight: bold;
	margin-right: 2rem;
	margin-bottom: 2rem;
	padding: 0.2rem 0.5rem;
}

.Angers{
	background-color: #D83A3A;
}

.Paris{
	background-color: #4D7E2F ;
}

.Bachelor_2 {
background-color: #AE6300;
}

.B3_e-business{
	background-color: #0478A2;
}
</style>
