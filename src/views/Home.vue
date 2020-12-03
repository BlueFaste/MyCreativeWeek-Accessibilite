<template>
	<div class="home">
		<Header></Header>
		<main role="main" tabindex="-1">
			<section class="px-10rem">
				<Title title="Les projets à la une" color="blue" class="text-uppercase"></Title>
				<article class="projetUne text-white d-flex flex-column justify-content-end align-items-start">
					<div class="blackFiltre"></div>
					<h3 class="projetUne_text ubuntu-B "> La 5ème édition de la Connected Week</h3>
					<p class="projetUne_text ubuntu-B ">Bachelor 2 - Projet inter-école</p>
				</article>
			</section>

			<article class="px-20rem d-flex flex-column align-items-center my-4">
				<h3 class="ubuntu-B my-4 text-uppercase ubuntu-B">L'école MyDigitalSchool</h3>
				<p class="w-80">MyDigitalSchool est une école web ouverte à toutes et à tous, aux initiés
					comme aux débutants et
					se donne pour objectif d’ouvrir le monde du digital à tous les talents.</p>
				<p class="w-80"> Sans profilage, ni prérequis, la pédagogie de l’école vise à former les étudiants et étudiantes
					à la maîtrise technique du web tout en leur garantissant une ouverture d’esprit sur les environnements et
					métiers liés à cet univers : e-commerce, communication, marketing, éditorial. Elle valorise les compétences de
					logique et clarté de raisonnement, comme de créativité, d’intuition et de maîtrise des langues.</p>
			</article>

			<section class="projects px-10rem py-4">
				<Title title="Les projets étudiants" color="yellow" class="text-white text-uppercase"></Title>
				<div class="px-5rem">
					<article class="d-flex justify-content-between align-items-center">
						<form class="d-flex justify-content-center">
							<label class="sr-only">Recherche un projet</label>
							<input type="search" placeholder="Rechercher un projet" class="h-100 p-2" role="search">
							<b-button class="buttonMDS ml-0">Rechercher</b-button>
						</form>

						<div class="d-flex" role="group" aria-label="Filtre">
							<legend class="ubuntu-B text-white mr-4 filtre">Filtres :</legend>
							<select id="ecoles" name="Écoles" class="mx-2">
								<option value="">École</option>
								<option value="Angers">Angers</option>
								<option value="Annecy">Annecy</option>
								<option value="Bordeaux">Bordeaux</option>
								<option value="Caen">Caen</option>
								<option value="Grenoble">Grenoble</option>
								<option value="Lille">Lille</option>
								<option value="Lyon">Lyon</option>
								<option value="Melun">Melun</option>
								<option value="Montpellier">Montpellier</option>
								<option value="Nantes">Nantes</option>
								<option value="Nice">Nice</option>
								<option value="Paris">Paris</option>
								<option value="Rennes">Rennes</option>
								<option value="Saint Quentin en Yvelines">Saint Quentin en Yvelines</option>
								<option value="Toulouse">Toulouse</option>
								<option value="Vannes">Vannes</option>
							</select>
							<select id="promotion" name="Promotion" class="mx-2">
								<option value="">Promotion</option>
								<option value="B1">B1</option>
								<option value="B2">B2</option>
								<option value="B3 - E-BUSINESS">B3 - E-BUSINESS</option>
								<option value="B3 - WEBMARKETING ET SOCIAL MEDIA">B3 - WEBMARKETING ET SOCIAL MEDIA</option>
								<option value="B3 - WEBDESIGN">B3 - WEBDESIGN</option>
								<option value="B3 - DEVELOPPEUR WEB">B3 - DEVELOPPEUR WEB</option>
								<option value="MBA EXPERT DATA MARKETING">MBA EXPERT DATA MARKETING</option>
								<option value="MBA MARKETING DIGITAL">MBA MARKETING DIGITAL</option>
								<option value="MBA MANAGEMENT DE L'INNOVATION DIGITAL">MBA MANAGEMENT DE L'INNOVATION DIGITAL</option>
								<option value="MBA UX/UI">MBA UX/UI</option>
								<option value="MBA SYSTEMES D'INFORMATION">MBA SYSTEMES D'INFORMATION</option>
							</select>
						</div>
					</article>

					<article class=" mt-4 d-flex flex-wrap justify-content-center">
						<ProjectDisplay v-for="project in projects" :key="project.key" :projet-title="project.title"  :img-url="project.img"  :ecole="project.tagSchool" :formation="project.tagLevel" :link="project.link" :filter-black="project.blackFilter"></ProjectDisplay>

						<router-link role="button" to="/" title="Tous les projets" class="buttonMDS my-4 bg-white text-dark text-uppercase ubuntu-B py-2 px-3">Tous les projets</router-link>
					</article>
				</div>
			</section>

			<section class="px-10rem py-4 bg-grey">
				<Title title="Les temps forts" color="pink" class="text-uppercase"></Title>
				<article class="d-flex justify-content-center">
					<ul class="ubuntu-B mr-4">
						<li class="my-3">
							<b-button class="noButton buttonCollaspeOpen" @click="collaspeOpen('B1','buttonB1')" id="buttonB1">
								Bachelor 1
							</b-button>
						</li>
						<li class="my-3">
							<b-button class="noButton" @click="collaspeOpen('B2','buttonB2')" id="buttonB2">Bachelor 2</b-button>
						</li>
						<li class="my-3">
							<b-button class="noButton" @click="collaspeOpen('B3','buttonB3')" id="buttonB3">Bachelor 3</b-button>
						</li>
						<li class="my-3">
							<b-button class="noButton" @click="collaspeOpen('M1-2','buttonM1_2')" id="buttonM1_2">Master 1-2
							</b-button>
						</li>

					</ul>

					<Collaspe class="w-75" v-show="collapseOpen==='B1'" :temps-fort="B1TF"></Collaspe>
					<Collaspe class="w-75" v-show="collapseOpen==='B2'" :temps-fort="B2TF" id="test"></Collaspe>
					<Collaspe class="w-75" v-show="collapseOpen==='B3'" :temps-fort="B3TF"></Collaspe>
					<Collaspe class="w-75" v-show="collapseOpen==='M1-2'" :temps-fort="M1_2TF"></Collaspe>
				</article>
			</section>
			<article class=" d-flex flex-column align-items-center my-4">
				<h3 class="ubuntu-B my-4 mb-5 text-uppercase">Une école digitale et polyvalante</h3>
				<div class="d-flex justify-content-center px-10rem">
					<SchoolSubject v-for="subject in schoolSubject" :icon="subject.icon" :subject="subject.subject"  :desc="subject.desc" :key="subject.key"></SchoolSubject>
				</div>
				<b-button class="buttonMDS buttonESP bg-light mb-5 mt-4">
					<a role="button" target="_blank" href="https://www.mydigitalschool.com/" class="text-dark text-uppercase ubuntu-B py-4" title="En savoir plus sur MyDigitalSchool - nouvel onglet">En savoir plus</a>
				</b-button>
			</article>
		</main>


		<Footer></Footer>
	</div>
