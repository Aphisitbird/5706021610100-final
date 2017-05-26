<template>
<div class="hello">
  <h1>{{ msg }}</h1>


  <div class="panel panel-default">
    <div class="panel-heading">
      <h3>Add Data</h3>
    </div>
    <div class="panel-body">
      <form id="form" class="form-inline" v-on:submit="adddata">
        <div class="form-group">
          <label>ชื่อวิชา:</label>
          <input type="text"  class="form-control" v-model="newdata.name" placeholder="Enter Name Subject">
        </div>
        <div class="form-group">
          <label>จำนวนหน่วยกิต:</label>
          <select class="form-control" v-model="newdata.total" name="total">
            <option value="1">1</option>
            <option value="3" selected="">3</option>
          </select>
        </div>
        <div class="form-group">
          <label>เกรด:</label>
          <select class="form-control" v-model="newdata.grade" name="grade">
            <option value="4">A</option>
            <option value="3.5">B+</option>
            <option value="3">B</option>
            <option value="2.5">C+</option>
            <option value="2">C</option>
            <option value="1.5">D+</option>
            <option value="1">D</option>
            <option value="0">F</option>
          </select>
        </div>
        <input type="submit" class="btn btn-primary" value="add data">
      </form>
    </div>
  </div>


  <div class="panel panel-default">
    <div class="panel-heading">
      <h3>Show Data</h3>
    </div>
    <div class="panel-body">
      <table class="table table-striped">
        <thead>
          <tr>
            <th>วิชา</th>
            <th>จำนวนหน่วยกิต</th>
            <th>เกรด</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="sub in sub1">
            <td>{{sub.name}}</td>
            <td>{{sub.total}}</td>
            <td>{{sub.grade}}</td>
          </tr>
        </tbody>
      </table>
      <button type="button" name="button" class="btn btn-primary">Cal Grade</button>
      <button type="button" name="button" class="btn btn-primary">Clear Grade</button>
    </div>


  </div>
</div>


</div>
</template>

<script>
export default {
  name: 'hello',
  data() {
    return {
      msg: 'Application Cal Grade',
      newdata: {
        name: '',
        total: '',
        grade: ''
      },
      sub1 : [
        {name: 'oop',total: '3',grade: 'A'}
      ],
      methods: {
        adddata: function(e){
          this.sub1.push({
            name : this.newdata.name,
            total : this.newdata.total,
            grade : this.newdata.grade,
            contacted : false
          });
          e.preventDefault();
        }
      }


    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
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
