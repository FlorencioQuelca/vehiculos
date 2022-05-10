<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          Quasar App
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
          Essential Links
        </q-item-label>
                <q-item
                    clickable
                    tag="a"
                  >
                    <q-item-section
                      v-if="icon"
                      avatar
                    >
                      <q-icon :name="icon" />
                    </q-item-section>

                    <q-item-section>
                      <q-item-label>{{ title }}</q-item-label>
                      <q-item-label caption>{{ caption }}</q-item-label>
                    </q-item-section>
                  </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>

export default {
  data(){
    return {
      leftDrawerOpen:false,
    }
  },
  methods:{
     toggleLeftDrawer () {
        this.leftDrawerOpen.value = !this.leftDrawerOpen.value;
      },

  },
}
</script>
