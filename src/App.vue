<template>
  <v-app id="inspire">

<v-navigation-drawer
v-model="drawer"
app
>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title">
            Vuetify To Do
          </v-list-item-title>
          <v-list-item-subtitle>
            This is my awesome to do list
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="item.to"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>


    <v-app-bar
      app
      color=primary
      dark
      src="mountains.jpeg"
      
      prominent
      >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(19,84,122,.5), rgba(128,208,199,.8)"
        ></v-img>
      </template>

      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-app-bar-title>My To Do App</v-app-bar-title>

      <v-spacer></v-spacer>

    </v-app-bar>


    <!-- <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Application</v-toolbar-title>
    </v-app-bar> -->

    <v-main>
      <router-view></router-view>

    </v-main>
  </v-app>
</template>

<script>
  export default {
    data: () => ({ 
      drawer: null,
      items: [
          { title: 'To Do', icon: 'mdi-format-list-checks', to: '/'},
          { title: 'About', icon: 'mdi-help-box', to: '/about'},
        ]
      }),
  }
</script>
