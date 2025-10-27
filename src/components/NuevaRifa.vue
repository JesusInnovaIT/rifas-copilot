<template>
  <div class="nueva-rifa-container">
    <h1>Sistema de Gestión de Rifas</h1>
    
    <div class="form-card">
      <h2>Nueva Rifa</h2>
      
      <form @submit.prevent="handleSubmit" class="rifa-form">
        <div class="form-group">
          <label for="nombre">Nombre de la rifa</label>
          <input
            id="nombre"
            v-model="formData.nombre"
            type="text"
            required
            placeholder="Ej: Rifa Navideña 2025"
            class="form-input"
          />
        </div>

        <div class="form-group">
          <label for="fecha">Fecha de la rifa</label>
          <input
            id="fecha"
            v-model="formData.fecha"
            type="date"
            required
            class="form-input"
          />
        </div>

        <div class="form-group">
          <label for="premios">Número de premios</label>
          <input
            id="premios"
            v-model.number="formData.numeroPremios"
            type="number"
            required
            min="1"
            placeholder="Ej: 3"
            class="form-input"
          />
        </div>

        <div class="form-group">
          <label for="boletos">Número de boletos</label>
          <input
            id="boletos"
            v-model.number="formData.numeroBoletos"
            type="number"
            required
            min="1"
            placeholder="Ej: 100"
            class="form-input"
          />
        </div>

        <div class="form-actions">
          <button type="submit" class="btn btn-primary">
            Crear Rifa
          </button>
          <button type="button" @click="resetForm" class="btn btn-secondary">
            Limpiar
          </button>
        </div>
      </form>

      <div v-if="rifasCreadas.length > 0" class="rifas-list">
        <h3>Rifas Creadas</h3>
        <div v-for="(rifa, index) in rifasCreadas" :key="index" class="rifa-item">
          <div class="rifa-info">
            <h4>{{ rifa.nombre }}</h4>
            <p><strong>Fecha:</strong> {{ formatDate(rifa.fecha) }}</p>
            <p><strong>Premios:</strong> {{ rifa.numeroPremios }}</p>
            <p><strong>Boletos:</strong> {{ rifa.numeroBoletos }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, reactive } from 'vue'

interface Rifa {
  nombre: string
  fecha: string
  numeroPremios: number
  numeroBoletos: number
}

const formData = reactive<Rifa>({
  nombre: '',
  fecha: '',
  numeroPremios: 0,
  numeroBoletos: 0
})

const rifasCreadas = ref<Rifa[]>([])

const handleSubmit = () => {
  // Create a copy of the form data
  rifasCreadas.value.push({
    nombre: formData.nombre,
    fecha: formData.fecha,
    numeroPremios: formData.numeroPremios,
    numeroBoletos: formData.numeroBoletos
  })
  
  // Show success message
  alert(`Rifa "${formData.nombre}" creada exitosamente!`)
  
  // Reset form
  resetForm()
}

const resetForm = () => {
  formData.nombre = ''
  formData.fecha = ''
  formData.numeroPremios = 0
  formData.numeroBoletos = 0
}

const formatDate = (dateString: string) => {
  const date = new Date(dateString)
  return date.toLocaleDateString('es-ES', {
    year: 'numeric',
    month: 'long',
    day: 'numeric'
  })
}
</script>

<style scoped>
.nueva-rifa-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem;
}

h1 {
  text-align: center;
  color: #2c3e50;
  margin-bottom: 2rem;
}

.form-card {
  background: white;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  padding: 2rem;
}

h2 {
  color: #42b883;
  margin-bottom: 1.5rem;
  padding-bottom: 0.5rem;
  border-bottom: 2px solid #42b883;
}

.rifa-form {
  margin-bottom: 2rem;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group label {
  display: block;
  margin-bottom: 0.5rem;
  font-weight: 600;
  color: #2c3e50;
}

.form-input {
  width: 100%;
  padding: 0.75rem;
  border: 2px solid #e0e0e0;
  border-radius: 4px;
  font-size: 1rem;
  transition: border-color 0.3s;
  box-sizing: border-box;
}

.form-input:focus {
  outline: none;
  border-color: #42b883;
}

.form-actions {
  display: flex;
  gap: 1rem;
  margin-top: 2rem;
}

.btn {
  padding: 0.75rem 1.5rem;
  border: none;
  border-radius: 4px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s;
}

.btn-primary {
  background-color: #42b883;
  color: white;
}

.btn-primary:hover {
  background-color: #359268;
}

.btn-secondary {
  background-color: #e0e0e0;
  color: #2c3e50;
}

.btn-secondary:hover {
  background-color: #d0d0d0;
}

.rifas-list {
  margin-top: 3rem;
  padding-top: 2rem;
  border-top: 2px solid #e0e0e0;
}

.rifas-list h3 {
  color: #2c3e50;
  margin-bottom: 1.5rem;
}

.rifa-item {
  background: #f8f9fa;
  border-left: 4px solid #42b883;
  padding: 1rem;
  margin-bottom: 1rem;
  border-radius: 4px;
}

.rifa-info h4 {
  color: #2c3e50;
  margin-bottom: 0.5rem;
}

.rifa-info p {
  margin: 0.25rem 0;
  color: #5a5a5a;
}
</style>
