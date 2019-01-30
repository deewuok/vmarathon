<template>
  <div class="graph">
    <h2>Inside the Bar component </h2>
    <p>{{someData}}</p>
    <!--<p>{{data}}</p>-->
    <svg id="bar-chart"> </svg>
  </div>
</template>

<script>
    export default {
      name: "bar",
      //  data: function() {
      //    return {
      //        data2: [80, 120, 60, 150, 200]
      //    }
      // },
      // dhw here
      // PASSED values go in props and are bound in the parent
      mounted: function () {
        var d=this.data
        console.log('mounted')
        console.log(d)
        this.drawChart(d)
      },
      methods: {
        drawChart: function (data) {
          var d3 = require('d3');
          var barHeight = 20;

          // console.log('mounted in bar (show this.someData)')
          // console.log(this.someData)
           console.log('this.someData')
           console.log(this.someData)
          d3.select('#bar-chart').html(""); // I don't know why, but I needed to do this for the graph torefresh
          var bar = d3.select('#bar-chart')
            .selectAll('rect')
            .data(this.someData )
            .enter()
            .append('rect')
            .attr('width', function (d) {
              return d;
            })
            .attr('height', barHeight - 1)
            .attr("fill", function (d) {
              return colorPicker(d)
            })
            .attr('transform', function (d, i) {
              return "translate(0," + i * barHeight + ")";
            });

          function colorPicker(v) {
            if (v < 120) {
              return "#666666"
            }
            else {
              return "#FF0033";
            }
          }
        }
      },
      // see : https://stackoverflow.com/questions/32481580/vue-js-get-data-from-parent-vue
      props: ['some-data'],
      // 1) when new data is updated, the watch will call drawChart and send the data to the method
      watch: {
        someData: function(newData) {
          console.log('newData')
          console.log(newData)
          this.drawChart(newData);
        }
      }
    }
</script>

<style scoped>

</style>
