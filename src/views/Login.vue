<template>
	<div>
		<Header></Header>
		<nav aria-label="Breadcrumb" class="breadcrumb">
			<ul>
				<li>
					<router-link to="/" class="text-dark">Accueil</router-link>
				</li>
				<li><span aria-current="page">Connexion</span></li>
			</ul>
		</nav>
		<article class="px-10rem d-flex flex-column align-items-center">
			<h1 class="ubuntu-B">Connectez-vous à votre compte MyDigitalSchool</h1>
			<form class="d-flex flex-column align-items-start my-5" method="post" action="">
				<div class="mt-3 mb-3">
					<label class="ubuntu-B mr-4" for="email">Email : </label>
					<input type="email" class="email" placeholder="Entrez votre email" id="email">

				</div>
				<div class="mt-3 mb-4">
					<label class="ubuntu-B mr-4" for="mdp">Mot de passe : </label>
					<input type="password" class="mdp" placeholder="Entrez votre mot de passe" id="mdp">

				</div>
				<router-link to="/login" class="font-size-0_8rem align-self-end text-dark" title="Mot de passe oublié">Mot de
					passe oublié ?
				</router-link>
				<b-button type="submit" class="buttonMDS align-self-center my-5 blackMDS ubuntu-B" @click.prevent="login">
					Connexion
				</b-button>
			</form>
		</article>


		<Footer></Footer>
	</div>
</template>

<script>
import Header from "@/components/Header";
import Footer from "@/components/Footer";

export default {
	name: "Login",
	components: {Footer, Header},
	methods: {
		login() {
			console.log('test')
			localStorage.setItem('login', true)
			this.$router.push('/')
		}
	}
}
</script>

<style scoped>

.breadcrumb {
	background-color: white !important;
}

.breadcrumb ul {
	display: flex;
	list-style-type: none;
}

.breadcrumb li::before {
	content: ">";
	margin-left: 1rem;
	margin-right: 1rem;
}

.breadcrumb li:first-child::before {
	content: "";
}

h1 {
	/*font-family: Ubuntu Mono;*/
	font-size: 1.5rem;
	color: #393939;
}

p {
	/*font-family: Helvetica Neue;*/
	color: #393939;
}

/*.connexion {*/
/*  margin-top: 4rem;*/
/*  margin-left: auto;*/
/*  margin-bottom: 2rem;*/
/*  margin-right: auto;*/
/*  width: 18.3rem;*/
/*  height: 8.5rem;*/
/*}*/

.email {
	width: 18.7rem !important;
	/*  width: 15rem;*/
	/*  height: 2rem;*/
	/*  font-size: 0.7rem;*/
	/*  border-color: #C9C9C9;*/
}

/*.mdp {*/
/*  width: 11.3rem;*/
/*  height: 2rem;*/
/*  font-size: 0.7rem;*/
/*  border-color: #C9C9C9;*/
/*}*/

.email, .mdp {
	border: solid #C9C9C9 2px;
	width: 15rem;
}

.font-size-0_8rem {
	font-size: 0.8rem;
}

.valider {
	border: none;
	width: 5rem;
	font-family: Ubuntu Mono;
}
</style>
