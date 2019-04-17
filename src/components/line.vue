<template>
    <div class="chart" id="main" ref="chart">
        line
    </div>
</template>

<script>
import * as echarts from 'echarts';
import lineData from '../mockData/line.js';
export default {
    // 折线图
    name: 'lineChart',
    data() {
        return {

        };
    },
    mounted() {
        let chart = echarts.init(this.$refs.chart);
        let option = {
            title: {
                text: 'Beijing AQI'
            },
            tooltip: {
                trigger: 'axis'
            },
            xAxis: {
                data: lineData.map(function (item) {
                    return item[0];
                })
            },
            yAxis: {
                splitLine: {
                    show: false
                }
            },
            toolbox: {
                left: 'center',
                feature: {
                    restore: {},
                    saveAsImage: {}
                }
            },
            dataZoom: [{
                startValue: '2014-06-01'
            }, {
                type: 'inside'
            }],
            visualMap: {
                pieces: [{
                    gt: 0,
                    lte: 50,
                    color: '#096'
                }, {
                    gt: 50,
                    lte: 100,
                    color: '#ffde33'
                }, {
                    gt: 100,
                    lte: 150,
                    color: '#ff9933'
                }, {
                    gt: 150,
                    lte: 200,
                    color: '#cc0033'
                }, {
                    gt: 200,
                    lte: 300,
                    color: '#660099'
                }, {
                    gt: 300,
                    color: '#7e0023'
                }],
                outOfRange: {
                    color: '#999'
                }
            },
            series: {
                name: 'Beijing AQI',
                type: 'line',
                data: lineData.map(function (item) {
                    return item[1];
                })
            }
        }
        chart.setOption(option);
    }
};
</script>

<style lang="scss" scoped>
.chart {
    width: 100%;
    height: 100%;
}
</style>

