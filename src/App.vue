<template>
	<div class="grid">
		<ServerList />
		<ServerName />
		<ChannelList />
		<UserInfo />
		<ChannelInfo />
		<ChannelData />
		<UserList />
	</div>
</template>

<script>
	import ServerList from './components/ServerList';
	import ServerName from './components/ServerName';
	import ChannelList from './components/ChannelList';
	import UserInfo from './components/UserInfo';
	import ChannelInfo from './components/ChannelInfo';
	import ChannelData from './components/ChannelData';
	import UserList from './components/UserList';

	export default {
		components: {
			ServerList,
			ServerName,
			ChannelList,
			UserInfo,
			ChannelInfo,
			ChannelData,
			UserList,
		},
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
