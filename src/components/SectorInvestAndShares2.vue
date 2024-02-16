<template>
  <div class="row row-cols-sm-1 row-cols-md-2 mt-5"> 
    <div class="col">
      <h2 class="text-center">Amount Invested by Sector</h2>
      <GChart
        type="PieChart"
        :data="investedData"
        :options="investedOptions"
      />
    </div>
    <div class="col">
      <h2 class="text-center">Amount of Shares by Sector</h2>
      <GChart
        type="PieChart"
        :data="sharesData"
        :options="sharesOptions"
      />
    </div>
  </div>
</template>

<script>
import { GChart } from 'vue-google-charts'

export default {
  components: {
    GChart
  },
  data() {
    return {
      investedData: [
        ['Sector', 'Amount Invested'],
        ['Retail Trade', 100000],
        ['Banking', 65000],
        ['Healthcare', 95000],
        ['Technology', 130000],
        ['Raw Materials', 40000],
        ['Industrial Products', 10000],
        ['Food and Drink', 10000],
        ['Telecommunication', 10000],
        ['Energy', 5000]
      ],
      investedOptions: {
        title: 'Amount Invested by Sector'
      },
      sharesData: [
        ['Sector', 'Amount of Shares'],
        ['Retail Trade', 100],
        ['Banking', 100],
        ['Healthcare', 300],
        ['Technology', 800],
        ['Raw Materials', 300],
        ['Industrial Products', 100],
        ['Food and Drink', 200],
        ['Telecommunication', 200],
        ['Energy', 100]
      ],
      sharesOptions: {
        title: 'Amount of Shares by Sector'
      }
    }
  }
}
</script>