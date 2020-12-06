<template>
	<form class="d-flex flex-column align-items-start my-5" method="post" action="">
		<div class="d-flex flex-column align-items-start pb-5 px-10rem">
			<p class="py-2">Tous les champs comportant une (<span class="pink">*</span>) sont obligatoires </p>
			<Title title="Introduction du projet" color="blue" id="introductionProject"></Title>
			<div style="padding: 0 7rem" class="d-flex flex-column align-items-start">
				<label class="py-2" for="school">Précisez votre école<span class="pink">*</span> (format: 3 premières lettres de
					l’école):
					<select id="school" name="Ecole" class="mx-2" required>
						<option value="Angers" title="Angers">ANG</option>
						<option value="Annecy" title="Annecy">ANN</option>
						<option value="Bordeaux" title="Bordeaux">BOR</option>
						<option value="Caen" title="Caen">CAE</option>
						<option value="Grenoble" title="Grenoble">GRE</option>
						<option value="Lille" title="Lille">LIL</option>
						<option value="Lyon" title="Lyon">LYO</option>
						<option value="Melun" title="Melun">MEL</option>
						<option value="Montpellier" title="Montpellier">MON</option>
						<option value="Nantes" title="Nantes">NAN</option>
						<option value="Nice" title="Nice">NIC</option>
						<option value="Paris" title="Paris">PAR</option>
						<option value="Rennes" title="Rennes">REN</option>
						<option value="Saint Quentin en Yvelines" title="Saint Quentin en Yvelines">SAI</option>
						<option value="Toulouse" title="Toulouse">TOU</option>
						<option value="Vannes" title="Vannes">VAN</option>
					</select>
				</label>
				<label class="py-2" for="promo">Précisez votre promotion<span class="pink">*</span> :
					<select id="promo" name="Promotion" class="mx-2" required>
            <option value="B1" title="Bachelor 1">B1</option>
            <option value="B2" title="Bachelor 2">B2</option>
            <option value="B3 - E-BUSINESS" title="Bachelor 3 - E-BUSINESS">B3 - E-BUSINESS</option>
            <option value="B3 - WEBMARKETING ET SOCIAL MEDIA" title="Bachelor 3 - WEBMARKETING ET SOCIAL MEDIA">B3 - WEBMARKETING ET SOCIAL MEDIA</option>
            <option value="B3 - WEBDESIGN" title="Bachelor 3 - WEBDESIGN">B3 - WEBDESIGN</option>
            <option value="B3 - DEVELOPPEUR WEB" title="Bachelor 3 - DEVELOPPEUR WEB">B3 - DEVELOPPEUR WEB</option>
            <option value="MBA EXPERT DATA MARKETING" title="Master EXPERT DATA MARKETING">MBA EXPERT DATA MARKETING</option>
            <option value="MBA MARKETING DIGITAL" title="Master MARKETING DIGITAL">MBA MARKETING DIGITAL</option>
            <option value="MBA MANAGEMENT DE L'INNOVATION DIGITAL" title="Master MANAGEMENT DE L'INNOVATION DIGITAL">MBA MANAGEMENT DE L'INNOVATION DIGITAL</option>
            <option value="MBA UX/UI DESIGN" title="Master UX/UI DESIGN">MBA UX/UI DESIGN</option>
            <option value="MBA FULLSTACK" title="Master FULLSTACK">MBA FULLSTACK</option>
					</select>
				</label>
				<label class="py-2" for="year">Précisez l'année votre promotion<span class="pink">*</span> (format: YYYY) :
					<input id="year" type="text" minlength="4" maxlength="4" size="4" required></label>
				<label class="py-2" for="date">Date du projet<span class="pink">*</span> :
					<input type="date" id="date" required>
				</label>
				<label class="py-2" for="projectName">Donnez un nom à votre projet<span class="pink">*</span> :
					<input type="text" id="projectName" required>
				</label>
			</div>
		</div>
		<div class="d-flex flex-column align-items-start py-5 bg-grey px-10rem">
			<Title title="Le projet" color="yellow" id="addProjectTitle"></Title>
			<div style="padding: 0 7rem" class="d-flex flex-column align-items-start">
				<label for="projectDesc">Description du projet<span class="pink">*</span> :</label>
				<textarea id="projectDesc" name="projectDescription" rows="10" cols="105"
									placeholder="Ajouter une description..." class="mb-4" required></textarea>
			</div>
		</div>

		<div class="d-flex flex-column align-items-start py-5 px-10rem">
			<Title title="Les réalisations" color="pink" id="addProjectRealisation"></Title>
			<div style="padding: 0 7rem">
				<div role="group" aria-label="Importez les éléments de votre projet" class="d-flex flex-column align-items-start">
					<legend class="filtre">Importez les éléments de votre projet<span class="pink">*</span> (format: .jpg, .pdf,
						.png):
					</legend>
					<div class="d-flex justify-content-center align-items-center">
						<label for="projectImg" class="labelImg d-flex flex-column align-items-center justify-content-center">
							<div class="cross d-flex justify-content-center align-items-center my-4">
								<span class="spanCross"></span>
								<span class="spanCross"></span>
							</div>
							<p class="text-white mt-5">(cliquez ou glissez votre fichier ici)</p>
							<input type="file" id="projectImg" class="position-absolute inputImg" @change="recupNameFile" required>
						</label>
						<b-button class="crossAddImg d-flex justify-content-center align-items-center ml-5" role="button" aria-label="Ajouter une image">
							<span class="spanCrossAddImg"></span>
							<span class="spanCrossAddImg"></span>
						</b-button>
					</div>
					<p class="d-flex justify-content-center align-items-center"><img alt="Fichier upload" src="../../../public/icons/file.png">{{ imgProjectName }}</p>
					<label for="titleImgProject">Titre de l'élément<span class="pink">*</span> :</label>
					<input type="text" id="titleImgProject" placeholder="Ex: Conception d'un logo" required>
				</div>
			</div>

		</div>
		<b-button class="buttonMDS align-self-center ubuntu-B blackMDS" type="submit" >Publier
		</b-button>

	</form>
</template>

<script>
import Title from "@/components/Title";

export default {
	name: "AddProject",
	components: {Title},
	data() {
		return {
			imgProjectName: "",
		}
	},
	methods: {
		recupNameFile(file) {
			const files = file.target.files || file.dataTransfer.files;
			if (!files.length)
				return;
			// console.log(files[0]);
			this.imgProjectName = files[0].name
		},
		postForm() {
			this.$router.push('/')
		}
	}
}
</script>

<style scoped>

.pink {
	color: #F74D9D;
}

input {
	border: solid #7A7A7A 1px;
}

.bg-grey {
	background-color: #F4F4F4;
	width: 100%;
}

.labelImg, .inputImg {
	width: 20rem;
	height: 20rem;
}

.labelImg {
	background-color: #707070;
}

.inputImg {
opacity: 0;
}

.cross, .crossAddImg {
	position: relative;
}

.spanCross:first-of-type, .spanCrossAddImg:first-of-type {
	transform: rotate(90deg);
}

.spanCross {
	background-color: white;
	display: block;
	height: 5rem;
	width: 0.5rem;
	position: absolute;
}

.crossAddImg {
	border: solid #707070 2px;
	width: 4rem;
	height: 4rem;
	border-radius: 100px;
  background-color: transparent;
}

.spanCrossAddImg {
	background-color: #707070;
	position: absolute;
	display: block;
	height: 1.5rem;
	width: 0.2rem;
}

</style>
