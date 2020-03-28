<template lang="pug">
	#home
		sidebar.sidebar
		div.d-flex.justify-center
			feed.feed
		div.contacts
</template>

<script>
import Feed from "~/components/feed/Feed";
import Sidebar from "~/components/sidebar/Sidebar";
export default {
  components: {
    Feed,
    Sidebar
  }
};
</script>

<style lang="scss" scoped>
#home {
  display: grid;
  // grid-template-columns: 325px auto 300px;
  height: 100%;

  div.feed {
    width: 600px;
  }

  div.sidebar,
  div.contacts {
    padding: 1em 0.5em;
    width: 325px;
    height: 100%;

    &.contacts {
      position: fixed;
      right: 0;
      background: #1a1a1a;
    }

    .feed {
      padding: 0 !important;
    }
  }
}
</style>
