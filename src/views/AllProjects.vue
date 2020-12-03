<template>
  <div>
<article class=" mt-4 d-flex flex-wrap justify-content-center">
						<ProjectDiplay v-for="project in projects" :key="project.key" :projet-title="project.title"  :img-url="project.img"  :ecole="project.tagSchool" :formation="project.tagLevel" :link="project.link" :filter-black="project.blackFilter"></ProjectDiplay>

						<router-link role="button" to="/" title="Tous les projets" class="buttonMDS my-4 bg-white text-dark text-uppercase ubuntu-B py-2 px-3">Tous les projets</router-link>
					</article>

  </div>
</template>

<script>
import ProjectDiplay from "@/components/ProjectDisplay";
export default {
  name: "AllProjects",
  components:{
    ProjectDisplay
  },
  data(){
    return{
      projects: [
				{
					title: 'La 5ème édition de la connected week',
					tagSchool: 'Inter-école',
					tagLevel: 'Bachelor_2',
					img: '../imgs/workplace-1245776_1920.png',
					link:'/',
          blackFilter: true,
				},
				{
					title: 'Le Motion Design Contest',
					tagSchool: 'Angers',
					tagLevel: 'B3_Webdesign',
					img: '../imgs/office-620817_1920.png',
					link:'/',
          blackFilter: false,
				},
				{
					title: 'Le concours d’infographie',
					tagSchool: 'Lyon',
					tagLevel: 'MBA_UX-UI_design',
					img: '../imgs/startup-1.png',
					link:'/',
          blackFilter: true,
				},
				{
					title: 'Le projet Fil Rouge à l’honneur cette année',
					tagSchool: 'Grenoble',
					tagLevel: 'Bachelor_1',
					img: '../imgs/startup-594090_1920.png',
					link:'/',
          blackFilter: false,
				},
				{
					title: 'Le challenge Portfolio',
					tagSchool: 'Lille',
					tagLevel: 'B3_Webmarketing',
					img: '../imgs/pexels-serpstat-572056.png',
					link:'/',
          blackFilter: true,
				},
				{
					title: 'English game : un projet d’une semaine',
					tagSchool: 'Bordeaux',
					tagLevel: 'B3_Webmarketing',
					img: '../imgs/startup-594091_1920.png',
					link:'/',
          blackFilter: false,
				},
				{
					title: 'My Digital Strat-up',
					tagSchool: 'Nantes',
					tagLevel: 'Bachelor_2',
					img: '../imgs/pexels-marc-mueller-380769.png',
					link:'/',
          blackFilter: true,
				},
				{
					title: 'Pitch ton CV : Le nouveau challenge des B2',
          tagSchool: 'Montpellier',
          tagLevel: 'MBA_Marketing_Digital',
					img: '../imgs/pexels-vlada-karpovich-4050320.png',
					link:'/',
          blackFilter: false,
				},
				{
					title: 'My Digital Week Édition 2020',
          tagSchool: 'Paris',
          tagLevel: 'Bachelor_1',
					img: '../imgs/pexels-lukas-574071.png',
					link:'/',
          blackFilter: true,
				},
			],
    }
  }
}
</script>

<style scoped>

</style>
