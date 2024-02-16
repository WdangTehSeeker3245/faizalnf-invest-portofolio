<template>
    <div class="row row-cols-sm-1 row-cols-md-2">
      <div class="col">
        <h3 class="text-center">Sector Investment</h3>
        <center>
          <Pie :data="investmentData" :options="investmentOptions" />
        </center>
      </div>
      <div class="col">
        <h3 class="text-center">Sector Shares</h3>
        <center>
          <Pie :data="sharesData" :options="sharesOptions" />
        </center>
      </div>
    </div>
</template>

<script lang="ts">
import { Chart as ChartJS, ArcElement, Tooltip, Legend } from 'chart.js';
import { Pie } from 'vue-chartjs';
ChartJS.register(ArcElement, Tooltip, Legend);
import { InvestmentData, SharesData } from './chartConfig.js';

export default {
name: 'SectorInvestAndShares',
components: {
    Pie
},
data() {
    return {
    sectors: [
        'Retail Trade', 'Banking', 'Healthcare', 'Technology',
        'Raw Materials', 'Industrial Products', 'Food and Drink',
        'Telecommunication', 'Energy'
    ],
    // Sample data for amount invested (in millions)
    investmentData: InvestmentData,
    // Sample data for amount of shares
    sharesData: SharesData,
    }
},
computed: {
    investmentOptions() {
    return {
        responsive: true,
        maintainAspectRatio: false,
    };
    },
    sharesOptions() {
    return {
        responsive: true,
        maintainAspectRatio: false,
    };
    }
}
}
</script>
