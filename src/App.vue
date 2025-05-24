<script setup>

</script>

<template>
  <div class="container">
    <header class="p-5 pb-2 mb-4 mt-4 bg-light rounded-3">
      <h1>Calculdora</h1>
      <p class="text-end">escolha abaixo a operação que deseja realizar <i class="bi bi-arrow-down"></i></p>
    </header>
    <form>
    <div class="row">
      <div class="col">
        <input type="number" placeholder="Digite o primeiro número" class="form-control">
      </div>
      <div class="col">
        <input type="number" placeholder="Digite o segundo número" class="form-control">
      </div>
      <div class="col">
        <select class="form-control">
          <option value="adicao">Adição</option>
          <option value="subtracao">Subtração</option>
          <option value="multiplicacao">Multiplicação</option>
          <option value="divisao">Divisão</option>
        </select>
      </div>
    </div>
  </form>
  </div>
  
</template>

<style scoped></style>
