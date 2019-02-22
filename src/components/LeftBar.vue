<template>
    <q-list>
      <q-item to="/about">
        <q-item-section avatar>
          <v-icon name="info-circle" scale="2"/>
        </q-item-section>
        <q-item-section>
          <q-item-label>About</q-item-label>
        </q-item-section>
      </q-item>
      <q-item to="/contact">
        <q-item-section avatar>
          <v-icon name="envelope" scale="2"/>
        </q-item-section>
        <q-item-section>
          <q-item-label>Contact</q-item-label>
        </q-item-section>
      </q-item>
      <q-item clickable tag="a" target="_blank" href="https://github.com/kfields/gridsar/issues">
        <q-item-section avatar>
          <v-icon name="exclamation-circle" scale="2"/>
        </q-item-section>
        <q-item-section>
          <q-item-label>Report an issue</q-item-label>
        </q-item-section>
      </q-item>
      <q-item clickable tag="a" target="_blank" href="https://github.com/kfields/gridsar">
        <q-item-section avatar>
          <v-icon name="brands/github" scale="2"/>
        </q-item-section>
        <q-item-section>
          <q-item-label>Github</q-item-label>
        </q-item-section>
      </q-item>
    </q-list>
</template>
<script>
import "vue-awesome/icons/info-circle";
import "vue-awesome/icons/envelope";
import "vue-awesome/icons/brands/github";
import "vue-awesome/icons/exclamation-circle";

export default {
  name: 'LeftBar',
  components: {
  },
  data () {
    return {
    }
  }
}
</script>
<style>
</style>
