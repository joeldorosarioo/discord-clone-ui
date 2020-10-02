<template>
	<div class="channel-list">
		<div class="category">
			<div>Canais de Texto</div>

			<div class="category-icon">
				<AddCategoryIcon :size="21" />
			</div>
		</div>

		<ChannelButton channelName="javascript-vanilla" />
		<ChannelButton selected channelName="vue-js" />
		<ChannelButton channelName="react-js" />
		<ChannelButton channelName="typescript" />
		<ChannelButton channelName="angular" />
	</div>
</template>

<script>
	import AddCategoryIcon from 'vue-material-design-icons/Plus';
	import ChannelButton from './ChannelButton';

	export default {
		components: {
			AddCategoryIcon,
			ChannelButton,
		}
	}
</script>

<style lang="scss" scoped>
	.channel-list {
		grid-area: channel-list;
		display: flex;
		flex-direction: column;
		padding: 24px 10px 0 16px;
		background-color: var(--secondary);
	}

	.category {
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin-bottom: 6px;
		color: var(--grey);
		font-size: 12px;
		font-weight: bold;
		text-transform: uppercase;

		.category-icon {
			color: var(--symbol);
			cursor: pointer;
			margin-right: 4px;

			&:hover {
				color: var(--white);
			}
		}
	}
</style>
