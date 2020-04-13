<template>
  <section class="chart">
    <div class="chart__dropdown">
      <select @change="changeChartType" v-model="selected">
        <option v-for="chart in charts" :key="chart.type" :value="chart.type">
          {{ chart.type }}
        </option>
      </select>
    </div>
    <Chart :options="chartOptions" />
  </section>
</template>

<script>
import {Chart} from 'highcharts-vue'

export default {
  name: 'BaseChart',

  props: {
    type: {
      type: String,
      default: 'line'
    }
  },

  components: {
    Chart
  },

  data: () => ({
    selected: '',
    charts: [
      { type: 'line' },
      { type: 'pie' },
      { type: 'bar' }
    ]
  }),

  computed: {
    chartOptions () {
      return {
        series: [
          {
            type: this.chartType,
            name: 'Point 1',
            color: '#00FF00',
            data: [1,2,3]
          },
          {
            type: this.chartType,
            name: 'Point 2',
            color: '#FF00FF',
            data: [10, 20, 30]
          }
        ]
      }
    },
    chartType: {
      get () {
        return this.type
      },
      set (newType) {
        this.type = newType
      }
    }
  },

  methods: {
    changeChartType () {
      this.chartType = this.selected
    }
  }
}
</script>

<style lang="scss">
.chart {
  border: 1px solid $c-mine-shaft;
  color:$c-mine-shaft;
  min-width: 49vw;
  max-width: 49vw;
  box-sizing: border-box;

  @media only screen and(max-width: 768px) {
    min-width: 100vw;
    max-width: 100vw;
  }
}
</style>