</template>

<script>
import Header from "@/components/Header";
import Footer from "@/components/Footer";
import Title from "@/components/Title";
import ProjectDisplay from "@/components/ProjectDisplay";
import Collaspe from "@/components/Collaspe";
import SchoolSubject from "@/components/SchoolSubject";

export default {
	name: 'Home',
	components: {
		SchoolSubject,
		Collaspe,
		ProjectDisplay,
		Title,
		Footer,
		Header,
	},
	data() {
		return {
			collapseOpen: "B1",
			projects: [
				{
					title: 'La 5ème édition de la connected week',
					tagSchool: 'Inter-école',
					tagLevel: 'Bachelor_2',
					img: '../imgs/workplace-1245776_1920.png',
					link:'/',
          blackFilter: true,
				},
				{
					title: 'Le Motion Design Contest',
					tagSchool: 'Angers',
					tagLevel: 'B3_Webdesign',
					img: '../imgs/office-620817_1920.png',
					link:'/',
          blackFilter: false,
				},
				{
					title: 'Le concours d’infographie',
					tagSchool: 'Lyon',
					tagLevel: 'MBA_UX-UI_design',
					img: '../imgs/startup-1.png',
					link:'/',
          blackFilter: true,
				},
				{
					title: 'Le projet Fil Rouge à l’honneur cette année',
					tagSchool: 'Grenoble',
					tagLevel: 'Bachelor_1',
					img: '../imgs/startup-594090_1920.png',
					link:'/',
          blackFilter: false,
				},
				{
					title: 'Le challenge Portfolio',
					tagSchool: 'Lille',
					tagLevel: 'B3_Webmarketing',
					img: '../imgs/pexels-serpstat-572056.png',
					link:'/',
          blackFilter: true,
				},
				{
					title: 'English game : un projet d’une semaine',
					tagSchool: 'Bordeaux',
					tagLevel: 'B3_Webmarketing',
					img: '../imgs/startup-594091_1920.png',
					link:'/',
          blackFilter: false,
				},
				{
					title: 'My Digital Strat-up',
					tagSchool: 'Nantes',
					tagLevel: 'Bachelor_2',
					img: '../imgs/pexels-marc-mueller-380769.png',
					link:'/',
          blackFilter: true,
				},
				{
					title: 'Pitch ton CV : Le nouveau challenge des B2',
          tagSchool: 'Montpellier',
          tagLevel: 'MBA_Marketing_Digital',
					img: '../imgs/pexels-vlada-karpovich-4050320.png',
					link:'/',
          blackFilter: false,
				},
				{
					title: 'My Digital Week Édition 2020',
          tagSchool: 'Paris',
          tagLevel: 'Bachelor_1',
					img: '../imgs/pexels-lukas-574071.png',
					link:'/',
          blackFilter: true,
				},
			],
			B1TF: [
				{
					id: 'B1TF_MDW',
					title: 'My Digital Week',
					desc: '',
				},
				{
					id: 'B1TF_MCW',
					title: 'My Creative Week',
					desc: '',
				},
				{
					id: 'B1TF_PFR',
					title: 'Projet fil rouge',
					desc: '',
				},
			],
			B2TF: [
				{
					id: 'B2TF_MCW',
					title: 'My Creative Week',
					desc: '',
				},
				{
					id: 'B2TF_PTC',
					title: 'Pitch ton CV',
					desc: 'Concours de CV vidéo.',
				},
				{
					id: 'B2TF_PFR',
					title: 'Projet fil rouge',
					desc: 'Accompagner un client réel sur ses problématiques digitales.',
				},
			],
			B3TF: [
				{
					id: 'B3TF_EG',
					title: 'ENGLISH GAME',
					desc: 'Projet à réaliser sur une semaine pour un client anglophone, immersion d’une semaine en anglais.',
				},
				{
					id: 'B3TF_MDP',
					title: 'MY DIGITAL PROJECT',
					desc: 'Création d’un projet de bout en bout jusqu’à la création d’un prototype.',
				}, {
					id: 'B3TF_PF',
					title: 'PORTFOLIO',
					desc: 'Réalisation d’un porfolio professionnel.',
				}, {
					id: 'B3TF_MDC',
					title: 'MOTION DESIGN CONTEST ',
					desc: 'Réalisation d’une vidéo en motion design. ',
				}, {
					id: 'B3TF_CI',
					title: 'CONCOURS D’INFOGRAPHIE ',
					desc: 'Création d’une infographie claire et impactante.',
				}, {
					id: 'B3TF_TC',
					title: 'TOP CODE ',
					desc: 'Concours battle dev.',
				},
			],
			M1_2TF: [
				{
					id: 'M1_2TF_MDSU',
					title: 'MY DIGITAL START UP ',
					desc: 'Création de votre start up.',
				},
				{
					id: 'M1_2TF_WC',
					title: 'WORKSHOPS CLIENTS ',
					desc: 'Travailler en mode agence sur des projets clients réels.',
				},
			],
			schoolSubject: [
				{
					subject: 'Développement',
					desc: 'Lorem ipsum dolor sit amet,consectetur adipiscing elit. Pellentesque luctus egestas rutrum.',
					icon: '../icons/dev.png',
				}, {
					subject: 'Design',
					desc: 'Lorem ipsum dolor sit amet,consectetur adipiscing elit. Pellentesque luctus egestas rutrum.',
					icon: '../icons/design.png',
				}, {
					subject: 'Marketing',
					desc: 'Lorem ipsum dolor sit amet,consectetur adipiscing elit. Pellentesque luctus egestas rutrum.',
					icon: '../icons/market.png',
				},
			]
		}
	},
	methods: {
		collaspeOpen(collapse, idButton) {
			this.collapseOpen = collapse
			const buttonCourentOpen = document.getElementsByClassName('buttonCollaspeOpen')
			buttonCourentOpen[0].classList.remove('buttonCollaspeOpen')
			const buttonCollapseOpen = document.getElementById(idButton)
			buttonCollapseOpen.classList.add('buttonCollaspeOpen')
			const aaa = document.getElementById('buttonB2TF_MCW')
			console.log(aaa)
			aaa.focus()
			console.log(document.activeElement)
		}
	}
}
</script>

