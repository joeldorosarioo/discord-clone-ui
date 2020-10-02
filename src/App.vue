<template>
	<div class="grid">
		<ServerList />
		<ServerName />
		<ChannelList />
		<UserInfo />
	</div>
</template>

<script>
	import ServerList from './components/ServerList';
	import ServerName from './components/ServerName';
	import ChannelList from './components/ChannelList';
	import UserInfo from './components/UserInfo';

	export default {
		components: {
			ServerList,
			ServerName,
			ChannelList,
			UserInfo,
		}
	}
</script>

<style lang="scss" scoped>
	.grid {
		display: grid;
		height: 100vh;

		grid-template-columns: 72px 240px auto 240px;
		grid-template-rows: 48px auto 52px;
		grid-template-areas:
			"server-list server-name channel-info channel-info"
			"server-list channel-list channel-data user-list"
			"server-list user-info channel-data user-list"
		;
	}
</style>
