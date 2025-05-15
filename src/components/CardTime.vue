<template>
    <q-card class="q-pa-lg meuCard">
        <q-card-title>
            <span class="text-h4" v-if="time !=null">
                {{ time.nome }}
            </span>
            <span class="text-h4" v-if="time == null">
                <q-skeleton type="rect"/>
            </span>
        </q-card-title>

<q-separator/>

        <q-card-section class="Furia" v-if="time !=null">
            <span class="text-h6" v-for="jogador in time.jogadores" v-bind:key="jogador"> {{ jogador }} <br> </span> 
        </q-card-section>

        <q-card-section v-if="time == null">
            <q-skeleton type="text" ></q-skeleton>
            <q-skeleton type="text" ></q-skeleton>
            <q-skeleton type="text" ></q-skeleton>
        </q-card-section>

    </q-card>
</template>

<script>
export default {
    name: 'CardTime',
    data(){
        return {
            time: null,
        }
    },
    mounted(){
        setTimeout(()=> {
            this.time = {
                nome: 'Furia',
                jogadores: ['Fallen', 'yuurih', 'YEKINDAR', 'KSCERATO', 'molodoy'],
            }
        }, 3000)
    }
}
</script>

<style>
 .meuCard {
    min-width: 400px;
    background-color: rgb(50, 50, 50);
 }
 .Furia {
    background-color: rgb(50, 50, 50);
 }
 .text-h4, .text-h6{
    color: rgb(0, 4, 115);
 }

</style>