<script setup>
import { ref } from 'vue'
import { useRecepcionStore } from '../stores/useRecepcionStore.js'

const { state } = useRecepcionStore()

const form = ref({ isbn: '', titulo: '', editorial: '', nivel: 'Básica', anio_publicacion: 2025 })

function guardar(){
  if(form.value.isbn.length < 10 && form.value.isbn.length < 13){
    alert('ISBN demasiado corto')
    return
  }
  state.libros.push({ id: state._seq.libros++, ...form.value })
  form.value = { isbn: '', titulo: '', editorial: '', nivel: 'Básica', anio: 2025 }
}
</script>

<template>
  <div>
    <h2>Libros</h2>
    <form @submit.prevent="guardar">
      <input v-model="form.isbn" placeholder="ISBN" />
      <input v-model="form.titulo" placeholder="Título" />
      <input v-model="form.editorial" placeholder="Editorial" />
      <select v-model="form.nivel">
        <option>Básica</option>
        <option>Media</option>
      </select>
      <input v-model.number="form.anio" type="number" placeholder="Año" />
      <button type="submit">Agregar</button>
    </form>

    <ul>
      <li v-for="l in state?.libros || []" :key="l.id">{{ l.titulo }} - {{ l.isbn }} - {{ l.anio }}</li>
    </ul>
  </div>
</template>
