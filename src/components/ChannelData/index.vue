<template>
	<div class="channel-data">
		<div class="messages">
			<ChannelMessage author="Joel Oliveira" date="10/10/2020">
				Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil numquam enim nulla consectetur id sit nemo beatae quaerat? Veritatis sed iure cupiditate soluta commodi in eveniet praesentium sint pariatur magni.
			</ChannelMessage>

			<ChannelMessage author="vue-bot" date="10/10/2020" isBot>
				Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quasi delectus dolorum maxime temporibus beatae, in reiciendis enim omnis illum nostrum qui impedit quae repudiandae asperiores explicabo iste adipisci voluptates! Aut!
			</ChannelMessage>

			<ChannelMessage author="Fulano da Silva" date="10/10/2020" hasMention>
				<Mention>Joel Oliveira</Mention>, olha só isso!
			</ChannelMessage>

			<ChannelMessage author="Joel Oliveira" date="10/10/2020" v-for="messages in 2" :key="messages.id">
				Lorem ipsum, dolor sit amet consectetur adipisicing elit. Animi, mollitia! Temporibus sit dolorem quia in quidem! Eos optio, at consectetur aliquid itaque voluptas inventore pariatur fuga quia expedita odio labore?
			</ChannelMessage>

			<ChannelMessage author="Fulano da Silva" date="10/10/2020" hasMention>
				<Mention>Joel Oliveira</Mention>, Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quaerat, minus veniam commodi earum, quasi, vitae fuga illo laudantium dolore aliquid unde. Non maxime deleniti iure ad sint possimus molestias neque!!
			</ChannelMessage>

			<ChannelMessage author="Joel Oliveira" date="10/10/2020" v-for="messages in 2" :key="messages.id">
				Lorem ipsum, dolor sit amet consectetur adipisicing elit. Animi, mollitia! Temporibus sit dolorem quia in quidem! Eos optio, at consectetur aliquid itaque voluptas inventore pariatur fuga quia expedita odio labore?
			</ChannelMessage>

			<ChannelMessage author="vue-bot" date="10/10/2020" isBot>
				Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quasi delectus dolorum maxime temporibus beatae, in reiciendis enim omnis illum nostrum qui impedit quae repudiandae asperiores explicabo iste adipisci voluptates! Aut!
			</ChannelMessage>
		</div>

		<div class="input-wrapper">
			<input type="text" placeholder="Conversar em #chat-livre" />

			<div class="icon">
				<AtIcon :size="24" />
			</div>
		</div>
	</div>
</template>

<script>
	import Vue from 'vue';
	import AtIcon from 'vue-material-design-icons/At';
	import ChannelMessage from "./ChannelMessage";

	export default {
		components: {
			ChannelMessage,
			AtIcon,
		},
	};

	Vue.component('Mention', {
		template: '<span class="mention"><slot /></span>'
	});
</script>

<style lang="scss" scoped>
	.channel-data {
		grid-area: channel-data;

		display: flex;
		flex: 1;
		flex-direction: column;
		justify-content: space-between;

		background-color: var(--primary);
	}

	.messages {
		display: flex;
		flex-direction: column;

		height: calc(100vh - 46px - 68px);
		max-height: calc(100vh - 46px - 68px);

		overflow-y: scroll;

		&::-webkit-scrollbar {
			width: 8px;
		}

		&::-webkit-scrollbar-thumb {
			background-color: var(--tertiary);
			border-radius: 4px;
		}

		.channel-message:first-child {
			margin-top: 0
		}
	}

	.input-wrapper {
		width: 100%;
		padding: 0 16px;
		height: 68px;

		input {
			width: 100%;
			height: 44px;
			padding-right: 10px;
			padding-left: 57px;
			border-radius: 5px;
			color: var(--white);
			background-color: var(--chat-input);
			position: relative;

			&::placeholder {
				color: var(--grey);
			}
		}

		.icon {
			color: var(--grey);
			position: relative;
			top: -50%;
			left: 14px;
			transition: .2s;
			width: 24px;
		}
	}
</style>
