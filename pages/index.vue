<template>
  <v-container>
    <test>
      <template v-slot:header>
        <h1>Here might be a page title</h1>
      </template>

      <template v-slot:default>
        <p>A paragraph for the main content.</p>
        <p>And another one.</p>
      </template>

      <template v-slot:footer>
        <p>Here's some contact info</p>
      </template>
    </test>

    <v-container>
      <v-row justify="center" align="center">
        <v-col class="shrink" style="min-width: 220px;">
          <v-text-field v-model="color" hide-details class="ma-0 pa-0" solo disabled style="color: black;">
            <template v-slot:append>
              <v-menu v-model="menu" top nudge-bottom="105" nudge-left="16" :close-on-content-click="false">
                <template v-slot:activator="{ on }">
                  <div :style="swatchStyle" v-on="on" />
                </template>
                <v-card>
                  <v-card-text class="pa-0">
                    <v-color-picker v-model="color" flat />
                  </v-card-text>
                </v-card>
              </v-menu>
            </template>
          </v-text-field>
        </v-col>
      </v-row>
    </v-container>

  </v-container>
</template>

<script>
import test from '@/components/test.vue'

export default {
  components: {
    test
  },
  data() {
    return {
      color: '#1976D2FF',
      menu: false,
    }
  },
  methods: {},
  computed: {
    swatchStyle() {
      const { color } = this
      return {
        backgroundColor: color,
        cursor: 'pointer',
        height: '30px',
        width: '30px',
        borderRadius:'50%',
        transition: 'border-radius 200ms ease-in-out'
      }
    }
  }
}
</script>