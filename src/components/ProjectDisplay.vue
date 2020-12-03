<template>
	<div class="projectSquare text-white d-flex flex-column justify-content-end align-items-start" :id="projetTitle" :style="{ backgroundImage: `url(${imgUrl})`}" tabindex="0">
		<div class="blackFiltre" v-if="filterBlack"></div>
		<div class="whiteFiltre" v-else></div>
      <h3 class="text-left w-75"><span class="test">{{ projetTitle }}</span></h3>
		<div class="d-flex w-100 align-items-center ">
			<span :class="`projectTag ${ecole}`">{{ ecoleRewrite }}</span>
			<span :class="`projectTag ${formation} `">{{ formationRewrite }}</span>
		</div>
    <router-link role="button" :to="link" class="align-self-end buttonVoirPlus text-dark" :title="'Voir plus - ' + projetTitle">
     Voir plus
    </router-link>
	</div>
</template>

<script>


export default {
	name: "ProjectDiplay",
	props: {
		projetTitle: String,
		imgUrl: String,
		ecole: String,
		formation: String,
    link: String,
		filterBlack: Boolean,
	},
	mounted() {
		const arrayEcole = this.ecole.split("_")
		const arrayFormation = this.formation.split("_")


		for (const word in arrayEcole) {
			this.ecoleRewrite = this.ecoleRewrite + arrayEcole[word] + ' '
		}
		for (const word in arrayFormation) {
			this.formationRewrite = this.formationRewrite + arrayFormation[word] + ' '
		}
	},
	data() {
		return {
			ecoleRewrite: "",
			formationRewrite: "",
		}
	}
}
</script>

<style scoped>
.test{
  color:black !important;
  background-color: white !important;
  box-shadow: 1rem 0 0 white,0em 0 0 white !important;
  line-height: 1.5;
}


.projectSquare {
	position: relative;
	background-size: cover;
	background-position: center;
	height: 21.8vw;
	width: 33%;
}

.projectTag, .buttonVoirPlus, h3 {
	z-index: 10;
}

.projectTag:first-child, h3 {
	z-index: 10;
	margin-left: 10% !important;
}

h3 {
	font-size: 1.2rem;
}

.projectTag {
	border-radius: 20px;
	padding: 0.2rem 0.7rem;
	margin: 1rem 0.5rem;
  height: max-content;
}

.buttonVoirPlus, .projectTag{
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

.Inter-école{
  background-color: #005757;
}

.Angers {
	background-color: #A72B00;
}

.Paris {
	background-color: #D3273E;
}

.Annecy {
	background-color: #5D3754;
}

.Bordeaux {
	background-color: #007A78;
}

.Caen {
	background-color: #BE0D0D;
}

.Grenoble {
	background-color: #7A4600;
}

.Lille {
	background-color: #973094;
}

.Lyon {
	background-color: #4F3097;
}

.Melun {
	background-color: #304697;
}

.Montpellier {
	background-color: #4B60A0;
}

.Nantes {
	background-color: #A04B4C;
}

.Nice {
	background-color: #197BB8;
}

.Rennes {
	background-color: #2D7B36;
}

.Saint-Quentin {
	background-color: #4C2CA3;
}

.Toulouse {
	background-color: #2A5B4A;
}

.Vannes {
	background-color: #6D7500;
}

.Bachelor_1{
  background-color: #193171;
}

.Bachelor_2 {
	background-color: #1F6FBF;
}

.B3_Webdesign,
.B3_e-Business ,
.B3_Développeur_Web,
.B3_Webmarketing{
  background-color: #4529B9;
}

.MBA_Marketing_Digital, .MBA_Data_Marketing,
.MBA_UX-UI_design,
.MBA_Développeur_full-stack,
.MBA_Management_Digital{
  background-color: #487C1B;
}

</style>
