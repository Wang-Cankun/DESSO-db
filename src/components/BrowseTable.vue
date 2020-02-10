<template>
  <v-card>
    <v-card-title>
      Browse all data
      <v-spacer></v-spacer>
      <v-text-field
        v-model="search"
        append-icon="mdi-search"
        label="Search"
        single-line
        hide-details
      ></v-text-field>
    </v-card-title>
    <v-data-table
      :headers="headers"
      :items="tfbsDetails"
      :items-per-page="15"
      class="elevation-1"
      :search="search"
      @click:row="selectRow"
      :multi-sort="true"
    ></v-data-table>
  </v-card>
</template>

<script>
export default {
  name: 'BrowseTable',
  props: {
    tfbsDetails: {
      type: Array,
      required: true
    }
  },
  data: () => ({
    search: '',
    headers: [
      { text: 'Data ID', value: 'id' },
      { text: 'ucsc_accession', value: 'ucsc_accession' },
      { text: 'lab', value: 'lab' },
      { text: 'treatment', value: 'treatment' },
      { text: 'antibody', value: 'antibody' },
      { text: 'control', value: 'control' },
      { text: 'dataversion', value: 'dataversion' },
      { text: 'controlId', value: 'controlId' },
      { text: 'quality', value: 'quality' },
      { text: 'cell_line_id', value: 'cell_line_id' },
      { text: 'factor_id', value: 'factor_id' }
    ]
  }),
  methods: {
    selectRow(event) {
      const tfbs = {
        name: event.antibody,
        title: event.ucsc_accession
      }

      this.$emit('select-tfbs', tfbs)
    }
  }
}
</script>

<style lang="scss" scoped></style>
