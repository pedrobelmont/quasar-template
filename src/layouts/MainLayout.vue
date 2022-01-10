<template>
  <q-layout view="lHr lpR lFr">

    <q-header class="bg-accent text-grey-13">
      <q-toolbar class="q-mx-ls">
        <q-toolbar-title>
          <img src="~assets/fugete.png"
           style="height: 28px; max-width: 38px">
          Company name
        </q-toolbar-title>
        <q-space />
        <q-tabs v-model="tab" 
        active-color="warning"
        indicator-color="transparent"
        inline-label>
          <q-tab name="Homepage" label="Homepage" />
          <q-tab name="Category 1" label="Category 1" />
          <q-tab name="Category 2" label="Category 2" />
          <q-tab icon="favorite_border" name="wishlist" label="wishlist"/>
          <q-tab  icon="shopping_basket"  label="shopping cart">
            <q-badge v-if="contagem>0" color="red" floating>{{contagem}}</q-badge>
          </q-tab>
      </q-tabs>
      </q-toolbar>
      <q-toolbar class='bg-grey-7 text-accent '>
        <div class="window-width row justify-center"> only $45.60 awat from free shipping</div>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer elevated class="bg-grey-8 text-white">
     
    </q-footer>

  </q-layout>
</template>
<script>
import { ref } from 'vue'
export default {
  setup () {
    return {
      tab: ref('')
    }
  }
}
</script>