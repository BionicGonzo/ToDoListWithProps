<template>
  <div id="app" class="p-3">
    <div class="col-md-6 mx-auto">
      <div class="card p-2">
        <div class="card-title">
          <h2>Ingresar Tarea</h2>
        </div>
        <div class="card-body">
          <div class="input-group mb-3">
            <span class="input-group-text" id="basic-addon1">Ingresar Tarea</span>
            <input v-model="tarea" @keyup.enter="addTarea" type="text" class="form-control" aria-label="Tarea" aria-describedby="basic-addon1">
          <button @click="addTarea" class="btn btn-outline-dark">Agregar</button>
          </div>
        </div>
        <Tareas mensaje="Lista de Tareas" :listaTareas="listaTareas" @remove="removeTareaEnviada"/>
      </div>
    </div>
  </div>
</template>

<script>
import Tareas from "@/components/tareas";

export default {
  name: 'App',
  components: {
    Tareas
  },
  data(){
    return {
      tarea: '',
      listaTareas: [],
    }
  },
  methods: {
    addTarea(){
      const tarea = this.tarea
      if (tarea !== '') {
        this.listaTareas.push(tarea)
      }
      console.log(this.listaTareas)
      this.tarea = ''
    },
    removeTareaEnviada(item){
      console.log(item)
      for(let i in this.listaTareas) {
        if (this.listaTareas[i] === item) {
          var n = parseInt(i)
        }
      }
      this.listaTareas.splice(n, 1)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
