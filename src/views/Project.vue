<template>
	<div>
		<Header></Header>
		<nav aria-label="Breadcrumb" class="breadcrumb mt-4" role="navigation">
			<ul>
				<li>
					<router-link to="/" class="text-dark">Accueil</router-link>
				</li>
				<li>
					<router-link to="/" class="text-dark"> Project</router-link>
				</li>
				<li aria-current="location">
					<router-link to="/"> La 5ème édition de la Connected Week</router-link>
				</li>
			</ul>
		</nav>
		<main role="main" class="mb-5">
			<section>
				<div class="px-10rem">
					<article class="projetUne text-white d-flex flex-column justify-content-center align-items-center">
						<div class="blackFiltre"></div>
						<h3 class="projetUne_text ubuntu-B mt-auto"> La 5ème édition de la Connected Week</h3>
						<div class="d-flex w-100 align-items-center  justify-content-center">
							<span class="projectTag Inter-école">Inter-école</span>
							<span class="projectTag Bachelor_2">Bachelor 2</span>
						</div>
						<p class="projetUne_text ubuntu-B mb-auto">01 Décembre 2020</p>
					</article>

				</div>
				<article class="px-10rem my-5">
					<Title title="Le projet" color="yellow" class="text-uppercase"></Title>
					<div class="text-left px-4"><p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi semper finibus dolor
						ultricies ultricies.</p>

						<p>Etiam in metus nec arcu lobortis tempor eget vitae lacus. Aliquam rhoncus metus sed lorem dapibus
							finibus.
							Nunc sollicitudin mauris et erat tempor tempor. Fusce nec tortor in nisi commodo iaculis vel ut sapien.
							Etiam ut sollicitudin mi. Vivamus eget nibh tincidunt, ultrices tellus sodales, faucibus sem. Fusce sed
							dolor ut mi pellentesque accumsan at non purus. Integer efficitur non ligula ut venenatis. Aenean in
							mattis
							felis. Suspendisse purus libero, maximus id massa sed, consequat sagittis lorem.</p>

						<p>Mauris semper tortor in metus tempus placerat. Vestibulum sed magna eget felis tincidunt fringilla
							feugiat
							nec diam. Fusce sed libero massa. Nam odio tortor, tincidunt euismod lobortis quis, iaculis varius libero.
							In egestas malesuada dolor. Aliquam justo ligula, consectetur sit amet laoreet id, vehicula ac orci.</p>

						<p>Phasellus odio libero, lacinia vel fringilla a, aliquam eget turpis. Donec non leo purus. Morbi cursus
							pulvinar diam, aliquam condimentum lectus efficitur eget. Donec ultricies dolor aliquet consequat
							accumsan.
							Quisque eu ante vitae dolor ultrices molestie rhoncus nec tortor. Sed interdum lacus at justo rutrum
							maximus. Curabitur eget magna quis lacus tempus fringilla a id ipsum.</p></div>
				</article>
				<article>
					<div class="px-10rem bg-grey px-10rem py-4">
						<Title title="Les réalisations" color="pink" class="text-uppercase"></Title>
						<div class="position-relative divImgProject">
							<img src="../assets/imgs/mockup-real.png" alt="Mockup du projet MyDigitalProject" class="imgMockUp">
						</div>
					</div>
					<div class="px-10rem d-flex align-items-center justify-content-around flex-wrap" style="padding-top: 15rem">
						<ImgProject v-for="img in imgProject" :key="img.key" :title="img.title" :img-url="img.imgUrl"
												:link="img.link"></ImgProject>


					</div>
				</article>
				<router-link role="button" to="/" class="buttonMDS text-uppercase text-black ubuntu-B py-2 px-2 my-5"> Voir d'autres Projets
				</router-link>
			</section>
		</main>
		<Footer></Footer>
	</div>

</template>

<script>
import Header from "@/components/Header";
import Footer from "@/components/Footer";
import Title from "@/components/Title";
import ImgProject from "@/components/ImgProject";

export default {
	name: "Project",
	components: {ImgProject, Title, Footer, Header},
	data() {
		return {
			imgProject: [
				{
					title: 'Création d\'un logo',
					imgUrl: '../imgs/Rectangle-220.png',
					link: '/',
				},
				{
					title: 'Réalisation d\'une étude de marché',
					imgUrl: '../imgs/Rectangle-221.png',
					link: '/',
				},
				{
					title: 'Développement d\'un site web',
					imgUrl: '../imgs/Rectangle-222.png',
					link: '/',
				},
				{
					title: 'Conception d\'une vidéo Teaser',
					imgUrl: '../imgs/Rectangle-223.png',
					link: '/',
				},
			]
		}
	}
}
</script>

<style scoped>

.projetUne {
	background-image: url("../assets/imgs/startup-594091_1920-bannier.png");
	background-size: cover;
	background-repeat: no-repeat;
	background-position: center;
}

.projectTag {
	border-radius: 20px;
	padding: 0.2rem 0.7rem;
	margin: 2rem 2rem;
	height: max-content;
	z-index: 10;

}

.projectTag:first-of-type {
	margin-left: 5% !important;
}

.Inter-école {
	background-color: #005757;
}

.Bachelor_2 {
	background-color: #1F6FBF;
}

.divImgProject {
	position: relative;
	height: 10rem;
}

.imgMockUp {
	width: 55%;
	position: absolute;
	top: 0;
	left: 25%;
}

a.buttonMDS.text-uppercase {
	border: solid #707070 2px;
}
</style>
