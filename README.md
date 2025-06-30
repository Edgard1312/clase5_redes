# FTSApp - Proyecto Integrador Redes

## Descripción

FTSApp es una aplicación para la transferencia segura de archivos entre un cliente y un servidor, desarrollada como trabajo práctico para la materia "Programación sobre redes". Permite subir, descargar, listar, renombrar y eliminar archivos de forma segura, tanto por línea de comandos como desde una interfaz web.

---

## Tecnologías utilizadas

- Node.js: Plataforma principal para el desarrollo del servidor y cliente.
- TLS (Transport Layer Security): Seguridad en la comunicación entre cliente y servidor.
- HTML/CSS/JavaScript: Interfaz web para la gestión de archivos.
- readline: Interfaz de línea de comandos para el cliente.
- Express: Servidor HTTP para la interfaz web.

---

## Estructura del proyecto

```
FTSAPP_5/
│
├── src/
│   ├── secure-server.js      # Servidor TLS
│   ├── secure-client.js      # Cliente TLS por consola
│   └── certs/                # Certificados TLS
│
├── public/
│   ├── index.html            # Interfaz web
│   ├── style.css             # Estilos de la interfaz
│   └── main.js               # Lógica de la interfaz web
│
├── .gitignore
└── README.md
```

---

## Pasos para ejecutar el sistema

### 1. Instalar dependencias

```bash
npm install
```


### 2. Iniciar el servidor

```bash
node src/secure-server.js
```

### 3. Usar el cliente por consola

```bash
node src/secure-client.js
```

### 4. Usar la interfaz web

Abrir `public/index.html` en rl navegador o acceder a través del servidor HTTP.

---

## Comandos disponibles en el cliente

- `LIST`  
  Lista los archivos disponibles en el servidor.
- `GET <archivo>`  
  Descarga un archivo.
- `PUT <archivo>`  
  Sube un archivo al servidor.
- `DELETE <archivo>`  
  Elimina un archivo del servidor.
- `RENAME <viejo> <nuevo>`  
  Renombra un archivo.
- `SALIR`  
  Cierra la conexión.

### 5. Actividades realizadas

1. Iniciar el servidor TLS (secure-server.js)
Este es el servidor que gestiona archivos.
node secure-server.js

Salida esperada:
[SERVER] Servidor TLS escuchando en puerto 6000

2. Iniciar el servidor web (web-server.js)
Este es el backend que expone la API REST + sirve la UI:
node web-server.js

Salida esperada:
🔐 UI web segura disponible en https://localhost:3000

3. Acceder a la interfaz web
Abrir navegador.
Ir a: https://localhost:3000
Aceptar el riesgo del certificado autofirmado.
Deberías ver la tabla de archivos del servidor y el formulario para subir archivos.
Pruebas a realizar:

1. Ver archivos existentes (LIST)
Si hay archivos en src/files/, deberían aparecer en la tabla.
Si no hay, debe mostrar el mensaje "No hay archivos en el servidor".

2. Subir archivo (PUT)
Seleccionar un archivo desde el formulario.
Click en “Subir”.
El archivo debe aparecer en la lista.
Verificar que no quede ningún archivo temporal en src/uploads/.

3. Descargar archivo (GET)
Click en “Descargar” al lado de un archivo.
El navegador debe descargar el archivo correctamente.

4. Eliminar archivo (DELETE)
Click en “Eliminar”.
Confirmar.
El archivo debe desaparecer de la lista y eliminarse en src/files/.

5. Renombrar archivo (RENAME)
Click en “Renombrar”.
Ingresar nuevo nombre (por ejemplo nuevo.txt).
El nombre debe actualizarse en la tabla.

6. Extras (opcional)
Probar con archivos binarios: imágenes, PDF, etc.
Probar varios usuarios accediendo al mismo tiempo (en distintas pestañas).
Apagar el servidor TLS y ver qué errores aparecen al operar.


## Cambios

Se realizaron cambios con css en la interdaz.

## Capturas de las actividades realizadas de las 5 clases

https://docs.google.com/document/d/1KaSkvpL--IhJm44_5KXlxFFZhZB6bzvTHqiQ42pmlGQ/edit?usp=sharing

