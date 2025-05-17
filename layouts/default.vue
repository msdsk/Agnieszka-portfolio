<template>
	<div class="layout-wrapper" :class="{ '--firstVisitAnimation': firstVisit }">
		<!-- <LayoutInfo /> -->
		<slot />
		<!-- <LayoutFooter /> -->
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
	width: 100%;
	height: 100%;
	background: rgb(232, 215, 200);
	color: rgb(215, 104, 0);
}

body {
	display: flex;
	justify-content: center;
	align-items: center;
}

* {
	color: inherit;
}

h1 {
	font-size: 3rem;
}
</style>
<!-- <style lang="scss" scoped>
.layout-wrapper {
	max-width: 100vh;
	margin: 0 auto;
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
</style> -->