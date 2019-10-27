<template>
    <div class="chart" id="main" ref="chart">
        填充地图
    </div>
</template>

<script>
import * as echarts from 'echarts';
import chinaJson from 'echarts/map/json/china.json';

export default {
    // 填充地图
    name: 'fillMap',
    data() {
        return {

        };
    },
    mounted() {
        let chart = echarts.init(this.$refs.chart);
        echarts.registerMap('china', chinaJson);
        let option = {
            series: [{
                type: 'map',
                map: 'china',
                data:[
                    {name: '湖北', value: 1234},
                    {name: '湖南', value: 987},
                    {name: '北京', value: 4823},
                    {name: '西藏', value: 123}
                ]
            }],
            visualMap: {
                left: 'left',
                inRange: {
                    color: ['#6FCF6A', '#FFFD64', '#FF5000']
                },
                min: 0,
                max: 5000
            }
        };
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




