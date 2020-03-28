<template lang="pug"> 
    #Navbar
        .Navbar-section
            .Navbar-section__item.circle.mx-0
                logo.logo
            .Navbar-section__item
                search.px-2
        .Navbar-section.center
            nuxt-link( :to={ name: "index" } ).Navbar-section__item.navigation
                i.fas.fa-home
            nuxt-link( :to={ name: "friends" } ).Navbar-section__item.navigation
                i.fas.fa-user-friends
            nuxt-link( :to={ name: "groups" } ).Navbar-section__item.navigation
                i.fas.fa-layer-group
        .Navbar-section.right
            .Navbar-section__item.circle
                i.fas.fa-plus
            .Navbar-section__item.circle
                i.fas.fa-inbox
            .Navbar-section__item.circle
                i.fas.fa-bell
            .Navbar-section__item.circle
                i.fas.fa-chevron-down
                
</template>

<script>
import Logo from "~/components/Logo";
import Search from "~/components/search/Search";
export default {
	components: {
		Logo,
		Search
	}
};
</script>

<style lang="scss" scoped>
#Navbar {
	position: fixed;
	width: 100%;
	background: #272727;
	height: 60px;
	border-bottom: 1px solid #3f3f3f;
	display: grid;
	grid-template-columns: repeat(3, 1fr);
	justify-content: space-between;
	padding: 0 1em;
	color: #969696;
	z-index: 99;

	.Navbar-section {
		height: inherit;
		display: flex;
		align-items: center;

		&.center {
			justify-content: center;
		}

		&.right {
			justify-content: flex-end;
		}

		&__item {
			height: 100%;
			display: flex;
			align-items: center;

			&.circle {
				width: 40px;
				height: 40px;
				background: #353535;
				justify-content: center;
				border-radius: 90px;
				color: #e2e2e2;
				cursor: pointer;
				transition: 0.15s ease;

				&:not(.no-margin) {
					margin-left: 0.5em;
				}

				&:hover {
					background: #494949;
					transition: none;
				}
			}

			&.navigation {
				cursor: pointer;
				color: #969696;
				font-size: 26px;
				width: 120px;
				justify-content: center;
				height: 80%;
				margin: 0 0.1em;
				border-radius: 10px;
				position: relative;
				// transition: 0.15s ease;

				&::after {
					content: "";
					position: absolute;
					bottom: 0;
					left: 0;
					height: 0;
					width: 100%;
					background: #1778f2;
				}

				&:hover:not(.nuxt-link-exact-active) {
					background: #353535;
					transition: none;
				}

				&.nuxt-link-exact-active {
					height: 100%;
					border-radius: 0;
					color: #1778f2;

					&::after {
						height: 3px;
						transition: 0.3s ease;
					}
				}
			}
		}
	}
}
</style>
