<template>
  <div class="base-layout">
    <component :is="layout">
      <slot></slot>
    </component>
  </div>
</template>

<script>
import PrimaryLayout from './PrimaryLayout'
import PublicLayout from './PublicLayout'
import { queryLayout } from '../utils'
import { layouts } from '../utils/config'

export default {
  name: 'BaseLayout',
  components: {
    primary: PrimaryLayout,
    public: PublicLayout
  },
  computed: {
    layout () {
      return queryLayout(layouts, this.$route.name)
    }
  }
}
</script>
