<script setup>
	import { onMounted, ref } from "vue";
	import { GrowthChartData, GrowthChartHeaderData } from "@/components/growthСhart/growthChart.data";

	const headersData = ref([]);
	const data = ref([]);

	onMounted(() => {
		headersData.value = GrowthChartHeaderData;
		data.value = GrowthChartData;
	});
</script>

<template>
	<div class="growth-chart-table">
		<div class="growth-chart-table__row">
			<p v-for="header in headersData" :key="header.id" class="growth-chart-table__header">
				{{ header.title }}
			</p>
		</div>
		<div v-for="growthChart in data" :key="growthChart.id" class="growth-chart-table__row">
			<p class="growth-chart-table__body">
				<img :src="growthChart.img" :alt="growthChart.img" />
				<span>{{ growthChart.title }}</span>
			</p>
			<p class="growth-chart-table__body">
				{{ growthChart.centralPercent }}
			</p>
			<p class="growth-chart-table__body">
				{{ growthChart.totalPercent }}
			</p>
		</div>
	</div>
</template>

<style lang="scss" scoped>
	@import "src/assets/variables";

	$left-indent: 34px;

	.growth-chart-table {
		margin-left: -$left-indent;
		padding: 18px 18px 24px $left-indent;
		width: 100%;
		max-width: 512px;

		background-color: $grey;

		@media (max-width: $screen-md) {
			max-width: 470px;
		}
		
		@media (max-width: 860px) {
			display: none;
		}

		&__body {
			display: flex;
			align-items: center;

			img {
				margin-right: 8px;
			}
		}

		&__header {
			color: $ruby;
			font-size: 12px;

			&:first-child {
				font-size: 18px;
				text-align: left;
				font-weight: 700;
				line-height: 24px;
			}

			&:not(:first-child) {
				text-align: center;
			}

			&:last-child {
				color: $light-blue;
			}
		}

		&__row {
			display: flex;
			align-items: center;

			&:first-child {
				margin-bottom: 20px;
			}

			> p {
				width: 100%;
				max-width: 90px;
			}

			> p:first-child {
				width: 100%;
				max-width: 290px;
				color: $black;

				@media (max-width: $screen-md) {
					max-width: 240px;
				}
			}

			> p:nth-child(2) {
				color: $ruby;
			}

			&:not(:first-child) {
				> p:not(:first-child) {
					justify-content: flex-end;
					font-weight: 700;
				}
			}

			+ .growth-chart-table__row {
				margin-top: 6px;
			}
		}
	}
</style>