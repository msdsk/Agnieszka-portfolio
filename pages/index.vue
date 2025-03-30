<template>
	<main id="main" class="home">
		{{ main.name }}
	</main>

</template>

<script setup>

const { data: main } = reactive(await useAsyncData("home", () =>
	queryContent("/main/about").findOne())
)

</script>

<style lang="scss" scoped>
main {
	display: grid;
	justify-items: center;
	align-items: center;

	:deep(div) {
		max-width: 50em;
	}

	// assets/scss/mixins
	@include fade-in;
}
</style>
