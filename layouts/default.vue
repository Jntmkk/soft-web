<template>
    <v-app style="background-color: #bee8c1" light>
        <template>
            <v-card>
                <v-toolbar style="background-color: #d4f0d6"
                >
                    <v-toolbar-title style="padding-left: 160px">WinSoft</v-toolbar-title>
                    <v-toolbar-items v-for="(item,idx) in items"
                                     :key="idx"
                                     style="height: initial;padding-left: inherit">
                        <NuxtLink :to="item.to">
                            {{item.title}}
                        </NuxtLink>
                    </v-toolbar-items>
                    <v-spacer></v-spacer>
                    <v-btn icon>
                        <v-icon>mdi-magnify</v-icon>
                    </v-btn>
                    <v-btn icon>
                        <v-icon>mdi-dots-vertical</v-icon>
                    </v-btn>
                </v-toolbar>
            </v-card>
        </template>
        <v-main class="main">
            <v-container>
                <nuxt/>
            </v-container>
        </v-main>
    </v-app>
</template>

<script>
  export default {
    data () {
      return {
        model: 0,
        colors: [
          'primary',
          'secondary',
          'yellow darken-2',
          'red',
          'orange',
        ],
        clipped: false,
        drawer: false,
        fixed: false,
        items: [
          {
            icon: 'mdi-apps',
            title: '首页',
            to: '/'
          },
          {
            icon: 'mdi-chart-bubble',
            title: '软件',
            to: '/inspire'
          }
        ],
        miniVariant: false,
        right: true,
        rightDrawer: false,
        title: 'Vuetify.js'
      }
    }
  }
</script>
<style lang="scss">
    .main {
        background-color: transparent;
    }
</style>
