<template>
  <div class="about">
    <v-container fill-height fluid grid-list-xl>
      <v-row>
        <v-col cols="2"> </v-col>
        <v-col cols="8">
          <v-responsive :aspect-ratio="16 / 5">
            <p class="text-center display-4">DESSO database</p>

            <v-text-field
              :label="label"
              :hint="hint"
              :placeholder="placeholder"
              :shaped="shaped"
              :outlined="outlined"
              :rounded="rounded"
              :solo="solo"
              :single-line="singleLine"
              :filled="filled"
              :clearable="clearable"
              :persistent-hint="persistentHint"
              :loading="loading"
              :flat="flat"
              :counter="counterEn ? counter : false"
              :dense="dense"
              prepend-inner-icon="mdi-magnify"
            ></v-text-field>
          </v-responsive>
        </v-col>
      </v-row>
      <v-row>
        <v-col
          v-for="statistic in statistics"
          :key="`${statistic.title}`"
          cols="3"
        >
          <v-spacer></v-spacer>
          <StatisticCard :statistic="statistic" />
        </v-col>

        <v-col v-for="sale in sales" :key="`${sale.title}`" cols="4" md="4">
          <SalesGraph :sale="sale" />
        </v-col>
        <v-col cols="12"> <EventTimeline :timeline="timeline" /> </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import StatisticCard from '@/components/StatisticCard'
import EventTimeline from '@/components/EventTimeline'
import SalesGraph from '@/components/SalesGraph'

import timelineData from '@/data/timeline.json'
import salesData from '@/data/sales.json'
import statisticsData from '@/data/statistics.json'

export default {
  name: 'Home',
  components: {
    EventTimeline,
    SalesGraph,
    StatisticCard
  },
  data() {
    return {
      statistics: statisticsData,
      sales: salesData,
      timeline: timelineData,
      label: 'Search',
      hint: 'Example: ATF3, wgEncodeEH002819, ENCODE Mar 2012 Freeze',
      placeholder: '',
      shaped: false,
      outlined: false,
      rounded: false,
      solo: false,
      singleLine: false,
      filled: false,
      clearable: false,
      persistentHint: true,
      loading: false,
      flat: false,
      counterEn: false,
      counter: 0,
      dense: false
    }
  }
}
</script>

<style scoped>
.v-text-field {
  font-size: 2em;
}
</style>
