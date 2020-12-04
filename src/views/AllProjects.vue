<template>
	<div>
		<Header></Header>
		<nav aria-label="Breadcrumb" class="breadcrumb mt-4" role="navigation">
			<ul>
				<li>
					<router-link to="/" class="text-dark">Accueil</router-link>
				</li>
				<li aria-current="location">
					<router-link to="/allprojects">Projets</router-link>
				</li>
			</ul>
		</nav>
		<section class="px-10rem">

			<article
					class="discoveryProject text-white d-flex flex-column justify-content-center align-items-center px-10rem mb-5">
				<div class="blackFiltre"></div>
				<h3 class="discoveryProject_text ubuntu-B mx-5"> Découvrez les projets réalisés au sein des écoles
					MyDigitalSchool</h3>

			</article>
			<article class="d-flex justify-content-between align-items-center ">
				<form class="d-flex justify-content-center">
					<label class="sr-only" for="searchProject">Recherche un projet</label>
					<input type="search" placeholder="Rechercher un projet" class="h-100 p-2 inputSearch" role="search" id="searchProject">
					<b-button class="buttonMDS ml-0" type="submit">Rechercher</b-button>
				</form>

				<div class="d-flex" role="group" aria-label="Filtre">
					<legend class="ubuntu-B text-black mr-4 filtre">Filtres :</legend>
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

			<article class="mt-4 d-flex flex-wrap justify-content-center ">
				<ProjectDisplay v-for="project in projects" :key="project.key" :projet-title="project.title"
												:img-url="project.img" :ecole="project.tagSchool" :formation="project.tagLevel"
												:link="project.link" :filter-black="project.blackFilter"></ProjectDisplay>

				<b-button class="text-dark text-uppercase ubuntu-B py-2 px-3 buttonMDS bg-white my-5">Charger plus de projets
				</b-button>
			</article>
		</section>


		<Footer></Footer>
	</div>
</template>

<script>
import Header from "@/components/Header";
import Footer from "@/components/Footer";
import ProjectDisplay from "@/components/ProjectDisplay";

export default {
	name: "AllProjects",
	components: {
		ProjectDisplay, Header, Footer
	},
	data() {
		return {
			projects: [
				{
					title: 'La 5ème édition de la connected week',
					tagSchool: 'Angers',
					tagLevel: 'Bachelor_2',
					img: '../imgs/workplace-1245776_1920.png',
					link: '/project',
					blackFilter: true,
				},
				{
					title: 'Le Motion Design Contest',
					tagSchool: 'Angers',
					tagLevel: 'B3_Webdesign',
					img: '../imgs/office-620817_1920.png',
					link: '/project',
					blackFilter: false,
				},
				{
					title: 'Le concours d’infographie',
					tagSchool: 'Lyon',
					tagLevel: 'MBA_UX-UI_design',
					img: '../imgs/startup-1.png',
					link: '/project',
					blackFilter: true,
				},
				{
					title: 'Le projet Fil Rouge à l’honneur cette année',
					tagSchool: 'Grenoble',
					tagLevel: 'Bachelor_1',
					img: '../imgs/startup-594090_1920.png',
					link: '/project',
					blackFilter: false,
				},
				{
					title: 'Le challenge Portfolio',
					tagSchool: 'Lille',
					tagLevel: 'B3_Webmarketing',
					img: '../imgs/pexels-serpstat-572056.png',
					link: '/project',
					blackFilter: true,
				},
				{
					title: 'English game : un projet d’une semaine',
					tagSchool: 'Bordeaux',
					tagLevel: 'B3_Webmarketing',
					img: '../imgs/startup-594091_1920.png',
					link: '/project',
					blackFilter: false,
				},
				{
					title: 'My Digital Strat-up',
					tagSchool: 'Nantes',
					tagLevel: 'Bachelor_2',
					img: '../imgs/pexels-marc-mueller-380769.png',
					link: '/project',
					blackFilter: true,
				},
				{
					title: 'Pitch ton CV : Le nouveau challenge des B2',
					tagSchool: 'Montpellier',
					tagLevel: 'MBA_Marketing_Digital',
					img: '../imgs/pexels-vlada-karpovich-4050320.png',
					link: '/project',
					blackFilter: false,
				},
				{
					title: 'My Digital Week Édition 2020',
					tagSchool: 'Paris',
					tagLevel: 'Bachelor_1',
					img: '../imgs/pexels-lukas-574071.png',
					link: '/project',
					blackFilter: true,
				},
				{
					title: 'La 5ème édition de la connected week',
					tagSchool: 'Angers',
					tagLevel: 'Bachelor_2',
					img: '../imgs/workplace-1245776_1920.png',
					link: '/project',
					blackFilter: false,
				},
				{
					title: 'Le Motion Design Contest',
					tagSchool: 'Angers',
					tagLevel: 'B3_Webdesign',
					img: '../imgs/office-620817_1920.png',
					link: '/project',
					blackFilter: true,
				},
				{
					title: 'Le concours d’infographie',
					tagSchool: 'Lyon',
					tagLevel: 'MBA_UX-UI_design',
					img: '../imgs/startup-1.png',
					link: '/project',
					blackFilter: false,
				},
				{
					title: 'Le projet Fil Rouge à l’honneur cette année',
					tagSchool: 'Grenoble',
					tagLevel: 'Bachelor_1',
					img: '../imgs/startup-594090_1920.png',
					link: '/project',
					blackFilter: true,
				},
				{
					title: 'Le challenge Portfolio',
					tagSchool: 'Lille',
					tagLevel: 'B3_Webmarketing',
					img: '../imgs/pexels-serpstat-572056.png',
					link: '/project',
					blackFilter: false,
				},
				{
					title: 'English game : un projet d’une semaine',
					tagSchool: 'Bordeaux',
					tagLevel: 'B3_Webmarketing',
					img: '../imgs/startup-594091_1920.png',
					link: '/project',
					blackFilter: true,
				},
			],
		}
	}
}
</script>

<style scoped>
.discoveryProject {
	background-image: url("../assets/imgs/startup-594091_1920-bannier.png");
	background-size: cover;
	background-repeat: no-repeat;
	background-position: center;
	width: 100%;
	height: 47vh;
	padding-right: 20%;
	padding-left: 20%;
	position: relative;
	margin: 2rem 0;
}

.discoveryProject_text {
	z-index: 10;
}


.px-15rem {
	padding-left: 13rem;
	padding-right: 13rem;
}

.inputSearch {
	background-color: #F5F5F5;
	border: solid #B1B1B1 1px;
}


</style>
