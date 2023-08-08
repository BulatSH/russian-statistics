<template>
	<header>
		<div class="container">
			<a href="">
				<img src="../assets/icons/logo.svg" alt="Логотип" />
			</a>
			<button class="menu">
				<img src="../assets/icons/menu.svg" alt="Логотип" />
			</button>
		</div>
	</header>
</template>
<style lang="scss" scoped>
	header {
		padding: 16px 0;

		box-shadow: 0 0 1px rgba(9, 30, 66, 0.31), 0 4px 8px rgba(9, 30, 66, 0.25);

		.container {
			display: flex;
			align-items: center;
			justify-content: space-between;
		}

		.menu {
			padding: 0;
			width: 24px;
			height: 24px;

			border: none;
			background: transparent;
			cursor: pointer;

			img {
				width: 100%;
				height: 100%;
			}
		}
	}
</style>