<style>
.projetUne {
	background-image: url("../assets/imgs/projet_a_la_une.png");
	width: 100%;
	height: 47vh;
	/*padding: 5rem;*/
	position: relative;
	margin: 2rem 0;
}

.projetUne_text {
	margin-left: 5rem;
	margin-bottom: 1rem;
	z-index: 10;
}

.projetUne_text:last-child {
	margin-bottom: 5rem;
}


.blackFiltre {
	position: absolute;
	background-color: black;
	width: 100%;
	height: 100%;
	opacity: 50%;
}

.whiteFiltre {
	position: absolute;
	background-color: white;
	width: 100%;
	height: 100%;
	opacity: 5%;
}

.px-20rem {
	padding: 0 20rem;
}

.projects {
	background-color: black;
	opacity: 80%;
}

input {
	border: none;
}

#ecoles, #promotion {
	width: 8rem;
	height: 2rem;
}

ul {
	list-style: none;
}

.noButton {
	background-color: transparent !important;
	color: black !important;
	border: none !important;
	border-radius: 0 !important;
}

.noButton:hover, .noButton:focus {
	background-color: #B4B4B4 !important;
	border-right: solid #707070 !important;
}

.buttonCollaspeOpen {
	background-color: #B4B4B4 !important;
	border-right: solid #707070 !important;
}

.filtre {
	font-size: 1rem;
}

/*.buttonESP{*/
/*  background-color: white !important;*/
/*  color: black !important;*/
/*}*/
</style>
