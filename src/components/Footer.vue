<template>
	<footer class="footer d-flex justify-content-around align-items-center" role="contentinfo">
		<div>
			<div class="d-flex footerText text-left row p-4 justify-content-between">
				<ul class="col footerLink" role="list">
					<li><router-link to="/"> Accueil </router-link></li>
					<li><router-link to="/login"> Connexion </router-link></li>
					<li><router-link to="/projectmanagement"> Ajouter un projet </router-link></li>
				</ul>
				<ul class="col footerLink" role="list">
					<li><a href="https://www.mydigitalschool.com/" title="MyDigitalSchool - nouvel onglet" target="_blank">MyDigitalSchool</a></li>
				</ul>
				<div class="d-flex flex-column footerLink col">
					<label for="newsletter">Inscrivez-vous à notre <span lang="en">Newsletter</span></label>
					<form action="" method="post" class="d-flex">
						<input type="email" id="newsletter" placeholder="Votre email"/>
						<b-button class="buttonMDS buttonNwlt" title="Confirmer l'email" type="submit" @click.prevent="$router.push('/')">Confirmer</b-button>
					</form>
				</div>
			</div>
			<p id="mentionLegal">© 2020 My Digital School - Tous droits réservés | <a href="https://www.mydigitalschool.com/mentions-legales" class="text-white" title="Mentions Légales - nouvel onglet" target="_blank"> Mentions légales</a></p>

		</div>
		<ul role="list">
			<li class="my-3"><a href="https://www.facebook.com/my.digital.schoolFR/" title="Facebook de MyDigitalSchool - nouvel onglet"><img src="../assets/imgs/Rs/Facebook.png" alt="Facebook de MyDigitalSchool" class="w-75"/></a></li>
			<li class="my-3"><a href="https://www.instagram.com/mydigitalschool/" title="Instagram de MyDigitalSchool - nouvel onglet"><img src="../assets/imgs/Rs/Instagram.png" alt="Instagram de MyDigitalSchool" class="w-75"/></a></li>
			<li class="my-3"><a href="https://www.youtube.com/channel/UC-x9a8FpIuvGoiOkzgL6kFA" title="Youtube de MyDigitalSchool - nouvel onglet"><img src="../assets/imgs/Rs/Youtube.png" alt="Youtube de MyDigitalSchool" class="w-75"/></a></li>
			<li class="my-3"><a href="https://twitter.com/contact_school" title="Twitter de MyDigitalSchool - nouvel onglet"><img src="../assets/imgs/Rs/Twitter.png" alt="Twitter de MyDigitalSchool" class="w-75"/></a></li>
			<li class="my-3"><a href="https://www.linkedin.com/company/mydigitalschool/" title="LinkedIn de MyDigitalSchool - nouvel onglet"><img src="../assets/imgs/Rs/LinkedIn.png" alt="LinkedIn de MyDigitalSchool" class="w-75"/></a></li>
		</ul>

	</footer>
</template>

<script>
export default {
	name: "Footer"
}
</script>

<style scoped>
.footer {
	background-color: black;
	opacity: 80%;
	/*padding: 2rem 12rem;*/
	padding: 1rem 0;
	position: relative;
}

.buttonNwlt {
	margin: 0;
}

.footerText {
	color: white;
	opacity: 80%;
}

ul {
	list-style: none;
}

.footerLink {
	width: 15rem;
}
li a {
	color: white;
}

ul li, label {
	margin-bottom: 1rem;
}

#mentionLegal{
	/*align-self: flex-end;*/
	position: absolute;
	left: 35%;
	color: white;
	opacity: 80%;
  font-size: 0.8rem;
}

</style>
