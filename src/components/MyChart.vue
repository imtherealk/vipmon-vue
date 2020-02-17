<template>
  <highcharts :options="chartOptions"></highcharts>
</template>

<script>
import { Chart } from 'highcharts-vue';

export default {
    name: 'MyChart',
    props: ['chartItems', 'categories'],
    components: {
        Highcharts: Chart
    },
    watch: {
        chartItems: {
            handler: function(newValue) {
                this.chartOptions.series = newValue;
            },
            deep: true
        }
    },
    created: function() {
    },
    data: function() {
        // let vm = this;
        return {
            chartOptions: {
                chart: {
                    type: 'line'
                },
                title: {
                    text: '5 toptalkers'
                },
                legend: {
                    layout: 'vertical',
                    align: 'right',
                    verticalAlign: 'top',
                    x: 0,
                    y: 0,
                    floating: true,
                    borderWidth: 1,
                },
                xAxis: {
                    categories: this.categories,
                },
                yAxis: {
                    title: {
                    text: 'connections per second'
                    }
                },
                tooltip: {
                    shared: true,
                    valueSuffix: 'cps'
                },
                credits: {
                    enabled: false
                },
                series: [],
                plotOptions: {
                    series: {
                        animation: false,
                    }
                },
            }
        }
    }
}
</script>

<style>

</style>