/* eslint-disable */
<template>
  <div id="app">
    <span>图表类型：</span>
    <select name="public-choice" v-model="activeChart">                                        
        <option :value="chart.type" :key="chart.type" v-for="chart in chartList" >{{chart.name}}</option>                                    
    </select>
    <component :is="activeChart"></component>
  </div>
</template>

<script>

import bar from './components/bar.vue';
import pileBar from './components/pileBar.vue';
import lineChart from './components/line.vue';
import stackLine from './components/stackLine.vue';
import pie from './components/pie.vue';
import eMap from './components/eMap.vue';

export default {
  name: 'app',
  components: {
    bar,
    pileBar,
    lineChart,
    stackLine,
    pie,
    eMap
  },
  data() {
    return {
      activeChart: 'bar',
      chartList:[
          {
            type: 'bar',
            name: '基本柱状图'
          },
          {
            type: 'pileBar',
            name: '堆叠柱状图'
          },
          {
            type: 'lineChart',
            name: '折线图'
          },
          {
            type: 'stackLine',
            name: '堆叠区域折线图'
          },
          {
            type: 'pie',
            name: '环形图'
          },
          {
            type: 'eMap',
            name: '地图'
          }
      ],
    };
  }
}
</script>

<style>
#app {  
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(52,45,81,0);
  font-family: "Microsoft YaHei" !important;
}
</style>
