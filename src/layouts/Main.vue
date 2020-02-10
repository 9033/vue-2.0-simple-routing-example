<template>
  <div class="container">
    <ul>
      <li>
        <v-link href="/">Home</v-link>
      </li>
      <li v-for="(route, index) in Route" v-if="0!=route.indexOf('Home')" v-bind:key="index" >
        <!-- <v-link v-bind:href="'/'+route.toLowerCase()"> -->
        <v-link v-bind:href="index">
          {{ route }}
        </v-link>
      </li>
    </ul>
    <slot></slot>
  </div>
</template>

<script>
  import VLink from '../components/VLink.vue'

  import Route from '../routes'

  export default {
    data (){
      return {
        Route,
      }
    },
    components: {
      VLink
    }
  }
</script>

<style scoped>
  .container {
    max-width: 600px;
    margin: 0 auto;
    padding: 15px 30px;
    background: #f9f7f5;
  }
</style>
