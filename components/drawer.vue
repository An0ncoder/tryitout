<template>
    <v-navigation-drawer app temporary right :value="$store.state.drawerOpen" color="green" @input="close($event)">
        <v-container>
        <h1>Drawer</h1>
        </v-container>
    </v-navigation-drawer>
</template>

<script>
export default {
    props: {
        open: {
            type: Boolean,
            open: false
        }
    },
    methods: {
        close($event) {
            if (!$event) {
                this.$store.commit('toggleDrawer')
            }
        }
    }
}
</script>