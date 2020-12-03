<template>
	<div class="px-10rem py-5" style="height: 80vh">
		<b-table striped hover :fields="fields" :items="items" head-variant="dark" :sticky-header="true" style="max-height: 70vh !important;" @row-clicked="rowSelected"></b-table>
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
					date: '15/04/2022',
					projectName: 'Motion Design contest',
					promotion: 'Bachelor 3',
					school: 'Angers',
					actions: '👁 🖍 ❌‍',
				}, {
					date: '12/11/2021',
					projectName: 'English Game',
					promotion: 'Bachelor 3',
					school: 'Angers',
					actions: '👁 🖍 ❌‍',
				}, {
					date: '12/03/2021',
					projectName: 'Pitch ton CV',
					promotion: 'Bachelor 2',
					school: 'Angers',
					actions: '👁 🖍 ❌‍',
				}, {
					date: '23/11/2020',
					projectName: 'My Créative Week',
					promotion: 'Bachelor 2',
					school: 'Angers',
					actions: '👁 🖍 ❌‍',
				}, {
					date: '10/10/2020',
					projectName: 'Projets fil rouge',
					promotion: 'Bachelor 2',
					school: 'Angers',
					actions: '👁 🖍 ❌‍',
				},
				{
					date: '02/02/2019',
					projectName: 'My Digital Week',
					promotion: 'Bachelor 1',
					school: 'Angers',
					actions: '👁 🖍 ❌‍',
				}, {
					date: '30/11/2019',
					projectName: 'My Digital Week',
					promotion: 'Bachelor 1',
					school: 'Angers',
					actions: '👁 🖍 ❌‍',
				}, {
					date: '15/11/2019',
					projectName: 'Projets fil rouge',
					promotion: 'Bachelor 1',
					school: 'Angers',
					actions: '👁 🖍 ❌‍',
				},
			]
		}
	},
	methods: {
		rowSelected() {
			this.$router.push('/project')
		}
	}
}
</script>

<style scoped>

</style>
