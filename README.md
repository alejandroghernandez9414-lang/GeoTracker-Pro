# GeoTracker-Pro

**Generación automatizada de mapas interactivos por técnico a partir de archivos Excel.**

GeoTracker-Pro es una herramienta web desarrollada para transformar información operativa contenida en archivos Excel en **mapas interactivos organizados por técnico**, facilitando la visualización y consulta de ubicaciones geográficas durante la ejecución de operaciones en campo.

La aplicación funciona directamente desde el navegador y automatiza gran parte del proceso de preparación, generación y distribución de los mapas.

---

## 🎯 ¿Qué problema resuelve?

Cuando la información de operaciones se encuentra distribuida en archivos Excel, preparar manualmente un mapa individual para cada técnico puede requerir una cantidad considerable de tiempo y aumentar el riesgo de errores.

GeoTracker-Pro automatiza este proceso:

```text
Archivo Excel
     ↓
Lectura y procesamiento de datos
     ↓
Identificación de técnicos y coordenadas
     ↓
Generación de mapas individuales
     ↓
Organización de mapas
     ↓
Generación de enlaces
     ↓
Distribución a los técnicos
```

El objetivo es reducir tareas repetitivas y facilitar el acceso a la información geográfica necesaria para el trabajo en campo.

---

## 🚀 Características principales

### 🗺️ Generación de mapas

* Procesamiento de archivos Excel desde el navegador.
* Detección de información geográfica.
* Generación de mapas interactivos individuales.
* Organización de operaciones por técnico.
* Visualización de múltiples puntos geográficos.

### 📍 Información geográfica

Cada mapa permite visualizar las diferentes operaciones mediante marcadores sobre el mapa.

Los puntos pueden utilizar coordenadas geográficas para representar las ubicaciones correspondientes.

### 📱 Navegación

Los mapas permiten utilizar servicios externos de navegación para facilitar el desplazamiento hacia una ubicación determinada.

Se incluyen accesos a:

* Google Maps
* Waze

### 📸 Información de referencia

La aplicación permite utilizar información adicional asociada a las operaciones para facilitar la consulta de referencias visuales desde los mapas.

### 📦 Generación de paquetes

GeoTracker-Pro puede generar un paquete con los mapas creados y una página de enlaces para facilitar su distribución.

El paquete puede contener:

```text
mapas/
├── mapa_tecnico_1.html
├── mapa_tecnico_2.html
├── mapa_tecnico_3.html
└── ...

links.html
```

Esto permite centralizar los mapas generados y facilitar el acceso individual a cada uno.

### 💾 Persistencia local

La aplicación utiliza `localStorage` del navegador para conservar determinada información durante la sesión de trabajo.

Esta funcionalidad permite mantener información localmente sin necesidad de implementar un servidor o una base de datos para el funcionamiento básico de la aplicación.

---

## 🧩 Componentes del proyecto

El proyecto está compuesto actualmente por dos aplicaciones principales:

### `Generador_Links_Mapas.html`

Herramienta encargada de generar una lista de enlaces a partir de los nombres de los mapas disponibles.

Permite:

1. Recibir la lista de archivos HTML.
2. Identificar el técnico correspondiente.
3. Asociar el archivo con el técnico.
4. Generar un archivo Excel con los resultados.
5. Crear los enlaces correspondientes a los mapas publicados.

---

### `mapa-tecnicos-v14final.html`

Aplicación principal encargada de procesar los archivos de datos y generar los mapas interactivos.

Entre sus responsabilidades se encuentran:

* Carga de archivos Excel.
* Procesamiento de información.
* Identificación de coordenadas.
* Generación de marcadores.
* Visualización de operaciones.
* Integración con servicios de navegación.
* Generación de mapas individuales.
* Generación de paquetes ZIP.

---

## 🛠️ Tecnologías utilizadas

### Frontend

* HTML5
* CSS3
* JavaScript

### Librerías y servicios

