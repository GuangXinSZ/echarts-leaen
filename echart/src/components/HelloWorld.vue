<template>
  <div class="container">
    <!-- 为ECharts准备一个具备大小（宽高）的Dom -->
    <div id="main" style="width: 600px;height:400px;"></div>
    <div class="content">
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
    }
  },
  methods: {
    drawLine () {
      let myChart = this.$echarts.init(document.getElementById('main'))
      // var option = {
      //   title: {
      //     text: 'ECharts 入门示例'
      //   },
      //   tooltip: {},
      //   legend: {
      //     data: ['销量']
      //   },
      //   xAxis: {
      //     data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
      //   },
      //   yAxis: {},
      //   series: [{
      //     name: '销量',
      //     type: 'bar',
      //     data: [5, 20, 37, 10, 10, 20]
      //   }]
      // }
      let option = {
        // 背景颜色
        backgroundColor: '#2c343c',
        // 随机颜色
        // color: ['#c23531','#2f4554', '#61a0a8', '#d48265', '#91c7ae','#749f83',  '#ca8622', '#bda29a','#6e7074', '#546570', '#c4ccd3'],
        series: [
          {
            // 自定义颜色
            // color: ['#c23531', '#32C5E9', '#67E0E3', '#9FE6B8', '#FFDB5C','#ff9f7f', '#fb7293', '#E062AE', '#E690D1', '#e7bcf3', '#9d96f5', '#8378EA', '#96BFFF'],
            name: '访问来源',
            type: 'pie',
            radius: '55%',
            roseType: 'angle',
            itemStyle: {
              // 阴影的大小
              shadowBlur: 0,
              // 阴影水平方向上的偏移
              shadowOffsetX: 0,
              // 阴影垂直方向上的偏移
              shadowOffsetY: 0,
              // 阴影颜色
              shadowColor: 'rgba(0, 0, 0, 0.5)'
            },
            // 引导线的颜色
            labelLine: {
               lineStyle: {
                color: 'rgba(255, 255, 255, 0.3)'
              }
            },
            data: [
              {value: 235, name: '视频广告'},
              {value: 274, name: '联盟广告'},
              {value: 310, name: '邮件营销'},
              {value: 335, name: '直接访问'},
              {value: 400, name: '搜索引擎'}
            ]
          }
        ]
      }
    //   let option = {
    //     title : {
    //       text: '某站点用户访问来源',
    //       subtext: '纯属虚构',
    //       x:'center'
    //     },
    //     tooltip : {
    //       trigger: 'item',
    //       formatter: "{a} <br/>{b} : {c} ({d}%)"
    //     },
    //     legend: {
    //       orient: 'vertical',
    //       left: 'left',
    //       data: ['直接访问','邮件营销','联盟广告','视频广告','搜索引擎']
    //     },
    //     series : [
    //     {
    //       name: '访问来源',
    //       type: 'pie',
    //       radius : '55%',
    //       center: ['50%', '60%'],
    //       data: [
    //         {value: 335, name: '直接访问'},
    //         {value: 310, name: '邮件营销'},
    //         {value: 234, name: '联盟广告'},
    //         {value: 135, name: '视频广告'},
    //         {value: 1548, name: '搜索引擎'}
    //       ],
    //       itemStyle: {
    //         emphasis: {
    //           shadowBlur: 10,
    //           shadowOffsetX: 0,
    //           shadowColor: 'rgba(0, 0, 0, 0.5)'
    //         }
    //       }
    //     }
    //   ]
    // }
      myChart.setOption(option)
    }
  },
  mounted () {
    this.drawLine()
  }
}
</script>

<!-- Add 'scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
