<template>
    <div class="chart" id="main" ref="chart">
        热力地图
    </div>
</template>

<script>
import * as echarts from 'echarts';
import {data} from '../mockData/heatMap';
export default {
    // 热力地图
    name: 'heatMap',
    data() {
        return {

        };
    },
    mounted() {
        var points = [].concat.apply([], data.map(function (track) {
            return track.map(function (seg) {
                return seg.coord.concat([1]);
            });
        }));
        let chart = echarts.init(this.$refs.chart);
        let option = {
            animation: false,
            bmap: {
                center: [120.13066322374, 30.240018034923],
                zoom: 14,
                roam: true
            },
            visualMap: {
                show: false,
                top: 'top',
                min: 0,
                max: 5,
                seriesIndex: 0,
                calculable: true,
                inRange: {
                    color: ['blue', 'blue', 'green', 'yellow', 'red']
                }
            },
            series: [{
                type: 'heatmap',
                coordinateSystem: 'bmap',
                data: points,
                pointSize: 5,
                blurSize: 6
            }]
        };
        chart.setOption(option);
        var bmap = chart.getModel().getComponent('bmap').getBMap();
        bmap.addControl(new BMap.MapTypeControl());
    }
};
</script>

<style lang="scss" scoped>
.chart {
    width: 100%;
    height: 100%;
}
</style>

