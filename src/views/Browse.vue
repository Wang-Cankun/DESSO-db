<template>
  <div class="about">
    <BrowseTable
      :tfbsDetails="tfbsDetails"
      @select-tfbs="setTfbs"
    ></BrowseTable>
    <v-snackbar v-model="snackbar" :left="$vuetify.breakpoint.lgAndUp">
      You have selected TF: {{ selectedTfbs.name }}, Data:
      {{ selectedTfbs.title }}
      <v-btn color="amber" text @click="snackbar = false">
        Close
      </v-btn>
    </v-snackbar>
  </div>
</template>

<script>
import BrowseTable from '@/components/BrowseTable'
//import testBrowse from '@/data/testBrowse.json'
import tfbsDetails from '@/data/tfbs_detail.json'

export default {
  name: 'DashboardPage',
  components: {
    BrowseTable
  },
  data() {
    return {
      tfbsDetails: tfbsDetails,
      selectedTfbs: {
        name: '',
        title: ''
      },
      snackbar: false
    }
  },
  methods: {
    setTfbs(event) {
      this.snackbar = true
      this.selectedTfbs.name = event.name
      this.selectedTfbs.title = event.title
    }
  }
}
</script>

<style lang="scss" scoped></style>
