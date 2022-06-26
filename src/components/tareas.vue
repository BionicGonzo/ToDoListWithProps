<template>
    <div>
        <h2>{{mensaje}}</h2>
        <table class="table">
            <thead>
                <tr>
                <th scope="col">#</th>
                <th scope="col">Tarea</th>
                <th scope="col"><i class="fa-solid fa-trash"></i></th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(item, index) in listaTareas" :key="index">
                <th>{{index + 1}}</th>
                <td>{{item}}</td>
                <td>
                    <button @click="removeTarea(item)" class="btn btn-outline-danger btn-sm" type="submit">
                        <i class="fa-solid fa-trash text-danger"></i>
                    </button>
                </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>
<script>
export default {
    name: "Tareas",
    props: {
        mensaje: String,
        listaTareas: Array
    },
    methods: {
        removeTarea(item) {
            this.$emit('remove', item)
        }
    }
}
</script>
<style scope>
</style>