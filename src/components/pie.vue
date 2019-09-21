<template>
    <div class="chart" id="main" ref="chart">
        pie
    </div>
</template>

<script>
import * as echarts from 'echarts';
export default {
    // 饼图
    name: 'pie',
    data() {
        return {

        };
    },
    mounted() {
        let chart = echarts.init(this.$refs.chart);
        let option = {
            title : {
                text: '某站点用户访问来源',
                subtext: '纯属虚构',
                x:'center'
            },
            tooltip : {
                trigger: 'item',
                formatter: "{a} <br/>{b} : {c} ({d}%)"
            },
            legend: {
                orient: 'vertical',
                left: 'left',
                data: ['直接访问','邮件营销','联盟广告','视频广告','搜索引擎']
            },
            series : [
                {
                    name: '访问来源',
                    type: 'pie',
                    radius : '55%',
                    center: ['50%', '60%'],
                    label: {
                        normal: {
                            position: 'outside'
                        }
                    },
                    labelLine: {
                        normal: {
                            show:  true,
                            length: 20,
                            length2: 50,
                            lineStyle: {
                                color: '#ccc',
                                width: 3
                            }
                        }
                    },
                    data:[
                        {value:335, name:'直接访问'},
                        {value:310, name:'邮件营销'},
                        {value:234, name:'联盟广告'},
                        {value:135, name:'视频广告'},
                        {value:1548, name:'搜索引擎'}
                    ],
                    itemStyle: {
                        emphasis: {
                            shadowBlur: 10,
                            shadowOffsetX: 0,
                            shadowColor: 'rgba(0, 0, 0, 0.5)'
                        }
                    }
                }
            ]
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

