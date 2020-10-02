<template>
	<div class="container">
		<div class="profile">
			<div class="avatar"></div>

			<div class="userdata">
				<strong>Joel Oliveira</strong>
				<span>#2654</span>
			</div>
		</div>

		<div class="user-actions">
			<MicIcon :size="20" />
			<HeadphoneIcon :size="20" />
			<SettingsIcon :size="20" />
		</div>
	</div>
</template>

<script>
	import MicIcon from 'vue-material-design-icons/Microphone';
	import HeadphoneIcon from 'vue-material-design-icons/Headphones';
	import SettingsIcon from 'vue-material-design-icons/CogOutline';

	export default {
		components: {
			MicIcon,
			HeadphoneIcon,
			SettingsIcon,
		},
	}
</script>

<style lang="scss" scoped>
	.container {
		grid-area: user-info;

		display: flex;
		align-items: center;
		flex-direction: row;
		justify-content: space-between;

		padding: 10px;
		background-color: var(--quaternary);
		box-shadow: 0 1px 0 0 rgba(0, 0, 0, .2);
	}

	.profile {
		display: flex;
		align-items: center;
	}

	.avatar {
		width: 32px;
		height: 32px;
		border-radius: 50%;
		background-color: var(--grey);
	}

	.userdata	{
		display: flex;
		flex-direction: column;
		margin-left: 8px;
		font-size: 13px;

		strong {
			display: block;
			color: var(--white);
		}

		span {
			color: var(--grey);
		}
	}

	.user-actions {
		color: var(--grey);

		span {
			cursor: pointer;
			transition: ease .2s;

			&:hover {
				color: var(--white);
			}
		}
	}

</style>
