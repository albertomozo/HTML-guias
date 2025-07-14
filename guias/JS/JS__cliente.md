## JavaScript como tecnología del lado del cliente

**JavaScript del lado del cliente** es código que se ejecuta directamente en el navegador web del usuario, no en el servidor donde está alojada la página web. Una vez que el navegador descarga los archivos HTML, CSS y JavaScript, es el propio navegador quien interpreta y ejecuta el código JavaScript utilizando los recursos del equipo del usuario (procesador, memoria, etc.).

### Características principales:

- **Ejecución local**: El código se procesa en el dispositivo del usuario
- **Acceso al navegador**: Puede interactuar con elementos de la página (DOM)
- **Recursos del cliente**: Utiliza la capacidad de procesamiento del equipo del usuario
- **Información local**: Accede a datos como la fecha/hora del sistema local, zona horaria, idioma del navegador, etc.

## Ejemplos de tareas que DEBEN realizarse en JavaScript (cliente):

### 1. **Interactividad inmediata con la interfaz**
```javascript
// Función para mostrar/ocultar elementos
function toggleMenu() {
    const menu = document.getElementById('menu');
    if (menu.style.display === 'none') {
        menu.style.display = 'block';
    } else {
        menu.style.display = 'none';
    }
}
```

### 2. **Validación de formularios**
```javascript
function validateEmail() {
    const email = document.getElementById('email').value;
    const errorMessage = document.getElementById('error-message');
    
    if (!email.includes('@')) {
        errorMessage.textContent = 'Email no válido';
        errorMessage.style.color = 'red';
        return false;
    } else {
        errorMessage.textContent = 'Email válido';
        errorMessage.style.color = 'green';
        return true;
    }
}
```

### 3. **Manipulación del DOM (Document Object Model)**
```javascript
function updateCounter() {
    let count = 0;
    count++;
    document.getElementById('counter').textContent = 'Clicks: ' + count;
}

function addNewElement() {
    const newDiv = document.createElement('div');
    newDiv.textContent = 'Nuevo elemento creado';
    document.body.appendChild(newDiv);
}
```

### 4. **Cálculos y procesamiento inmediato**
```javascript
function calculateTotal() {
    const price = parseFloat(document.getElementById('price').value);
    const quantity = parseInt(document.getElementById('quantity').value);
    const total = price * quantity;
    
    document.getElementById('total').textContent = 'Total: €' + total.toFixed(2);
}

function convertTemperature() {
    const celsius = parseFloat(document.getElementById('celsius').value);
    const fahrenheit = (celsius * 9/5) + 32;
    document.getElementById('fahrenheit').value = fahrenheit;
}
```

### 5. **Gestión de información local del usuario**
```javascript
function showUserInfo() {
    const now = new Date();
    const userLanguage = navigator.language;
    const userAgent = navigator.userAgent;
    
    document.getElementById('current-time').textContent = now.toLocaleString();
    document.getElementById('user-language').textContent = userLanguage;
    document.getElementById('browser-info').textContent = userAgent;
}
```

## Funcionalidades que hacen JavaScript FUNDAMENTAL en el cliente:

### 1. **Cookies - Recordar información del usuario**
```javascript
// Guardar una preferencia del usuario
function saveUserPreference() {
    const theme = document.getElementById('theme-selector').value;
    document.cookie = "userTheme=" + theme + "; expires=Thu, 18 Dec 2025 12:00:00 UTC; path=/";
}

// Leer la preferencia guardada
function loadUserPreference() {
    const cookies = document.cookie.split(';');
    for (let cookie of cookies) {
        if (cookie.trim().startsWith('userTheme=')) {
            const theme = cookie.split('=')[1];
            document.getElementById('theme-selector').value = theme;
            applyTheme(theme);
        }
    }
}
```

### 2. **LocalStorage - Almacenamiento persistente local**
```javascript
// Guardar datos del usuario sin fecha de caducidad
function saveToStorage() {
    const userName = document.getElementById('username').value;
    const userEmail = document.getElementById('email').value;
    
    localStorage.setItem('userName', userName);
    localStorage.setItem('userEmail', userEmail);
}

// Recuperar datos guardados
function loadFromStorage() {
    const savedName = localStorage.getItem('userName');
    const savedEmail = localStorage.getItem('userEmail');
    
    if (savedName) {
        document.getElementById('username').value = savedName;
    }
    if (savedEmail) {
        document.getElementById('email').value = savedEmail;
    }
}
```

### 3. **SessionStorage - Almacenamiento temporal**
```javascript
// Guardar datos solo durante la sesión actual
function saveSessionData() {
    const formData = document.getElementById('form-data').value;
    sessionStorage.setItem('tempFormData', formData);
}

// Recuperar datos de la sesión
function loadSessionData() {
    const tempData = sessionStorage.getItem('tempFormData');
    if (tempData) {
        document.getElementById('form-data').value = tempData;
    }
}
```

### 4. **Geolocalización - Acceso a la ubicación del usuario**
```javascript
function getUserLocation() {
    if (navigator.geolocation) {
        navigator.geolocation.getCurrentPosition(function(position) {
            const latitude = position.coords.latitude;
            const longitude = position.coords.longitude;
            
            document.getElementById('location').textContent = 
                'Latitud: ' + latitude + ', Longitud: ' + longitude;
        });
    } else {
        document.getElementById('location').textContent = 'Geolocalización no soportada';
    }
}
```

### 5. **Detección de capacidades del navegador**
```javascript
function checkBrowserCapabilities() {
    const capabilities = {
        cookiesEnabled: navigator.cookieEnabled,
        onlineStatus: navigator.onLine,
        screenWidth: screen.width,
        screenHeight: screen.height,
        colorDepth: screen.colorDepth
    };
    
    document.getElementById('browser-info').innerHTML = 
        'Cookies: ' + capabilities.cookiesEnabled + '<br>' +
        'Online: ' + capabilities.onlineStatus + '<br>' +
        'Resolución: ' + capabilities.screenWidth + 'x' + capabilities.screenHeight;
}
```

## ¿Por qué JavaScript es FUNDAMENTAL en el cliente?

1. **Persistencia de datos**: Cookies y localStorage permiten recordar preferencias sin servidor
2. **Experiencia personalizada**: Adapta la interfaz según el usuario y dispositivo
3. **Funcionalidad offline**: Muchas características funcionan sin conexión
4. **Acceso a hardware**: Cámara, micrófono, GPS, sensores (solo desde el navegador)
5. **Rendimiento**: Procesamiento local sin sobrecargar el servidor
6. **Interactividad inmediata**: Respuesta instantánea sin esperar al servidor
7. **Seguridad**: Validación en tiempo real antes de enviar datos al servidor

Estas capacidades hacen que JavaScript sea absolutamente esencial para crear aplicaciones web modernas y funcionales.