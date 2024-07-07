# Desafio Manejo de Eventos

![alt](./public/Captura%20de%20pantalla%202024-07-07%20154256.png)

## Sistema de Gestión de Pacientes

### Descripción

Esta es una sencilla aplicación Vue.js para gestionar citas de pacientes. La aplicación permite a los usuarios agregar, visualizar y eliminar citas de pacientes con detalles como nombre, fecha, hora, gravedad y motivo de la cita.

## Características

<ul>
<li>Agregar nuevas citas para pacientes.</li>
<li>Mostrar una lista de citas de pacientes.</li>
<li>Eliminar una cita de un paciente.</li>
<li>Clasificar las citas según su gravedad (Leve, Moderada, Grave).</li>
<li>Estructura del proyecto</li>
</ul>

## El proyecto consta de los siguientes componentes principales:

<ul>
<li>App.vue : el componente principal de la aplicación.</li>
<li>FormularioCitas.vue : Un componente de formulario para agregar nuevas citas de pacientes.</li>
<li>TodoComponent.vue : un componente para mostrar citas de pacientes individuales.</li>

</ul>

## Componentes

<ul>
<li>App.vue.
Este es el componente principal de la aplicación que contiene la estructura general de la aplicación. Incluye el FormularioCitascomponente para agregar nuevos pacientes y una sección para mostrar la lista de pacientes que utilizan el TodoComponent.</li>
<li>FormularioCitas.vue.
Este componente proporciona un formulario para que los usuarios ingresen los datos del paciente. Envía los datos al componente principal ( App.vue) cuando se envía el formulario.</li>

</ul>

## Dudas
<ul>
<li>En las cards, especialmente donde salen el motivo, no supe que estilos darles, porque si limitaba el widh se va para abajo y si no para los lados, honestamente lo deje asi porque no supe como resolver esto</li>

</ul>

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Lints and fixes files

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
