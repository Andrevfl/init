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
      <q-list
      to="/"
      exact
      clickable
      v-ripple
      >
        <q-item-label
          header
        >
          Essential Links
        </q-item-label>

        <q-item
        to="/formProduto"
        exact
        clickable
        v-ripple
        
        >
          <q-item-section avatar>
            <q-icon name="description" />
          </q-item-section>
          <q-item-section
          >
          Cadastro de Produto
          </q-item-section>
        </q-item>

        <q-item
        to="/formProduto"
        exact
        clickable
        v-ripple
        
        >
          <q-item-section avatar>
            <q-icon name="shopping_cart" />
          </q-item-section>
          <q-item-section
          >
            Caixa
          </q-item-section>
        </q-item>

        <q-item
        to="/formProduto"
        exact
        clickable
        v-ripple
        
        >
          <q-item-section avatar>
            <q-icon name="attach_money" />
          </q-item-section>
          <q-item-section
          >
            Financeiro
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
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'



export default defineComponent({
  name: 'MainLayout',

  components: {
 
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
   
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
