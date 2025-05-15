<template>
    <q-card class="q-pa-lg meuCard" v-for="time in times" v-bind:key="time">
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
            times: null,
        }
    },
    mounted(){
        setTimeout(()=> {
            this.times = [{
                nome: 'Furia',
                jogadores: ['Fallen', 'yuurih', 'YEKINDAR', 'KSCERATO', 'molodoy'],
            },
            {
                nome: 'MIBR',
                jogadores: ['a', 'b', 'c', 'd', 'e'],
            }]
        }, 3000)
    },
}
</script>

<style>
 .meuCard {
    min-width: 400px;
    background-color: rgb(50, 50, 50);
    margin: 16px;
 }
 .Furia {
    background-color: rgb(50, 50, 50);
 }
 .text-h4, .text-h6{
    color: rgb(255, 255, 255);
 }

</style>