<template>
  <v-app dark>
    <v-container fluid>
      <v-row justify="center">
        <v-col cols="6">
          <v-autocomplete
            v-model="select"
            :items="items"
            :search-input.sync="search"
            append-icon="mdi-magnify"
            clearable
            dark
            multiple
            chips
          >
          </v-autocomplete>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      select: null,
      search: null,
      items: [],
    }
  },

  watch: {
    search(value) {
      this.fetchSuggestions(value)
    },
  },

  methods: {
    fetchSuggestions(value) {
      this.items = ['fu', 'fu so hard', 'fu wtf is this shit']
    },
  },
}
</script>
