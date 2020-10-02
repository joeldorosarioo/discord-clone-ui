<template>
	<div class="container">
		<div class="title">Servidor Vue</div>

		<div class="icon-wrapper">
			<ChevronDownIcon size="28" />
		</div>
	</div>
</template>

<script>
	import ChevronDownIcon from 'vue-material-design-icons/ChevronDown';

	export default {
		components: {
			ChevronDownIcon,
		}
	}
</script>

<style lang="scss" scoped>
	.container {
		grid-area: server-name;
		display: flex;
		align-items: center;
		justify-content: space-between;
		background-color: var(--secondary);
		padding-left: 16px;
		padding-right: 11px;
		box-shadow: 0 1px 0 0 rgba(0, 0, 0, .9);
		z-index: 2;
	}

	.title {
		color: var(--white);
		font-size: 16px;
		font-weight: bold;
	}

	.icon-wrapper {
		color: var(--white);
		cursor: pointer;
		margin-top: 4px;
	}
</style>
