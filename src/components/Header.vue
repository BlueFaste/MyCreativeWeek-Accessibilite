<template>
	<header class="d-flex justify-content-between ubuntu-B align-items-center py-2 px-10rem" role="banner">
		<h1 class="projects-title">
			<img src="../assets/logo-MyDigitalProject.png" alt="MyDigitalProject" id="logoMDS">
		</h1>
		<div>
			<b-button v-show="!login" class="blackMDS buttonMDS">Connexion</b-button>
			<b-button v-show="login" class="blackMDS buttonMDS">Ajouter un projet</b-button>
			<b-button v-show="login" class="blackMDS buttonMDS">Mon compte</b-button>
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
	data(){
		return{
			login : localStorage.getItem('login') ? true : false,
		}
	}
}
</script>

<style scoped>

.projects-title{
	font-size: 1.5rem;
}

#logoMDS{
	width: 10rem;
	/*height: 5rem;*/
}

</style>
