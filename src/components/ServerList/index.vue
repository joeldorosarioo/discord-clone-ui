<template>
	<div class="container">
		<ServerButton isHome />
		<div class="separator"></div>

		<ServerButton hasNotification :mentions="3" />
		<ServerButton hasNotification />
		<ServerButton />
		<ServerButton />
		<ServerButton hasNotification :mentions="32" />
		<ServerButton />
		<ServerButton hasNotification />

		<ServerButton isSearchServer />
		<ServerButton isExplore />
		<ServerButton isDownload />
	</div>
</template>

<script>
	import ServerButton from './ServerButton';

	export default {
		components: {
			ServerButton,
		}
	}
</script>

<style lang="scss" scoped>
	.container {
		grid-area: server-list;
		display: flex;
		flex-direction: column;
		align-items: center;

		background-color: var(--tertiary);
		padding-top: 11px;
		padding-bottom: 11px;
		max-height: 100vh;

		overflow-y: scroll;

		&::-webkit-scrollbar {
			display: none;
		}
	}

	.separator {
		width: 30px;

		margin-bottom: 8px;
		border-bottom: 2px solid var(--quaternary);
	}
</style>
