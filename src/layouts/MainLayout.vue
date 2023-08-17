<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          v-if="$route.fullPath.includes('/chat')"
          @click="$router.push('/')"
          icon="arrow_back"
          flat
          label="Back" />
        <q-toolbar-title class="absolute-center">
          {{ title }}
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
export default{
  computed: {
    title () {
     let currentPath = this.$route.fullPath
      if (currentPath === '/') return 'Smart-Chat'
      else if (currentPath === '/chat') return 'Chat'
      else if (currentPath === '/auth') return 'Login'
      else return 'Error'
    }
  }
}
</script>

