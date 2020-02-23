<template>
<v-container>
<v-btn @click="toggleDrawer()">Open drawer</v-btn>
<v-btn@click="debuglog(open)">Open value?</v-btn>
  <Drawer :open=$store.state.drawerOpen @close="$store.commit('toggleDrawer')"/>
</v-container>
</template>

<script>
import { mapMutations } from 'vuex'
import Drawer from '@/components/drawer.vue'

export default {
  components: {
    Drawer
  },
  data: () => ({
    open: false
  }),

  methods: {
    ...mapMutations(['toggleDrawer']),
    debuglog() {
      alert(this.open)
    }
  }
}
</script>
