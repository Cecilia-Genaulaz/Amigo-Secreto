// El principal objetivo de este desafío es fortalecer tus habilidades en lógica de programación. Aquí deberás desarrollar la lógica para resolver el problema.

// Array para almacenar los nombres ingresados por el usuario
let nombres = []; 

// Función para agregar nombres al array
function agregarNombre() {
    const nombreInput = document.getElementById('nombreInput');  
    const nombre = nombreInput.value.trim();  
   
    // Verificar si el campo está vacío
    if (nombre === "") {
        
        document.getElementById('error').textContent = "¡DEBES INGRESAR UN NOMBRE CORRECTO!";
    } else {
        
        nombres.push(nombre);
        
        nombreInput.value = "";
       
        document.getElementById('error').textContent = ""; 
    }
}

// Función para realizar el sorteo aleatorio
function realizarSorteo() {
    
    if (nombres.length === 0) {
        // Si no hay nombres, mostrar un mensaje de error
        document.getElementById('error').textContent = "¡DEBES INGRESAR AL MENOS UN NOMBRE!";
        return;  
    }

    // Seleccionar un ganador aleatorio de la lista de nombres
    const ganador = nombres[Math.floor(Math.random() * nombres.length)];

    // Mostrar el resultado del sorteo
    document.getElementById('resultado').textContent = `El ganador del sorteo es: ${ganador}`;
}
