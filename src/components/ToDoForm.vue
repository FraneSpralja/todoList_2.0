<template>

  <form id="form" @submit.prevent="addTarea">

    <input type="text" id="inputForm" v-model="tarea">
    <button type="submit" id="btn">Agregar tarea</button>

  </form>
    <table id="table">
        <thead>
            <tr>
                <th>ID</th>
                <th>Tarea</th>
                <th>Terminar</th>
            </tr>
        </thead>
      <PaintList 
      
        v-for="(item, index) in arrayTareas" :key="index" :item="item" :index="index" 
        
        @accion="deleteTarea(index)"
        
      /> 
    </table>
  

</template>

<script>
import PaintList from './PaintList.vue'


export default {
  name: 'ToDoForm',
  components: {
    PaintList,
  },
  data(){
    return {
      tarea: "",
      arrayTareas: [],
    }
  },
  methods:{
    addTarea(){

      if (this.tarea !== ""){
        this.arrayTareas.push(this.tarea)
        console.log(this.arrayTareas)
      }else{
        console.log("No has agregado tarea")
      }

    },

    deleteTarea(index){
      
      this.arrayTareas.splice(index, 1)
  },
  }}
</script>

// <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#form{
  padding: 2em;
  margin: 0 auto;
}

#inputForm {
  height: 1.5em;
  width: 40%;
  border-radius: 7px;
  box-shadow: 0 0 4px #000;
  margin-right: 7px;
}

#btn{
  padding: .3em 0;
  width: 20%;
  border-radius: 25px;
  box-shadow: 0 0 4px;
  background-color: rgb(30, 0, 201);
  color: #fff;
}

#table {
  width: 50%;
  font-family: monospace;
  font-size: 25px;
  text-align: center;
}

tr:nth-child(even){
  background-color: #6bc9ff;
}

th, td {
  border-bottom: 1px solid #000;
}

</style>