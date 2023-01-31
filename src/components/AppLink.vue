<template>
  <a 
  :href="to"
  v-bind="$attrs"
  target="_blank"
  v-if="isExternalLink"
  ><slot/></a>
  <router-link :to="to" v-else><slot/></router-link>
</template>

<script>

import { computed } from "vue";
import { RouterLink } from "vue-router"
export default {
  name: "AppLink",
  props: {
    ...RouterLink.props
  },
  setup (props) {
    const isExternalLink = computed(() => {
      return typeof props.to === "string" && props.to.startsWith("http")
    })

    return {
      isExternalLink
    }
  }
}
</script>

<style scoped>

</style>