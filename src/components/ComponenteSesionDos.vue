<template>
    <div class="sessionDos">
        <h2>Componente Sesión 2</h2>
        <div id="contenedorPadre">
            <div id="contenedorIzquierda">
                <form>
                    <label for="txtNombre">Nombre:</label><br>
                    <input type="text" id="txtNombre" v-model="nombre"> <br>
                    <label for="txtApellido">Apellido:</label><br>
                    <input type="text" id="txtApellido" v-model="apellido"><br>
                    <label for="txtEdad">Edad:</label><br>
                    <input type="text" id="txtEdad" v-model="edad"><br>
                    <label for="txtCorreo">Correo:</label><br>
                    <input type="text" id="txtCorreo" v-model="correo"><br>
                    <input type="submit" id="btnEnviar" value="Enviar" v-on:click.prevent="procesarDatos">

                </form>
            </div>
            <div id="contenedorDerecha">
                <p id="parrafoSaludo">Mensaje de Salida: {{ mensajeSalida }}</p>
                <p id="parrafoEdad"> Mensaje de Edad: {{ mensajeEdad }}</p>
            </div>
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'SesionDos',
    data: function () {
        return {
            nombre: '',
            apellido: '',
            edad: '',
            correo: '',
            mensajeSalida: '',
            mensajeEdad: '',
        }
    },
    methods: {
        procesarDatos: function () {
            this.mensajeSalida = `Hola ${this.nombre} ${this.apellido}, el correo registrado es ${this.correo}`;
            let edadNumero = Number(this.edad);
            let catalogacion = '';
            if (edadNumero >= 0 && edadNumero <= 13) {
                catalogacion = 'Niñez';
            }
            else if (edadNumero >= 14 && edadNumero <= 17) {
                catalogacion = 'Adolescente';
            }
            else if (edadNumero >= 18 && edadNumero <= 35) {
                catalogacion = 'Adulto Jóven';
            }
            else if (edadNumero >= 36 && edadNumero <= 64) {
                catalogacion = 'Adulto';
            }
            else {
                catalogacion = 'Adulto Mayor';
            }

            this.mensajeEdad = `La catalogación de su edad ${this.edad} es ${catalogacion}`;
        },
    },
}
</script>

<style scoped>
#contenedorIzquierda{
    width: 50%;
    display: inline-block;
}

#contenedorDerecha{
    width: 30%;
    display: inline-block;
}
input{
    width: 20%;
}
#btnEnviar{
    margin-top: 20px;
}
</style>
  