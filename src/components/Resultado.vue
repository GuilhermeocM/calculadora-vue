<script setup>
    const props = defineProps(['resultado'])

</script>

<template>
    <p class="resultado">
        {{ props.resultado }}
    </p>
</template>