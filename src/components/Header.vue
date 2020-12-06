<template>
	<header class="d-flex justify-content-between ubuntu-B align-items-center py-2 px-10rem" role="banner">
		<h1 class="projects-title">
			<router-link to="/" title="MyStudentProject - Page principale"><img src="../assets/logo-myStudentProject.png"
																																					alt="MyStudentProject" id="logoMDS">
			</router-link>
		</h1>
		<nav class="" role="navigation">
      <a href="#projetALaUne" class="sr-only" title="Projet à la une - Scroll sur la page"> Le projet à la une</a>
      <a href="#projetsEtudiants" class="sr-only" title="Les projets étudiants récents - Scroll sur la page"> Les projets étudiants récents</a>
      <router-link to="/allprojects" class="sr-only" title="Tous les projets - Nouvelle page"> Tous les projets étudiants</router-link>
      <a href="#tempsForts" class="sr-only" title="Les temps forts - Scroll sur la page"> Les temps forts</a>
			<router-link role="button" to="/login" v-show="!login" class="text-white blackMDS buttonMDS py-2 px-2" title="Connexion">
				Connexion
			</router-link>
			<router-link role="button" to="/projectmanagement" v-show="login" class="text-white w-100 blackMDS buttonMDS py-2 px-2 w-25" title="Ajouter un projet">Ajouter un
				projet
			</router-link>
			<router-link role="button" to="/" v-show="login" class="text-white w-100 blackMDS buttonMDS py-2 px-2" title="Mon compte">Mon
				compte
			</router-link>
			<b-button @click="deco" class=" blackMDS buttonMDS px-2" style="padding-top: 0.35rem; padding-bottom: 0.35rem"
								v-show="login">
				Déconnexion
			</b-button>
		</nav>
	</header>
</template>

<script>
export default {
	name: "Header",
	mounted() {
		// localStorage.removeItem('login');
		// localStorage.setItem('login', true);
	},
	data() {
		return {
			login: localStorage.getItem('login') ? true : false,
		}
	},
	methods: {
		deco() {
			// console.log("test")
			localStorage.removeItem('login', false);
			// console.log(this.$route);
			if (this.$route.path === '/') {
				document.location.reload(true);
			} else {
				this.$router.push('/')

			}
		}
	}
}
</script>

<style scoped>

.projects-title {
	font-size: 1.5rem;
}

#logoMDS {
	width: 10rem;
	/*height: 5rem;*/
}

.sr-only:focus{
  position: relative;
  /*width: 2rem;*/
  /*height: 1rem;*/
}

</style>
