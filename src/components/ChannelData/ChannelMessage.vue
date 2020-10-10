<template>
	<div class="channel-message" :class="{ 'has-mention': hasMention }">
		<div class="avatar" :class="{ 'bot-avatar': isBot }"></div>

		<div class="message">
			<div class="user">
				<strong>{{ author }}</strong>

				<span class="bot" v-if="isBot">Bot</span>

				<span class="date">{{ date }}</span>
			</div>

			<div class="body-message">
				<slot />
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		props: {
			author: String,
			date: String,
			hasMention: Boolean,
			isBot: Boolean,
		},
	}
</script>

<style lang="scss" scoped>
	.channel-message {
		display: flex;
		align-items: flex-start;

		margin-top: 3px;
		margin-right: 4px;
		padding: 16px 16px;
		background-color: transparent;
		transition: .3s;

		&:hover {
			background-color: var(--quaternary);
		}

		&.has-mention {
			background-color: var(--mention-message);
			border-left: 2px solid var(--mention-detail);
		}
	}

	.avatar {
		width: 40px;
		height: 40px;
		border-radius: 50%;
		background-color: var(--secondary);
		flex-shrink: 0;

		&.bot-avatar {
			background-color: var(--mention-detail);
		}
	}

	.message {
		display: flex;
		flex-direction: column;
		justify-content: space-between;

		margin-left: 17px;

		.user {
			margin-bottom: 6px;
		}

		strong {
			color: var(--white);
			font-size: 16px;
		}

		.date {
			margin-left: 6px;
			color: var(--grey);
			font-size: 13px;
		}

		.bot {
			margin-left: 9px;
			background-color: var(--discord);
			color: var(--white);
			padding: 4px 5px;
			border-radius: 4px;
			text-transform: uppercase;
			font-size: 11px;
			font-weight: bold;
		}

		.body-message {
			color: var(--white);
			text-align: left;
			font-size: 16px;

			.mention {
				color: var(--link);
				cursor: pointer;

				&:hover {
					text-decoration: underline;
				}
			}
		}
	}
</style>
