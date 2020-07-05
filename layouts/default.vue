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
            item-text="label"
            item-value="id"
            return-object
            small-chips
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
    select(value) {
      console.log('selected :', value)
    },
  },

  methods: {
    fetchSuggestions(value) {
      this.items = [
        {
          id: 'fu',
          label: 'fu',
        },
        {
          id: 'fu so hard',
          label: 'fu so hard',
        },
        {
          id: 'fu wtf is this shit',
          label: 'fu wtf is this shit',
        },
      ]
    },
  },
}
</script>
