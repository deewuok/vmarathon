<template>
  <div class="graph">
    <h2>Bar Chart With D3 </h2>
    <svg id="bar-chart"> </svg>>
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
      methods: {
        drawChart: function(data) {
          console.log('drawchart')
          console.log(data)
        }
      },
      // dhw here 'my data is recognized as undefined, have to work on this
      // it may be that mounted happens before data is set up
      // it may be that props from the parent need to be involved
      // this.data didn't work below, data is not set up
      mounted: function () {
        var d3=require('d3');
        var barHeight = 20;

        console.log('mounted')
        console.log(this.data)
        // var bar = d3.select('#bar-chart')
        //   .selectAll('rect')
        //   .data(data2)
        //   .enter()
        //   .append('rect')
        //   .attr('width', function (d) {
        //     return d;
        //   })
        //   .attr('height', barHeight - 1)
        //   .attr("fill", function (d) {
        //     return colorPicker(d)
        //   })


        function colorPicker(v) {
          if (v < 120) {
            return "#666666"
          }
          else {
            return "#FF0033";
          }
        }
      },
      props: ['data'],
      // 1) when new data is updated, the watch will call drawChart and send the data to the method
      watch: {
        data: function(newData) {
          this.drawChart(newData);
        }
      }
    }
</script>

<style scoped>

</style>
