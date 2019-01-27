<template>
  <div id='container'>
    <div id='text-input'>
      <h2>Text Input</h2>

      <form>
        First name:<br>
        <input type="text" name="firstname">
        <br>
        Last name:<br>
        <input type="text" name="lastname">
      </form>
    </div>


    <bar>

    </bar>
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

  import bar from './components/bar.vue'

  export default {
    name: 'app',
    components: { bar},
    data: function() {
      return {
        mydata: [80, 120, 60, 150, 200]
      }
    },

  }
</script>`


<style scoped>
  .forms{
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
