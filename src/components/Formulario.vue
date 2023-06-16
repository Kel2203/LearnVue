<template>
    <div class="box">
        <div class="columns">
            <div class="columns is-8" role="form" aria-label="Formulario para criação de uma nova tarefa">
                <input type="text" class="input" placeholder="Qual tarefa voce deseja iniciar?">
                
            </div>
            <div class="is-fles is-aling-items-center is-justify-content-space-between">
            <div class="columns">
               
                    <section>
                        <strong>
                            {{ tempoDecorrido  }}
                        </strong>
                        
                      </section>
                      <button class="button" @click="iniciarTarefa">
                        <span class="icon">
                            <i class="fas fa-play"></i>
                        </span>
                        <span>play</span>
                    </button>
                    <button class="button" @click="pararTarefa">
                        <span class="icon">
                            <i class="fas fa-stop"></i>
                        </span>
                        <span>stop</span>
                    </button>
                        </div>
                </div>
         
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'FormularioMestre',
    data(){
        return{
            tempoEmSegundos: 0,
            cronometro: 0
        }
    },
    computed: {
        tempoDecorrido() : string {
            return new Date(this.tempoEmSegundos * 1000).toISOString().substr(11, 8);
        }
    },
    methods: {

       
           
        iniciarTarefa(){
            this.cronometro = setInterval(() => {
                this.tempoEmSegundos++;
            }, 1000);
        },
        pararTarefa(){
           clearInterval(this.cronometro);
        }
    }
});
</script>
