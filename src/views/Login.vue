<template>
	<div>
		<Header></Header>
		<nav aria-label="Breadcrumb" class="breadcrumb mt-4" role="navigation">
			<ul>
				<li>
					<router-link to="/" class="text-dark">Accueil</router-link>
				</li>
				<li aria-current="location">
					<router-link to="/login"> Connexion</router-link>
				</li>
			</ul>
		</nav>
		<main role="main" class="px-10rem d-flex flex-column align-items-center">
			<h2 class="ubuntu-B">Connectez-vous à votre compte MyDigitalSchool</h2>
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
		</main>


		<Footer></Footer>
	</div>
</template>

<script>
import Header from "@/components/Header";
import Footer from "@/components/Footer";

export default {
	name: "Login",
	components: {Footer, Header},
	created() {
		localStorage.removeItem('login')

	},
	methods: {
		login() {
			// console.log('test')
			localStorage.setItem('login', true)
			this.$router.push('/')
		}
	}
}
</script>

<style scoped>


h2 {
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
