<script setup>
  import Header from './components/Header.vue'
  import Statistics from "@/components/statistics/Statistics.vue";
  import GrowthChart from "@/components/growthСhart/GrowthChart.vue";
  import RussianMap from "@/components/RussianMap.vue";
</script>

<template>
  <Header />
	<main>
		<div class="container">
			<h1 class="main-title"><span>Центральная россия — </span>1/3 экономики страны</h1>
		</div>
		<Statistics />
		<div class="main-bottom">
			<div class="container">
				<GrowthChart />
				<RussianMap />
			</div>
		</div>
	</main>
</template>

<style lang="scss" scoped>
	@import "assets/variables";

	main {
		padding: 32px 0 16px;
	}

	.main-bottom {
		margin-top: 50px;
	}

	.main-title {
		margin-bottom: 32px;
	}

	@media (max-width: $screen-md) {
		main {
			padding: 16px 0;
		}

		.main-title {
			margin-bottom: 20px;
		}

		.main-bottom {
			margin-top: 32px;
		}
	}
</style>