<template>
	<secttion class="landing section">
		<img src="/images/main.png" class="landing__image" />
		<MDC :value="main.motivation" />
	</secttion>

	<main id="main" class="home section">
		<h2 class="home__title">Om mig</h2>
		<div class="home__experience">
			<MDC :value="main.experience" />
		</div>
	</main>
</template>

<script setup>

const { data: main } = reactive(await useAsyncData("about", () =>
	queryContent("/main/about").findOne())
)

</script>

<style lang="scss" scoped>
.section {
	padding: 4rem
}


.home {
	@include grid;
}

.home__title {
	grid-row: 2;
	grid-column: 1/ span 2;
}

.home__experience {
	grid-row: 2;
	grid-column: 3 / span 7;
	display: flex;
	justify-content: center;
	align-items: center;
}

.landing {
	position: relative;
	font-size: 1.2rem;
	background: #000;
	color: #fff;
	min-height: 100vh;
	display: flex;
	align-items: center;
	padding: 2rem;
	box-shadow: -100vh 0 0 #000, 100vh 0 0 #000;
}

.landing__image {
	background: no-repeat center/contain;
	display: flex;
	position: absolute;
	max-width: 30vw;
	left: calc(50vmin - 50vmax + 4rem);
	top: 4rem;
	mix-blend-mode: screen;
}
</style>
