<template>
    <div class="chart" id="main" ref="chart">
        bar
    </div>
</template>

<script>
import * as echarts from 'echarts';
export default {
    // 基本柱状图
    name: 'bar',
    data() {
        return {

        };
    },
    mounted() {
        let chart = echarts.init(this.$refs.chart);
        let option = {
            title: {
                text: 'ECharts 入门示例'
            },
            xAxis: {
                type: 'category',
                data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
            },
            yAxis: {
                type: 'value'
            },
            series: [{
                data: [120, 200, 150, 80, 70, 110, 130],
                type: 'bar'
            }]
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

