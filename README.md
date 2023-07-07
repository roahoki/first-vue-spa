# first-vue-spa 🧃
Aqui esta el codigo del primer spa que creo utilizando el framework Vue y la Fake API https://jsonplaceholder.typicode.com/


## Indice
I. Requerimientos de la tarea
II. Documentacion de la tarea 
III. Cómo correr la tarea


## Requerimientos de la tarea
De partida, la tarea cumple con todos los requerimientos pedidos en el enunciado
1. ✅Al inicio de la aplicación, todos los campos de texto estarán vacíos y los
numéricos tendrán valor 0. Además, los botones ">", "<" y "ID" se encuentran desactivados

2. ✅ Al presionar cargar, se traen TODOS los “posts” (son 100) desde la API
externa que provee jsonplaceholder ubicada en:
https://jsonplaceholder.typicode.com/

Esto ocurre cuando se presiona el boton "Cargar" 

3. ✅ Usted debe cargar la respuesta de la API en una estructura que le permita
realizar las operaciones descritas en este enunciado.

Los posts son agregados a la variable `posts: []`

4. ✅ El campo contador se incrementará en 1 cada vez que este es presionado y
obtiene con éxito los datos provenientes desde la API

5. Presionado el botón cargar:
a. ✅ El campo id se deja en “1”
b. ✅ El campo título cargará el contenido dado por el atributo “title” para el
elemento 1
c. ✅ El campo texto cargará el contenido del por el atributo “text” para el
elemento 1

6. ✅ Al presionar el botón “>” (avance), se deberá cambiar “avanzar” en el siguiente
elemento dentro de la estructura almacenada (del n, pasa al n+1), modificando
valores de título, texto y id acorde al elemento “n+1”

7. ✅ Al presionar el botón “<” (retroceso), se deberá cambiar “retroceder” en el
elemento anterior dentro de la estructura almacenada (del n, pasa al n-1),
modificando valores de título, texto y id acorde al elemento “n-1”

8. ✅ También puede ingresar directamente un id en el campo id (valor de 1 a 100) y
desplegar el elemento n-ésimo solicitado.

9. ✅ Cada vez que se presione cargar se DEBE invocar a la API y obtener la totalidad
de los elementos

10. ✅ Usted debe controlar que no se puede retroceder más allá del elemento 1 ni avanzar más allá del elemento 100

11. ✅ Usted debe controlar que no se puedan ingresar elementos menores a 1 ni mayores a 100 en el campo id


## Documentacion de la tarea

El trabajo se realizó en base al framework de Vue para javascript. Se trabajó principalmente en los documentos views/App.vue y styles/App.css 

Para poder codear esto me ayudé directamente de ChatGPT para la parte de las implementaciones de <template> y <script> en App.vue

Tambien saque css de https://codepen.io/team/codepen/pen/axwMPo para crear una transicion inicial y de https://codepen.io/ en general obtuve codigo css de la pagina general https://codepen.io

## Como correr la tarea

Para correr la tarea es necesario abrir la consola en el directorio raiz del trabajo y ejecutar `npm install` para instalar las dependencias del proyecto, posteriormente se debe ejecutar `npm run dev` en consola se podra obtener del localhost http://localhost:5173/


