<template lang="pug">
    nuxt-link( :to="{ path: to }" )
      .SidebarItem( :class="{ avatar }" )
          .SidebarItem__icon
              i( v-if="icon" :class="[ icon, color ]" )
              v-avatar( v-if="avatar" color="primary" size="36" )
                  img( :src="src" )
          .SidebarItem__text 
            | {{ text }}
            .count( v-if="count" ) {{ count }}

</template>

<script>
export default {
	props: {
		icon: {
			type: String,
			default: null
		},
		text: {
			type: String,
			default: ""
		},
		color: {
			type: String,
			default: null
		},
		src: {
			type: String,
			default: null
		},
		avatar: {
			type: Boolean,
			default: false
		},
		count: {
			type: Number,
			default: null
		},
		to: {
			type: String,
			default: "index"
		}
	}
};
</script>

<style lang="scss" scoped>
.SidebarItem {
	align-items: center;
	border-radius: 8px;
	cursor: pointer;
	padding: 0 0.5em;
	height: 52px;
	transition: 0.2s ease;
	display: grid;
	grid-template-columns: 50px auto;

	&:hover {
		background: #353535;
		transition: 0.1s ease;
	}

	&.avatar &__text {
		color: #dedede;
	}

	&__icon {
		padding: 0 0.5em;
		margin-right: 0.5em;
		justify-self: center;
	}

	&__text {
		font-weight: 500;
		font-size: 15px;
		color: #cfcfcf;
		display: flex;
		justify-content: space-between;
		align-items: center;

		.count {
			font-size: 12px;
			font-weight: 300;
		}

		&--name {
			font-weight: 500;
			font-size: 14px;
		}
	}
}
</style>
