<script setup>
	import { onMounted, ref } from "vue";
	import { StatisticsData } from "@/components/statistics/statistics.data";

	const data = ref([]);

	onMounted(() => {
		data.value = StatisticsData;
	});
</script>

<template>
	<div class="container">
		<div class="statistics">
			<div v-for="statistics in data" :key="statistics.id" class="statistics__part">
				<h2 class="statistics__title">{{ statistics.title }}</h2>
				<ul class="statistics__list">
					<li v-for="(item, i) in statistics.data" :key="i" class="statistics__item">
						<p class="statistics__percent">
							{{ item.percent }}
						</p>
						<p class="statistics__meaning">
							{{ item.meaning }}
						</p>
					</li>
				</ul>
			</div>
		</div>
	</div>
</template>

<style lang="scss" scoped>
	@import "src/assets/variables";

.statistics {
	 display: flex;
	 align-items: flex-start;
	 justify-content: space-between;

	 &__part {
		 padding: 0 5px;
		 width: 100%;
		 max-width: 355px;
	 }

	 &__title {
		 margin-bottom: 12px;
	 }

	 &__item {
		 display: flex;
		 align-items: flex-start;

		 > p {
			 line-height: 24px;
		 }

		 + .statistics__item {
			 margin-top: 12px;
		 }
	 }

	 &__percent {
		 margin-right: 14px;

		 font-weight: 700;
		 color: $black;
	 }

	 @media (max-width: $screen-md) {
		 &__part {
			 max-width: 270px;
		 }
	 }

	 @media (max-width: $screen-sd) {
		 flex-direction: column;

		 &__part {
			 padding: 0;
			 max-width: 100%;

			 + .statistics__part {
				 margin-top: 32px;
			 }
		 }
	 }
}
</style>