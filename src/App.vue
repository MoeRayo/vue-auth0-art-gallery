<template>
  <div id="app">
    <navigation></navigation>
    <router-view />
  </div>
</template>

 <script>
  import navigation from "@/components/navigation.vue";


export default {
  name: 'App',
  components: {
    navigation,
  }
}

</script>

