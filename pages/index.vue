<template>
	<h1>Agnieszka Stobierska</h1>
	<a href="https://www.instagram.com/agnieszka.stobierska"><svg fill="currentColor" width="1.3em" height="1.3em"
			class="icon" viewBox="0 0 32 32" xmlns="http://www.w3.org/2000/svg">
			<path
				d="M20.445 5h-8.891A6.559 6.559 0 0 0 5 11.554v8.891A6.559 6.559 0 0 0 11.554 27h8.891a6.56 6.56 0 0 0 6.554-6.555v-8.891A6.557 6.557 0 0 0 20.445 5zm4.342 15.445a4.343 4.343 0 0 1-4.342 4.342h-8.891a4.341 4.341 0 0 1-4.341-4.342v-8.891a4.34 4.34 0 0 1 4.341-4.341h8.891a4.342 4.342 0 0 1 4.341 4.341l.001 8.891z" />
			<path
				d="M16 10.312c-3.138 0-5.688 2.551-5.688 5.688s2.551 5.688 5.688 5.688 5.688-2.551 5.688-5.688-2.55-5.688-5.688-5.688zm0 9.163a3.475 3.475 0 1 1-.001-6.95 3.475 3.475 0 0 1 .001 6.95zM21.7 8.991a1.363 1.363 0 1 1-1.364 1.364c0-.752.51-1.364 1.364-1.364z" />
		</svg>@agnieszka.stobierska</a> &bull; <a href="mailto:agnieszka.stobierska@me.com">agnieszka.stobierska@me.com</a>
	<p>Page coming soon</p>
</template>

<script setup>

const { data: main } = reactive(await useAsyncData("about", () =>
	queryContent("/main/about").findOne())
)

</script>

<style lang="scss" scoped>
.icon {
	height: 1.2rem;
	width: auto;
	vertical-align: middle;
}

/* .section {
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
} */
</style>
