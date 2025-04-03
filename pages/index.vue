<template>
	<header class="header">
		<div class="header__name">
			<div>
				<h1>{{ main.name }}</h1>
			</div>
			<div>{{ main.title }}</div>
		</div>
		<div class="header__email">{{ main.email }}</div>
		<div class="header__phone">{{ main.phone }}</div>
	</header>

	<div class="landing">
		<div style="background-image: url('/images/main.png')" class="landing__image"></div>
		<MDC :value="main.motivation" />
	</div>

	<main id="main" class="home">
		<h2 class="home__title">Om mig</h2>
		<div class="home__experience">
			<MDC :value="main.experience" />
		</div>
	</main>

</template>

<script setup>

const { data: main } = reactive(await useAsyncData("home", () =>
	queryContent("/main/about").findOne())
)

</script>

<style lang="scss" scoped>
.header {
	@include grid;
	padding: 1rem 0;

	@media screen and (max-width: $breakpoint-md) {
		display: block;
	}
}

.header__phone {
	grid-row: 1;
	grid-column: 1 / span 2;
}

.header__email {
	grid-row: 1;
	grid-column: 3 / span 3;
}

.header__name {
	grid-row: 1;
	grid-column: 6 / span 4;

	h1 {
		font-size: inherit;
	}
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
	font-size: 1.5rem;
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
	left: calc(50vmin - 50vmax + 4rem);
	top: 4rem;
	width: 15em;
	height: 15em;
	mix-blend-mode: screen;
	opacity: .5;
}
</style>
