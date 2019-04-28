<template>
    <div class="chart" id="main" ref="chart">
        stackLine
    </div>
</template>

<script>
import * as echarts from 'echarts';
export default {
    // 堆叠区域折线图
    name: 'stackLine',
    data() {
        return {

        };
    },
    mounted() {
        let chart = echarts.init(this.$refs.chart);
        let option = {
            title: {
                text: '堆叠区域图'  // 图表标题
            },
            tooltip : {
                trigger: 'axis',    // 图表提示类型为坐标轴提示
                axisPointer: {
                    type: 'cross',
                    label: {
                        backgroundColor: '#6a7985'
                    }
                }
            },
            legend: {
                data:['邮件营销','联盟广告','视频广告','直接访问','搜索引擎'] // 图例
            },
            toolbox: {  // 工具箱
                feature: {  // 特性
                    saveAsImage: {} // 保存为图片
                }
            },
            grid: { // 网格
                left: '3%',
                right: '4%',
                bottom: '3%',
                containLabel: true  // 包含标签
            },
            xAxis : [
                {
                    type : 'category',
                    boundaryGap : true,     // 类目粥，坐标留白策略为真，表示图表维度轴出现留白
                    data : ['周一','周二','周三','周四','周五','周六','周日']
                }
            ],
            yAxis : [
                {
                    type : 'value'
                }
            ],
            series : [
                {
                    name:'邮件营销',
                    type:'line',
                    stack: '总量',
                    areaStyle: {},  // 区域展示，设置后折线图会变成区域图
                    data:[120, 132, 101, 134, 90, 230, 210],
                    smooth: true        //  折线平滑展示
                },
                {
                    name:'联盟广告',
                    type:'line',
                    stack: '总量',
                    areaStyle: {},
                    data:[220, 182, 191, 234, 290, 330, 310],
                    smooth: true
                },
                {
                    name:'视频广告',
                    type:'line',
                    stack: '总量',
                    areaStyle: {},
                    data:[150, 232, 201, 154, 190, 330, 410],
                    smooth: true
                },
                {
                    name:'直接访问',
                    type:'line',
                    stack: '总量',
                    areaStyle: {normal: {}},
                    data:[320, 332, 301, 334, 390, 330, 320],
                    smooth: true
                },
                {
                    name:'搜索引擎',
                    type:'line',
                    stack: '总量',
                    label: {
                        normal: {
                            show: true,
                            position: 'top'
                        }
                    },
                    areaStyle: {normal: {}},
                    data:[820, 932, 901, 934, 1290, 1330, 1320],
                    smooth: true
                }
            ]
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

