<template lang="pug">
    #sidebar
        item( src="https://cdn.vuetifyjs.com/images/john.jpg" text="Ben Shachar Heimberg" to="BHEIMBERG" avatar )
        item( icon="fas fa-user-friends" text="Friends" color="blue--text text--lighten-1" to="friends" :count="16" )
        item( icon="fas fa-layer-group"  text="Groups"  color="orange--text text--lighten-1" to="groups" :count="1" )
        item( icon="fas fa-bookmark"     text="Saved"   color="green--text text--lighten-1" to="saved" )

        .test
</template>

<script>
import Item from "./item/Item";
export default {
	components: {
		Item
	}
};
</script>

<style lang="scss" scoped>
#sidebar {
	position: fixed;
	width: 100%;
	height: calc(100% - 60px);

	&::-webkit-scrollbar {
		width: 6px;
	}
	&::-webkit-scrollbar-thumb {
		background: white;
	}

	.test {
		height: 1200px;
	}

	//   .SidebarItem {
	//     display: flex;
	//     align-items: center;
	//     border-radius: 8px;
	//     cursor: pointer;
	//     padding: 0 0.5em;
	//     height: 52px;
	//     transition: 0.2s ease;
	//     display: grid;
	//     grid-template-columns: 50px auto;

	//     &:hover {
	//       background: #353535;
	//       transition: 0.1s ease;
	//     }

	//     &__icon {
	//       padding: 0 0.5em;
	//       margin-right: 0.5em;
	//       justify-self: center;
	//     }

	//     &__text {
	//       font-weight: 500;
	//       font-size: 15px;
	//       color: #cfcfcf;

	//       &--main {
	//         color: white;
	//         font-weight: 400;
	//       }
	//     }
	//   }
}
</style>
