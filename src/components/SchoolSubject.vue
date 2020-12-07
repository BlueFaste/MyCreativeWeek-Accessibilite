<template>
	<div class="mx-4 w-25">
		<img alt="" role="presentation" :src="icon" class="subjectIcon">
		<h4 class="ubuntu-B mt-4 mb-3">{{ subject }}</h4>
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
	width: 4.5rem;
	height: 4rem;
}

</style>
