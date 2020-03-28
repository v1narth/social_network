<template lang="pug">
	#feed
		PostPlaceholder

		div.FeedList
			.FeedList__item( v-for="(item, index) in items" :key="index" )
				.FeedList__item--title
					.avatar.mr-2
						v-avatar( size="40" )
							img( src="https://cdn.vuetifyjs.com/images/john.jpg" )
					.post-info
						.name {{ item.author.name }}
							span( v-if="item.user" )
								i.fas.fa-caret-right.mx-2
								| {{ item.user.name }}

						.date {{ item.created_at }}
					.options.ml-auto.d-flex.align-center
						i.fas.fa-ellipsis-h.grey--text
				.FeedList__item--content {{ item.content }}
				.FeedList__item--footer
					div.footer__info
						div.d-flex
							div.reactions( v-if="item.reactions" )
								img( src="~/assets/images/icons/like.svg" width="16" )
								span.ml-2 {{ item.reactions.length }}
						div.comments( v-if="item.comments" ) {{ item.comments.length }} Comments

					hr.mt-4.mb-1

					div.footer__actions
						div
							i.far.fa-thumbs-up.mr-2
							| Like
						div 
							i.far.fa-comment-alt.mr-2
							| Comment
						div 
							i.fas.fa-share.mr-2
							| Share
					div.footer__comments
					div.footer__comment

</template>

<script>
import PostPlaceholder from "~/components/post/Placeholder";
export default {
	components: {
		PostPlaceholder
	},
	data: () => ({
		items: [
			{
				id: 1,
				content: "This is a post content",
				author: {
					id: 1,
					name: "Ben Shachar Heimberg"
				},
				user: {
					id: 2,
					name: "Dominik Heimberg"
				},
				comments: [
					{
						id: 2,
						content: "This is comment for post 1",
						user: {
							id: 2,
							name: "Dominik Heimberg"
						}
					}
				],
				reactions: [
					{
						id: 1,
						name: "Testy",
						type: "like"
					}
				],
				created_at: "24 mins"
			},
			{
				id: 1,
				content: "This is a post content",
				author: {
					id: 2,
					name: "Dominik Heimberg"
				},
				user: {
					id: 1,
					name: "Ben Shachar Heimberg"
				},
				comments: [
					{
						id: 2,
						content: "This is comment for post 1",
						user: {
							id: 2,
							name: "Dominik Heimberg"
						}
					}
				],
				created_at: "1 hr"
			},
			{
				id: 1,
				content: "This is a post content",
				author: {
					id: 1,
					name: "Ben Shachar Heimberg"
				},
				comments: [
					{
						id: 2,
						content: "This is comment for post 1",
						user: {
							id: 2,
							name: "Dominik Heimberg"
						}
					}
				],
				created_at: "2 hrs"
			}
		]
	})
};
</script>

<style lang="scss" scoped>
#feed {
	margin-top: 1em;

	.FeedList {
		padding: 1em 0;

		&__item {
			padding: 1em 1em 5px;
			background: #202020;
			border-radius: 8px;
			font-size: 15px;
			margin-bottom: 1em;

			&--title {
				display: flex;
				height: 36px;

				.post-info {
					.name {
						font-weight: 400;
					}
					.date {
						font-weight: 300;
						font-size: 12px;
						color: #ccc;
					}
				}
				.options {
					width: 36px;
					display: flex;
					justify-content: center;
					align-items: center;
					border-radius: 90px;
					cursor: pointer;
					transition: 0.2s ease;

					&:hover {
						background: #353535;
						transition: none;
					}
				}
			}
			&--content {
				padding: 1em 0;
			}
			&--footer {
				color: #ccc;

				.footer__info {
					display: flex;
					justify-content: space-between;

					.reactions {
						display: flex;
						align-self: center;
					}
				}
				.footer__actions {
					display: flex;
					font-weight: 400;

					> div {
						flex: 1 1 auto;
						padding: 0.35em;
						display: flex;
						justify-content: center;
						align-items: center;
						border-radius: 4px;
						cursor: pointer;
						transition: 0.2s ease;

						&:hover {
							background: #353535;
							transition: none;
						}
					}
				}
			}
		}
	}
}
</style>
