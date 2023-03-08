<script setup>
    const props = defineProps(['trocarOperacao', 'operacao', 'numero1', 'numero2',]);
</script>

<template>
    <div class="row mt-5">
        <div class="col-sm-12 col-md-3">
            <label for="numero1" class="form-label">Primeiro Numero</label>
            <input @change="props.numero1" id="numero1" class="form-control" type="text"
                placeholder="Digite o primeiro numero">
        </div>
        <div class="col-sm-12 col-md-3">
            <label for="numero2" class="form-label">Primeiro Numero</label>
            <input @change="props.numero2" id="numero2" class="form-control" type="text"
                placeholder="Digite o primeiro numero">
        </div>
        <div class="col-sm-12 col-md-2">
            <label class="form-label">Operação</label>
            <select @change="props.trocarOperacao" class="form-control">
                <option value="Somar">Somar</option>
                <option value="Subtrair">Subtrair</option>
                <option value="Multiplicar">Multiplicar</option>
                <option value="Dividir">Dividir</option>
            </select>
        </div>
        <div class="col-sm-12 col-md-3">
            <label class="pt-5">Resultado: </label>
            <span>{{ operacao }}</span>
        </div>
    </div>
</template>