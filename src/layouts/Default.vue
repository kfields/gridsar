<template>
  <q-layout view="lHh Lpr lFf">
    <q-header reveal class="bg-white text-black">
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          aria-label="Menu"
        >
          <v-icon name="bars" scale="2"/>
        </q-btn>

        <q-toolbar-title>
        <router-link to="/">
        <q-avatar>
          <img alt src="/logos/logo-circle-normal.svg">
        </q-avatar>
          Gridsar
        </router-link>
        </q-toolbar-title>

      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      bordered
      content-class="bg-grey-2"
    >
      <LeftBar/>
    </q-drawer>

    <q-page-container>
      <!-- <NavBar/>  -->
      <q-page>
      <slot/>
      <FootBar/>
      </q-page>
    </q-page-container>
  </q-layout>
</template>
<script>
import "vue-awesome/icons/bars";
export default {
  name: 'DefaultLayout',
  components: {
  },
  data () {
    return {
      leftDrawerOpen: this.$q.platform.is.desktop
    }
  }
}
</script>
<style>
</style>
