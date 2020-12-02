<template>
	<div class="accordion mt-3" role="tablist">
		<b-card no-body class="mb-1" v-for="tempsF in tempsFort" :key="tempsF.key">
			<b-card-header header-tag="header" class="p-1" role="tab">
				<b-button block @click="toogleCollapse(tempsF.id)" variant="light" class="text-capitalize" :id="'button'+ tempsF.id">{{ tempsF.title.toLowerCase() }}
					<span class="toggleLogo"> > </span></b-button>
			</b-card-header>
			<b-collapse :id="tempsF.id" :ref="tempsF.id" visible accordion="my-accordion" role="tabpanel">
				<b-card-body>
					<!--          <b-card-text>I start opened because <code>visible</code> is <code>true</code></b-card-text>-->
					<b-card-text>{{ tempsF.desc }}</b-card-text>
				</b-card-body>
			</b-collapse>
		</b-card>
	</div>
</template>

<script>
export default {
	name: "Collaspe",
	props: {
		tempsFort: Array,
	},
	data() {
		return {}
	},
	methods: {
		toogleCollapse(id) {
			console.log(id)
			this.$root.$emit('bv::toggle::collapse', `${id}`)
		}
	},
	mounted() {

	}
}
</script>

<style scoped>

.toggleLogo {
	position: absolute;
	right: 4%;
	transform: rotate(90deg);
}

</style>
