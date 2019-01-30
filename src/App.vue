<template>

    <div id='container'>
      <div class='text-input'>
        <h2>Text Input</h2>

        <form>
          First name:<br>
          <input type="text" name="firstname">
          <br>
          Last name:<br>
          <input type="text" name="lastname">
        </form>
      </div>
      <div class="graph">
        <!--<h1>{{someData}}</h1>-->
        <h2>Bar Chart With D3 </h2>
        <!--<pie :data="names" />-->
        <bar :some-data="someData"/>
	<button @click='randgraph' type="button">Randomize</button>

       </div>
      <!--<bar> </bar>-->
      <div class="tableview">
        <h2>Tableview</h2>
        <table style="width:100%">
          <tr>
            <th>Firstname</th>
            <th>Lastname</th>
            <th>Age</th>
          </tr>
          <tr>
            <td>Jay</td>
            <td>Smith</td>
            <td>51</td>
          </tr>
          <tr>
            <td>Joe</td>
            <td>Johnson</td>
            <td>9</td>
          </tr>
        </table>
      </div>
    </div>
</template>

<script>
  import bar from './components/bar.vue';
  import pie from './components/pie.vue';
  var _ = require('lodash')

  const NAMES = [
    { name: 'Sarah', value: 2502 },
    { name: 'Emma', value: 2005 },
    { name: 'Laura', value: 1968 },
    { name: 'Chloé', value: 1863 },
    { name: 'Marie', value: 1810 },
    { name: 'Emily', value: 1637 },
    { name: 'Léa', value: 1592 },
    { name: 'Camille', value: 1572 },
    { name: 'Anna', value: 1433 },
    { name: 'Manon', value: 1403 }
  ]

  export default {
    components: {
      pie: pie,
      bar: bar
    },
    data: function() {
      return {
        names: _.take(NAMES, 3),
        someData:[85, 125, 65, 155, 225] // set to '' for null start
      }
    },
    // },
    // computed: {
    //   canAddAName: function() {
    //     return this.names.length < NAMES.length;
    //   }
    // },
    // methods: {
    //   addName: function() {
    //     this.names.push(NAMES[this.names.length]);
    //   }
    // }
     methods: {
       randgraph: function() {
         this.someData=Array.from({length: 5}, () => Math.floor(Math.random() * 150)+100)
       }
     }
  }
</script>


<style scoped>
  .text-input{
    width:55%;
    margin-right:2%;
    float: left;
  }
  .graph {
    width:42%;
    float: left;
  }
  .tableview {
    clear:both;
    width:100%;
  }
  table, th, td {
    border: 1px solid black;
  }

</style>
