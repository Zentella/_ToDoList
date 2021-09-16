<template>
    <div class="container">
        <div class="hellovue">Crear una nueva tarea

        </div>
            <div class="tarea">
                Tarea
                <input type="text" v-model="texto" placeholder="ingresa nueva tarea"/>
                <button @click="guardar">Crear</button>

                
                    <p class="lista">Lista</p>
            </div>

            <div class="listaOk" v-if="listaOk">
                <ul>
                    <li v-for="(item , index) in lista" :key="index">
                        <span>{{ index }}: {{ item }}</span>                  
                    </li>
                </ul>
            </div>

            <div>
                cuenta regresiva
                <button @click="b1">1</button>
                <button @click="b2">2</button>
                <button @click="b3">3</button>
            </div>

            <div v-if="mostrar">
                        {{ tiempo }}
                
            </div>
    </div>
</template>

<script>
    export default {
        name: 'HelloVue',
        data() {
            return {
                listaOk: false,
                lista: [],
                tiempo:'',
                texto : '',
                mostrar: false              
            };
        },
        methods: {
            guardar: function () {
                this.lista.push(this.texto)
                this.texto = ""
                this.listaOk = "!this.listaOk"                    
            },
            b1() {
                this.mostrar = "!this.mostrar" 
                this.tiempo = 1
                //tiempo = setInterval(1000);  
                //this.tiempo = setInterval(20000); 
                //this.tiempo = setInterval(function(){ 'this.tiempo' }, 3000);
                
                //this.tiempo = setTimeout(this.tiempo, 3000);
                //setTimeout(() => {this.tiempo}, 5000);
                setTimeout(() => {
                this.tiempo--
                }, 1000);
            },
            b2() {
                this.mostrar = "!this.mostrar" 
                this.tiempo = 2
                //tiempo = setInterval(1000);  
                //this.tiempo = setInterval(20000); 
                //this.tiempo = setInterval(function(){ 'this.tiempo' }, 3000);
                
                //this.tiempo = setTimeout(this.tiempo, 3000);
                //setTimeout(() => {this.tiempo}, 5000);
                setTimeout(() => {
                    setTimeout(() => {
                this.tiempo--
                }, 2000);
                this.tiempo--
                }, 1000);
            },
            b3() {
                this.mostrar = "!this.mostrar" 
                this.tiempo = 3
                //tiempo = setInterval(1000);  
                //this.tiempo = setInterval(20000); 
                //this.tiempo = setInterval(function(){ 'this.tiempo' }, 3000);
                
                //this.tiempo = setTimeout(this.tiempo, 3000);
                //setTimeout(() => {this.tiempo}, 5000);
                setTimeout(() => {
                    setTimeout(() => {
                        setTimeout(() => {
                this.tiempo--
                }, 3000);
                this.tiempo--
                }, 2000);
                this.tiempo--
                }, 1000);
            },
        }

    };
</script>

<style scoped>
    .container {
        padding:40px 400px;
    }
    .hellovue {
        color: gray;
        font-weight: bold;
        font-size: 50px;
    }
    .tarea {
        color: black;
        font-weight: bold;
        font-size: 20px;
        margin-top: 20px;
        margin-left: 50px;

    }
    .lista {
        color: gray;
        font-weight: bold;
        font-size: 50px;
        margin-left: 100px;
    }
        .listaOk {
        color: black;
        font-weight: bold;
        margin-left: 100px;
    }
</style>
