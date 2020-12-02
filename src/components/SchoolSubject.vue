<template>
	<div class="mx-4">
		<img alt="" role="presentation" :src="icon" class="subjectIcon">
		<p class="ubuntu-B pt-4">{{ subject }}</p>
		<p>{{ desc }}</p>
	</div>
</template>

<script>
export default {
	name: "SchoolSubject",
	props:{
		subject: String,
		desc: String,
		icon: String,
	}
}
</script>

<style scoped>
.subjectIcon{
	width: 5rem;
	height: 5rem;
}

</style>
