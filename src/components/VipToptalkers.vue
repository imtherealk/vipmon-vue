<template>
  <v-container fluid>
    <h1>adc</h1>
    <h2>vip toptalkers (cps, last 30min.)</h2>
    <v-btn id="refresh" color="primary" v-on:click="getData">
         Refresh <v-icon>mdi-refresh</v-icon> 
    </v-btn>
    <mychart 
      v-bind:chartItems="chartItems"
      v-bind:categories="categories"></mychart>
    <br>
    <v-divider></v-divider>
    <br>
    <mytable v-bind:headers="headers" v-bind:items="tableItems"></mytable>
  </v-container>
</template>

<script>
  import axios from 'axios';
  import MyChart from './MyChart.vue';
  import MyTable from './MyTable.vue';

  let numToZero = function(num) {
    let result = [];
    for (let idx=-num; idx<=0; idx++) {
      result.push(idx);
    }
    return result;
  }

  export default {
    name: 'VipToptalkers',
    data: function() {
      return {
        headers: this.getHeaders(30),
        vipData: [],
        categories: numToZero(30)
      }
    },
    components: {
      mychart: MyChart,
      mytable: MyTable,
    },
    watch: {
      
    },
    created: function() {
      this.getData();
      
    },
    computed: {
      tableItems: function() {
        let data = this.vipData;
        let newItems = []
        for (let vip of data) {
          let item = {};
          item['vname'] = vip.vname;
          for (let i=0; i<31; i++){
            item['value'.concat(String(i))] = vip.cps_list[i];
          }   
          newItems.push(item);
        }
        return newItems;     
      },
      chartItems: function() {
        let data = this.vipData;
        let newItems = new Array(5)
        let idx = 0;  
        for (let vip of data.slice(0, 5)) {
          let item = {};
          item['name'] = vip.vname;
          item['data'] = [];
          for (let i=30; i>=0; i--){
            item['data'].push(vip.cps_list[i]);
          }   
          newItems[idx] = item;
          idx = idx + 1;
        }            
        return newItems;
      },
    },
    methods: {
      getData: function() {
        let vm = this;
        axios.get('http://127.0.0.1:5000/vips/toptalkers')
          .then(function (response) {
            let data = response.data;
            vm.vipData = data;
          })
          .catch(function (error) {
              console.log(error);
          });
      },
      getHeaders: function(minutes) {
        let result = []
        for (let idx=0; idx<=minutes; idx++) {
          result.push({
            text: String(idx).concat('분전'),
            value: 'value'.concat(String(idx))
          });
        }
        result.push({
          text: 'vname',
          value: 'vname',
        })
        return result;
      } 
    },
  }
</script>

<style>
#refresh {
  margin: 10px;
}
</style>