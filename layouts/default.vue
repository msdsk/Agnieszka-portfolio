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