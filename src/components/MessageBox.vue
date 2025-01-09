<template>
    <div class="w-1/4 h-auto m-4 absolute right-4">
        <Transition name="slide-fade">
            <div v-if="orderName" class="p-10 bg-indigo-100 rounded-lg">
                <h1 class="text-xl mb-3">Você selecionou o item <span class="text-pink-400 font-bold">{{ orderName
                        }}</span>
                </h1>
                <p>Por favor crie sua lista de pedidos usando apenas</p>
                <p>itens relacionado á <span class="text-pink-400">{{ orderName }}</span></p>
            </div>
        </Transition>
        <Transition name="slide-fade">
            <div v-if="isValidOrder" class="p-10 bg-red-400 rounded-lg">
                <h1 class="text-xl mb-3 text-white">Você não selecionou nenhum item!!!</h1>
                <p class="text-white">Por favor, vá até o menu lateral esquerdo e selecione um item para prosseguir com seu pedido!</p>
            </div>
        </Transition>
    </div>
</template>

<script setup>
const props = defineProps(['orderName', 'isValidOrder'])

</script>

<style scoped>
.slide-fade-enter-active {
    transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
    transition: all 0.2s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
    transform: translateY(-20px);
    opacity: 0;
}
</style>