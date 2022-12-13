<template>
	<div>home</div>
	<div v-for="item in listData">{{ item.name }}</div>
</template>

<script setup>
	const { data } = await useAsyncData("ssr", () =>
		$fetch("https://mock.apifox.cn/m1/2077110-0-default/api/nuxt3/fetch")
	);
	const listData = data.value.data;
	console.log(listData);
</script>

<style scoped></style>
