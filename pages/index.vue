<template>
    <div style="width: 80%;align-content: center;margin: 0 auto;">
        <v-row justify-content="center">
            <v-col cols="12">
                <template>
                    <v-carousel v-model="model"
                                continuous
                                cycle
                                interval="3000"
                                hide-delimiter-background
                                delimiter-icon="mdi-minus">
                        <v-carousel-item v-for="(color, i) in colors"
                                         :key="color">
                            <v-sheet :color="color"
                                     height="100%"
                                     tile>
                                <v-row
                                    class="fill-height"
                                    align="center"
                                    justify="center">
                                    <div class="display-3">
                                        Slide {{ i + 1 }}
                                    </div>
                                </v-row>
                            </v-sheet>
                        </v-carousel-item>
                    </v-carousel>
                </template>
            </v-col>
        </v-row>
        <v-row justify-content="space-between">
            <v-col v-for="(item,idx) in items"
                   :key="idx">
                <v-btn :class="item.class" height="100px" style="width: inherit;">
                    <v-icon :class="item.icon" class="left-icon">{{item.icon}}</v-icon>
                    {{item.title}}
                </v-btn>
            </v-col>
        </v-row>
        <v-row>
            <v-col cols="2">
                <v-btn style="font-size: x-large;height: 100%" class="transparent"
                       :elevation="0">
                    <v-icon class="left-icon">mdi-blender-software</v-icon>
                    精品软件
                </v-btn>
            </v-col>
            <v-col cols="8">
                <v-btn-toggle class="transparent"
                              v-model="tab"
                              tile
                              color="deep-purple accent-3"
                              group>
                    <v-btn text value="idx" class="transparent"
                           v-for="(tab,idx) in tabs"
                           :key="idx"
                           :value="tab.value">
                        {{tab.title}}
                    </v-btn>
                </v-btn-toggle>
            </v-col>
            <v-col cols="1" align="end">
                <v-btn style="height: 100%" class="transparent" :elevation="0">more</v-btn>
            </v-col>
        </v-row>
    </div>
</template>

<script>
  import Logo from '~/components/Logo.vue'
  import VuetifyLogo from '~/components/VuetifyLogo.vue'
  import Rec from '~/components/Rec'

  export default {
    data () {
      return {
        tab: 'new',
        tabs: [
          {
            title: '新鲜发布',
            value: 'new'
          },
          {
            title: '热门下载',
            value: 'download'
          },
          {
            title: '站长推荐',
            value: 'rec'
          },
          {
            title: '最多评论',
            value: 'comment'
          },
          {
            title: '最高评分',
            value: 'rank'
          }],
        model: 0,
        colors: [
          'primary',
          'secondary',
          'yellow darken-2',
          'red',
          'orange',
        ],
        items: [
          {
            title: '新人必备',
            class: 'light-green darken-1 white--text',
            icon: 'mdi-gift-outline'
          },
          {
            title: '新人必备',
            class: 'cyan lighten-2 white--text',
            icon: 'mdi-google-photos'
          },
          {
            title: '新人必备',
            class: 'purple lighten-2 white--text',
            icon: 'mdi-laptop'
          },
          {
            title: '新人必备',
            class: 'teal lighten-3 white--text',
            icon: 'mdi-more'
          },
        ]
      }
    },
    components: {
      Logo,
      VuetifyLogo
    }
  }
</script>
<style lang="scss">
    .left-icon {
        margin-right: 10px;
    }

    .transparent {
        background-color: transparent;
    }
</style>
