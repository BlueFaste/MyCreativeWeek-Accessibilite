<template>
	<div class="px-10rem">
		Ici vous pouvez gérer vos projets
		<b-table striped hover :fields="fields" :items="items"></b-table>
	</div>
</template>

<script>
export default {
	name: "ManagementProjects",
	data() {
		return {
			fields: [
				{
					key: 'date',
					label: 'Date'
				},
				{
					key: 'projectName',
					label: 'Nom du projet'
				},
				{
					key: 'promotion',
					label: 'Promotion'
				},
				{
					key: 'school',
					label: 'École'
				},
				{
					key: 'actions',
					label: 'Action'
				},
			],
			items: [
				{
					date: '23/11/2020',
					projectName: 'La 5ème édition de la Créative Week',
					promotion: 'Bachelor 2',
					school: 'Angers',
					actions: '👁 🖍 ❌‍',
				}, {
					date: '23/11/2020',
					projectName: 'La 5ème édition de la Créative Week',
					promotion: 'Bachelor 2',
					school: 'Angers',
					actions: '👁 🖍 ❌‍',
				},
			]
		}
	}
}
</script>

<style scoped>

</style>
