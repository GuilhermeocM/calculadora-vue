<script setup>
    const props = defineProps(['editaPrimeiroNumero', 'editaSegundoNumero', 'editaFiltro'])

</script>

<template>
    <form>
        <div class="row">
            <div class="col">
                <input type="number" placeholder="Digite o primeiro número" class="form-control" @keyup="props.editaPrimeiroNumero" @change="props.editaPrimeiroNumero">
            </div>
            <div class="col">
                <input type="number" placeholder="Digite o segundo número" class="form-control" @keyup="props.editaSegundoNumero" @change="props.editaSegundoNumero">
            </div>
            <div class="col">
                <select @change="props.editaFiltro"
                    class="form-control">
                    <option value="adicao">Adição</option>
                    <option value="subtracao">Subtração</option>
                    <option value="multiplicacao">Multiplicação</option>
                    <option value="divisao">Divisão</option>
                </select>
            </div>
        </div>
    </form>
</template>