* [Leaflet](https://leafletjs.com/) — visualización de mapas interactivos.
* [SheetJS](https://sheetjs.com/) — lectura y procesamiento de archivos Excel.
* [JSZip](https://stuk.github.io/jszip/) — generación de archivos ZIP.
* OpenStreetMap — información cartográfica.
* Google Maps — navegación hacia coordenadas.
* Waze — navegación hacia coordenadas.

### Almacenamiento local

* `localStorage`

La aplicación funciona principalmente del lado del cliente (**client-side**), reduciendo la necesidad de infraestructura backend para su funcionamiento.

---

## 📁 Estructura del proyecto

```text
GeoTracker-Pro/
│
├── .gitignore
│
├── app/
│   ├── Generador_Links_Mapas.html
│   └── mapa-tecnicos-v14final.html
│
├── demo/
│
└── scripts/
```

### `app/`

Contiene las aplicaciones principales del proyecto.

### `demo/`

Espacio destinado a datos y ejemplos ficticios para demostración pública del proyecto.

### `scripts/`

Contiene scripts auxiliares relacionados con tareas de mantenimiento y administración del proyecto.

---

## ▶️ Uso

GeoTracker-Pro está diseñado para ejecutarse directamente desde un navegador web moderno.

### Generación de mapas

1. Abrir la aplicación principal.
2. Cargar el archivo Excel correspondiente.
3. Revisar los datos detectados.
4. Procesar la información.
5. Generar los mapas.
6. Revisar los mapas generados.
7. Generar el paquete de mapas si es necesario.

### Generación de enlaces

1. Obtener la lista de archivos HTML generados.
2. Abrir `Generador_Links_Mapas.html`.
3. Pegar la lista de archivos.
4. Procesar los nombres de los mapas.
5. Generar el archivo Excel de enlaces.
6. Utilizar los enlaces generados para distribuir los mapas.

---

## 🔐 Privacidad y seguridad

La versión pública de este repositorio está preparada para demostración y portafolio.

No se incluyen:

* Datos personales reales.
* Números de identificación.
* Mapas reales de técnicos.
* Archivos operativos internos.
* Credenciales.
* Tokens.
* Contraseñas.
* Información confidencial.

Los datos utilizados para demostraciones públicas deben ser ficticios o estar anonimizados.

---

## 🌐 Arquitectura

GeoTracker-Pro utiliza una arquitectura principalmente **client-side**:

```text
┌─────────────────────────────┐
│        Usuario              │
│        Navegador            │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│      GeoTracker-Pro         │
│                             │
│ HTML + CSS + JavaScript     │
└──────────────┬──────────────┘
               │
       ┌───────┼────────┐
       ▼       ▼        ▼
    Excel    Mapas    Archivos
   SheetJS   Leaflet    ZIP
       │       │        │
       └───────┼────────┘
               ▼
       Información geográfica
               │
       ┌───────┴────────┐
       ▼                ▼
 Google Maps           Waze
```

Esta arquitectura permite ejecutar gran parte del procesamiento directamente en el equipo del usuario.

---

## 💡 Objetivo del proyecto

El objetivo de GeoTracker-Pro es demostrar cómo una tarea operativa repetitiva puede convertirse en un flujo automatizado mediante tecnologías web.

El proyecto combina:

* Automatización de procesos.
* Procesamiento de archivos.
* JavaScript.
* Visualización geográfica.
* Generación dinámica de contenido.
* Manipulación de archivos.
* Integración con servicios externos.

Además, busca servir como ejemplo de una solución desarrollada con tecnologías web sin depender obligatoriamente de un backend para las funciones principales.

---

## 🔮 Próximas mejoras

Algunas mejoras previstas para futuras versiones:

* [ ] Crear una demostración pública con datos ficticios.
* [ ] Mejorar la documentación técnica.
* [ ] Añadir capturas de pantalla del funcionamiento.
* [ ] Mejorar la estructura interna del proyecto.
* [ ] Incorporar validaciones adicionales de archivos.
* [ ] Añadir estadísticas sobre los mapas generados.
* [ ] Mejorar la experiencia de usuario.
* [ ] Automatizar aún más el proceso de distribución de enlaces.

---

## 👨‍💻 Autor

**Luis Alejandro Gamboa Hernández**

Proyecto desarrollado como parte de mi proceso de formación y experiencia en desarrollo de software y automatización de procesos.

### Áreas aplicadas

* Desarrollo web
* JavaScript
* Automatización
* Procesamiento de datos
* Sistemas de información geográfica
* Manipulación de archivos Excel
* Optimización de procesos

---

## 📄 Licencia

Este proyecto se encuentra publicado con fines de demostración y portafolio profesional.

El uso, modificación o redistribución del proyecto debe respetar las condiciones establecidas por el autor.
