<template>
	<div class="d-flex flex-column justify-content-between">
		<Header></Header>
		<section>
			<article v-if="!login" class="px-10rem">
				<p class="mb-5">Pour ajouter un projet connectez-vous s'il vous plait.</p>
				<router-link role="button" to="/login" v-show="!login" class="text-white blackMDS buttonMDS py-2 px-2 ubuntu-B" title="Connexion">
					Connexion
				</router-link>
			</article>

			<article v-else>
				<nav aria-label="Breadcrumb" class="breadcrumb px-10rem" role="navigation">
					<ul>
						<li>
							<router-link to="/" class="text-dark">Accueil</router-link>
						</li>
						<li>
							<router-link to="/" class="text-dark">Mon compte</router-link>
						</li>
						<li aria-current="location">
							<router-link to="/projectmanagement">Gestion de projet</router-link>
						</li>
					</ul>
				</nav>

				<div class="px-10rem">
					<b-button class="text-uppercase mx-5 buttonManagement active" @click="setActive('addProject')"
										id="addProject">Ajouter un projet
					</b-button>
					<b-button class="text-uppercase mx-5 buttonManagement" @click="setActive('managementProject')"
										id="managementProject">Gérer les projets
					</b-button>
				</div>

				<AddProject></AddProject>

			</article>

		</section>
		<Footer class=""></Footer>
	</div>
</template>

<script>
import Header from "@/components/Header";
import Footer from "@/components/Footer";
import AddProject from "@/views/projectManagement/AddProject";

export default {
	name: "projectManagement",
	components: {AddProject, Footer, Header},
	data() {
		return {
			login: localStorage.getItem('login') ? true : false,
			pageActive: "addProject"

		}
	},
	methods: {
		setActive(idButton) {
			const buttonCourentActive = document.getElementsByClassName('active')
			buttonCourentActive[0].classList.remove('active')
			const buttonBecomeActive = document.getElementById(idButton)
			buttonBecomeActive.classList.add('active')
			this.pageActive = idButton

		}
	}
}
</script>

<style scoped>

.buttonManagement {
	background-color: white !important;
	border: none !important;
	border-radius: 0px !important;
	color: #8E8E8E !important;
}

.buttonManagement.active {
	color: black !important;
	border-bottom: solid black 2px !important;
}

</style>
