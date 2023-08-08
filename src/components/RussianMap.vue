<template>
	<img src="../assets/images/russian-map.svg" class="russian-map" alt="Карта России" />
</template>

<style lang="scss" scoped>
	@import "src/assets/variables";

	.russian-map {
		position: absolute;
		top: 50%;
		right: 0;

		width: 100%;
		max-width: 406px;

		transform: translateY(-50%);

		@media (max-width: $screen-md) {
			max-width: 355px;
		}

		@media (max-width: 860px) {
			position: initial;
			transform: initial;
			display: block;
			margin: 0 auto;
		}
	}
</style>