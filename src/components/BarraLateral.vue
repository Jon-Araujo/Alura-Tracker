<template>
    <header>
        <h1>
            <img src="../assets/logo.png" alt="Logo do Alura Tracker.">
        </h1>
        <button @click="alterarTema"> {{ textoModoEscuro }}</button>
    </header>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';
    
    export default defineComponent({
        name: 'BarraLateral',
        emits: ['aoTemaAlterado'],
        data () {
            return {
                modoEscuro: false
            } 
        },
        computed: {
            textoModoEscuro () {
                if (this.modoEscuro) {
                    return 'Desativar modo escuro'
                } else {
                    return 'Ativar modo escuro'
                }
            }
        },
        methods: {
            alterarTema () {
                this.modoEscuro = !this.modoEscuro
                this.$emit('aoTemaAlterado', this.modoEscuro)
            }
        }
    })
</script>

<style scoped>
    header {
        background-color: #0d3b66;
        text-align: center;
        width: 100%;
        height: 100vh;
        padding: 1rem;
    }
    button {
        padding: 1rem;
        border-radius: 8px;
    }
    @media only screen and (max-width: 768px) {
        header {
            padding: 2.5rem;
            height: auto;
        }
    }
</style>
