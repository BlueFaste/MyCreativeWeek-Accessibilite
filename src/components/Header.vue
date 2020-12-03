<template>
	<header class="d-flex justify-content-between ubuntu-B align-items-center py-2 px-10rem" role="banner">
		<h1 class="projects-title">
			<router-link to="/" title="MyStudentProject - Page principale"><img src="../assets/logo-myStudentProject.png" alt="MyStudentProject" id="logoMDS">
			</router-link>
		</h1>
		<nav class="" role="navigation">
			<router-link role="button" to="/login" v-show="!login" class="text-white blackMDS buttonMDS py-2 px-2" title="Connexion">
				Connexion
			</router-link>
			<router-link role="button" to="/projectmanagement" v-show="login" class="text-white w-100 blackMDS buttonMDS py-2 px-2 w-25" title="Ajouter un projet">Ajouter un
				projet
			</router-link>
			<router-link role="button" to="/" v-show="login" class="text-white w-100 blackMDS buttonMDS py-2 px-2" title="Mon compte">Mon
				compte
			</router-link>
			<b-button @click="deco" class=" blackMDS buttonMDS px-2" style="padding-top: 0.35rem; padding-bottom: 0.35rem" v-show="login">
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
			console.log("test")
			localStorage.removeItem('login', false);
			this.$router.push('/')
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

</style>
