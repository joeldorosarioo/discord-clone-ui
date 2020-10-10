<template>
	<div class="user-list">
		<div class="role">Disponível - 1</div>
		<User nickname="Joel Oliveira" />

		<div class="role">Bots - 1</div>
		<User nickname="vue-bot" isBot />

		<div class="role">Offline - 18</div>

		<!-- <User nickname="Fulano da Silva de Almeida" /> -->
		<User nickname="Fulano da Silva" v-for="users in 18" :key="users.id" />

	</div>
</template>

<script>
	import User from './User';

	export default {
		components: {
			User,
		},
	}
</script>

<style lang="scss" scoped>
	.user-list {
		grid-area: user-list;

		display: flex;
		flex-direction: column;

		padding: 3px 6px 10px 16px;
		background-color: var(--secondary);
		max-height: calc(100vh - 46px);
		overflow-y: scroll;

		&::-webkit-scrollbar {
			width: 8px;
		}

		&::-webkit-scrollbar-thumb {
			background-color: var(--tertiary);
			border-radius: 4px;
		}
	}

	.role {
		margin-top: 20px;
		color: var(--grey);
		font-weight: 500;
		font-size: 13px;
		text-transform: uppercase;
	}
</style>
