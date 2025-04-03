<template>
	<div class="layout-wrapper" :class="{ '--firstVisitAnimation': firstVisit }">
		<slot />
		<LayoutFooter />
	</div>
</template>

<script setup>

const route = useRoute();
// initiallize 'firstVisit' state => changed via watch 
const firstVisit = useState("firstVisit", () => route.path === '/');

watch(() => route.fullPath,
	() => {
		firstVisit.value = false
	}
)
</script>
<style lang="scss">
html,
body {
	perspective: 10px;
	transform-style: preserve-3d;
}
</style>
<style lang="scss" scoped>
.layout-wrapper {
	max-width: 100vh;
	margin: 0 auto;
	padding: 0 2rem;
}

.layout-wrapper::after {
	content: '';
	display: block;
	width: calc(50vw - 50vh - 2rem);
	height: 100%;
	position: fixed;
	top: 0;
	left: 0;
	background-color: rgba(0, 29, 121, 0.74);
}
</style>