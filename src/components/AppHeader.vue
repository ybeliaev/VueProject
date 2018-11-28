<template>
  <v-app>

    <v-navigation-drawer
    app
    temporary
    v-model="drawer"
  >
    <v-list >
      <v-list-tile
        v-for="(item, i) in menuItems"
        :key="`menuItems${i}`"
               
      >
        <v-list-tile-action>
          <v-icon>{{ item.icons }}</v-icon>
        </v-list-tile-action>

        <v-list-tile-content>
          <v-list-tile-title>{{ item.title }}</v-list-tile-title>
        </v-list-tile-content>
      </v-list-tile>
    </v-list>
  </v-navigation-drawer>

    <v-toolbar app dark color="primary">
      <v-toolbar-side-icon 
        @click="drawer = !drawer"
        class="hidden-md-and-up"
        ></v-toolbar-side-icon>
      <v-toolbar-title v-text="'Title'"></v-toolbar-title>

      <v-spacer></v-spacer>

      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn flat v-for="(item, i) in menuItems" :key="`menuItems${i}`" :to="item.url">
          {{ item.title }}
        </v-btn>
        
      </v-toolbar-items>
  </v-toolbar>
  
  </v-app>
</template>

<script>
  export default {    
    data() {
      return {
        drawer: false,
        menuItems: [
        {icons: 'accessible', title: 'Login', url: '/login'},
        {icons: 'face', title: 'Registration', url: '/registration'},
        {icons: 'bookmark_border', title: 'Orders', url: '/orders'},
        ]
      }
      
    }
  }
  
 
</script>