<template>
	<div class="px-10rem py-5" style="height: 80vh">
    <Title title="Gestion des projets" color="blue" id="introductionProject"></Title>
		<b-table :responsive="true" striped hover :fields="fields" :items="items" head-variant="dark" :sticky-header="true" style="max-height: 70vh !important;" @row-clicked="rowSelected" selectable></b-table>
	</div>
</template>

<script>
import Title from "@/components/Title";
export default {
	name: "ManagementProjects",
  components: {Title},
  data() {
		return {
			fields: [
				{
					key: 'date',
					label: 'Date',
          // sortable: true,
          headerTitle : 'Date',
          isRowHeader: true,
				},
				{
					key: 'projectName',
					label: 'Nom du projet',
          // sortable: true,
          headerTitle : 'Nom du projet',
          isRowHeader: true,
        },
				{
					key: 'promotion',
					label: 'Promotion',
          // sortable: true,
          headerTitle : 'Promotion',
          isRowHeader: true,

        },
				{
					key: 'school',
					label: 'École',
          // sortable: true,
          headerTitle : 'École',
          isRowHeader: true,

        },
				{
					key: 'actions',
					label: 'Action',
          headerTitle : 'Action',
          isRowHeader: true,

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
