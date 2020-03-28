<template lang="pug">
    div.PostPlaceholder
        .PostPlaceholder__content
            v-avatar.mr-2( color="primary" size=40 )
                img( src="https://cdn.vuetifyjs.com/images/john.jpg" )
    
            .PostPlaceholder__content--input( @click="modal = true" )
              | What's on your mind, Ben?
        //- hr

        div.PostPlaceholder__overlay( v-if="modal" @click.self="modal = false" )
          div.Placeholder__card
            .Placeholder__card--title Create Post
              i.fas.fa-times.close( @click="modal = false" ) 
            .Placeholder__card--content
              div.user
                v-avatar.mr-2( color="primary" size=40 )
                  img( src="https://cdn.vuetifyjs.com/images/john.jpg" )
                span.name Ben Shachar Heimberg
              div.post-content
                textarea( placeholder="What's on your mind, Ben?" v-model="input" ref="textarea" )
            .Placeholder__card--footer
              button( :class="{ active: input.length }" ) Post

              

</template>

<script>
export default {
	data: () => ({
		modal_status: false,
		input: ""
	}),
	computed: {
		modal: {
			get() {
				return this.modal_status;
			},
			set(value) {
				this.modal_status = value;

				if (value) {
					this.$nextTick(() => {
						this.$refs.textarea.focus();
					});
				}
			}
		}
	}
};
</script>

<style lang="scss" scoped>
.PostPlaceholder {
	background: #202020;
	padding: 0.75em 1em;
	border-radius: 8px;

	&__content {
		display: flex;
		justify-content: space-between;

		&--input {
			width: 100%;
			display: flex;
			background: #353535;
			font-size: 17px;
			display: flex;
			align-items: center;
			padding: 0 1em;
			border-radius: 90px;
			cursor: pointer;
			color: #858585;
			line-height: 0;
			transition: 0.15s ease;

			&:hover {
				background: #424242;
				transition: 0.05s ease;
			}
		}
	}
	&__overlay {
		position: fixed;
		top: 60px;
		left: 0;
		width: 100%;
		height: 100%;
		background: rgba(0, 0, 0, 0.75);
		z-index: 999;
		display: flex;
		justify-content: center;
		align-items: center;

		.Placeholder__card {
			transform: translateY(-110px);
			width: 500px;
			background: #202020;
			border: 1px solid #2b2b2b;
			border-radius: 8px;
			color: #ccc;

			&--title {
				text-align: center;
				font-size: 21px;
				font-weight: 600;
				position: relative;
				padding: 0.75em 0;
				border-bottom: 1px solid #2b2b2b;

				.close {
					position: absolute;
					right: 0.75em;
					top: 50%;
					transform: translateY(-50%);
					width: 35px;
					height: 35px;
					background: #3a3a3a;
					display: flex;
					justify-content: center;
					align-items: center;
					border-radius: 90px;
					font-weight: 600;
					color: #bdbdbd;
					cursor: pointer;
					transition: 0.2s ease;

					&:hover {
						background: #535353;
						transition: none;
					}
				}
			}
			&--content {
				padding: 1em;

				.user {
					margin-bottom: 1em;

					.name {
						font-weight: 500;
						font-size: 15px;
					}
				}

				.post-content {
					textarea {
						width: 100%;
						height: 155px;
						font-size: 24px;
						resize: none;
						color: #ccc;

						&::placeholder {
							font-weight: 400;
							color: #ccc;
						}
					}
				}
			}
			&--footer {
				display: flex;
				justify-content: center;
				padding: 1em;

				button {
					padding: 0.45em 0;
					background: #464646;
					width: 100%;
					border-radius: 6px;
					font-size: 15px;
					font-weight: 500;
					color: #838383;
					cursor: unset;

					&.active {
						cursor: pointer;
						background: #1778f2;
						color: white;

						&:hover {
							background: #3e8ceb;
						}
					}
				}
			}
		}
	}
}
</style>
