document.getElementById('pillForm').addEventListener('submit', function (e) {
    e.preventDefault();

    // Obtener la hora seleccionada por el usuario
    const pillTime = document.getElementById('pillTime').value;
    
    // Guardar el recordatorio
    localStorage.setItem('pillTime', pillTime);

    // Actualizar el mensaje de recordatorio
    const pillMessage = document.getElementById('pillMessage');
    pillMessage.textContent = `Tienes que tomar tu pastilla a las ${pillTime}.`;

    // Mostrar el botón "Tomé la pastilla"
    const markButton = document.getElementById('markAsTaken');
    markButton.style.display = 'block';
});

// Función para verificar si es hora de tomar la pastilla
function checkPillReminder() {
    const pillTime = localStorage.getItem('pillTime');

    if (pillTime) {
        const currentTime = new Date().toLocaleTimeString('en-GB', { hour: '2-digit', minute: '2-digit' });

        if (currentTime === pillTime) {
            alert("¡Es hora de tomar tu pastilla!");
        }
    }
}

// Evento para marcar la pastilla como tomada
document.getElementById('markAsTaken').addEventListener('click', function () {
    const pillMessage = document.getElementById('pillMessage');
    pillMessage.textContent = `Pastilla tomada a las ${localStorage.getItem('pillTime')}`;
    pillMessage.classList.add('taken');

    // Ocultar el botón de tomar la pastilla
    this.style.display = 'none';

    // Eliminar la hora guardada
    localStorage.removeItem('pillTime');
});

// Revisa cada minuto si es hora de tomar la pastilla
setInterval(checkPillReminder, 60000);
