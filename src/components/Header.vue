<template>
	<header class="d-flex justify-content-between ubuntu-B align-items-center py-2 px-10rem" role="banner">
		<h1 class="projects-title">
			<router-link to="/"><img src="../assets/logo-MyDigitalProject.png" alt="MyDigitalProject" id="logoMDS">
			</router-link>
		</h1>
		<div>
			<router-link role="button" to="/login" v-show="!login" class="text-white w-100 blackMDS buttonMDS py-2 px-2" title="Connexion">
				Connexion
			</router-link>
			<router-link role="button" to="/" v-show="login" class="text-white w-100 blackMDS buttonMDS py-2 px-2" title="Ajouter un projet">Ajouter un projet
			</router-link>
			<router-link role="button" to="/" v-show="login" class="text-white w-100 blackMDS buttonMDS py-2 px-2" title="Mon compte">Mon
				compte
			</router-link>
		</div>
	</header>
</template>

<script>
export default {
	name: "Header",
	mounted() {
		localStorage.removeItem('login', false);
		// localStorage.setItem('login', true);
	},
	data() {
		return {
			login: localStorage.getItem('login') ? true : false,
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
