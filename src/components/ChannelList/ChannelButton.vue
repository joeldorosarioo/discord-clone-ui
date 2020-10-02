<template>
	<div class="channel-button" :class="{ active: selected }">
		<div class="channel-info">
			<HashTagIcon class="hash-icon" :size="20" />

			<div>{{ channelName }}</div>
		</div>

		<div class="channel-actions">
			<InviteIcon class="icon-actions" :size="16" />
			<SettingsIcon class="icon-actions" size="16" />
		</div>
	</div>
</template>

<script>
	import HashTagIcon from 'vue-material-design-icons/Pound';
	import InviteIcon from 'vue-material-design-icons/AccountPlus';
	import SettingsIcon from 'vue-material-design-icons/CogOutline';

	export default {
		components: {
			HashTagIcon,
			InviteIcon,
			SettingsIcon,
		},
		props: {
			channelName: String,
			selected: Boolean,
		}
	}
</script>

<style lang="scss" scoped>
	.channel-button {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
		cursor: pointer;
		padding: 5px 8px;
		background-color: transparent;

		height: 32px;
		border-radius: 4px;
		display: flex;
		flex-direction: row;
		align-items: center;
		transition: ease .2s;

		> div {
			display: flex;
		}

		.channel-info {
			div {
				color: var(--senary);
				margin-left: 5px;
			}

			.hash-icon {
				color: var(--symbol);
			}
		}

		.channel-actions {
			display: none;

			.icon-actions {
				color: var(--symbol);
				margin-left: 4px;
				margin-top: 2px;
				transition: ease .2s;

				&:hover {
					color: var(--white);
				}
			}
		}

		&:hover, &.active {
			background-color: var(--quinary);

			.channel-info {
				div {
					color: var(--white);
				}
			}

			.channel-actions {
				display: flex;
			}
		}
	}
</style>
