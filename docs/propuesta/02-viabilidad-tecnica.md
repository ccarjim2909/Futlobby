# 1.  Análisis de requisitos funcionales.

### Funcionalidades Principales

1.  El usuario puede registrarse con un perfil de jugador .

2.  El usuario puede iniciar/cerrar sesión.

3.  El usuario puede crear un partido especificando fecha, hora, ubicación, tipo de fútbol (F5/F7) y plazas disponibles.

4.  El usuario puede definir el precio total del campo y la cuota individual por jugador.

5.  El usuario puede buscar partidos públicos filtrando por ciudad/zona, fecha, horario y nivel requerido.

6.  El usuario puede unirse a un partido público disponible realizando el pago de la plaza individual.

7.  El usuario puede cancelar la inscripción a un partido dentro del margen de tiempo permitido.

8.  El usuario puede valorar el nivel de juego de los rivales y compañeros al finalizar un partido.

9.  El usuario puede consultar el perfil de un jugador con su nivel medio ponderado y estadísticas básicas.

10. El usuario puede visualizar los partidos disponibles en una lista y en un mapa interactivo.

11. El usuario puede registrar polideportivos e instalaciones deportivas con sus campos disponibles.

12. El usuario puede reservar pistas de forma directa a través de la plataforma.

13. La aplicación envía de forma automática una notificación de decisión al organizador si quedan menos de 24 horas para el partido y el cupo mínimo de jugadores no se ha completado.

14. El usuario puede consultar el historial de partidos jugados y cobros/pagos realizados.

15. El usuario puede visualizar la clasificación y ranking local de jugadores por zona.

### Priorización MoSCoW

#### Must Have (Indispensables)

-   El usuario puede registrarse con un perfil de jugador 

-   El usuario puede iniciar/cerrar sesión.

-   El usuario con rol de organizador puede crear un partido especificando fecha, hora, ubicación manual de la pista (ya reservada externamente), tipo de fútbol (F5/F7) y plazas disponibles.

-   El usuario con rol de organizador puede definir el precio total del campo y la cuota individual por jugador.

-   El usuario puede buscar partidos públicos filtrando por ciudad/zona, fecha, horario y nivel requerido.

-   El usuario puede unirse a un partido público disponible realizando el pago con tarjeta (simulado con Stripe API). El dinero se retiene de manera segura en la plataforma hasta que se valide la realización del partido para evitar fraudes.


#### Should Have (Importantes)

-   El organizador puede cancelar la inscripción a un partido dentro del margen de tiempo permitido (24 horas).

-   El usuario puede visualizar los partidos disponibles en una lista.

-   La aplicación puede enviar notificaciones de confirmación, avisos de plaza cubierta o cancelaciones, esto se usara usando Resend.

-   El usuario puede valorar el nivel de juego de los rivales y compañeros al finalizar un partido.

-   El usuario puede consultar el perfil de un jugador con su nivel medio ponderado y estadísticas básicas.

-   Automatización mediante una tarea programada que, al faltar 24 horas para el partido si el cupo no está completo, envía una notificación por correo electrónico al organizador para que decida si sigue adelante o cancela (lo que activa la devolución automática de los fondos).

#### Could Have (Deseables)

-   El usuario puede registrar polideportivos e instalaciones deportivas con sus campos disponibles.

-   El usuario puede visualizar los partidos disponibles en una lista y en un mapa interactivo (implementado con Leaflet y OpenStreetMap).

-   El usuario puede filtrar partidos según nivel

-   El usuario puede consultar el historial de partidos jugados y cobros/pagos realizados.

#### Won't Have (Fuera de alcance para esta versión)

-   El usuario puede visualizar la clasificación y ranking local de jugadores por zona.

-   El usuario puede reservar pistas de forma directa a través de la plataforma.


#### MVP (Minimum Viable Product - Mínimo Producto Viable)

-   Registro e Inicio de sesión: El usuario crea su perfil de jugador y accede al menú principal.

-   Flujo del Organizador: El usuario crea un partido rellenando un formulario con los datos (Fecha, hora, ubicación del polideportivo donde ya reservó, tipo de fútbol y plazas).

-   Flujo del Jugador: El jugador busca partidos por su zona, selecciona el encuentro y realiza el pago con tarjeta mediante la pasarela en desarrollo. El dinero se registra y bloquea en el backend.


# 2.  Análisis de requisitos técnicos.


### Frontend (React SPA)

-   Navegación: react-router-dom para el enrutamiento del lado del cliente y la protección de rutas privadas (panel de usuario, creación de partidos).

-   Gestión de Estado Global: zustand para un control ligero del estado de la sesión autenticada y filtros activos de búsqueda.

-   Interfaz y Estilos: tailwindcss junto a componentes de shadcn/ui para construir rápidamente una interfaz adaptable.

-   Peticiones HTTP: axios configurado con interceptores para adjuntar automáticamente el token JWT en cada solicitud.

### Infraestructura y Despliegue

-   Frontend:  Vercel o Netlify. Plan Hobby/Free (Despliegue continuo con GitHub, SSL automático, 100 GB de transferencia mensual gratuita).

-   Backend:  Render (Plan Free Web Service, 512 MB RAM)

-   Base de datos:  MongoDB Atlas. Plan M0 Shared Cluster gratuito permanente


### Backend (Node.js + Express)

-   Autenticación y Autorización: Implementación de JSON Web Tokens (JWT) mediante cookies de tipo HttpOnly para evitar ataques XSS.

-   Control de Roles:

-   Jugador: Usuario base que busca, se une y valora partidos.

-   Organizador: Usuario que crea el evento y administra sus plazas.

-   Administrador: Gestión de reportes, usuarios y catálogo de centros deportivos.

-   Servicios Externos e Integraciones:

-   Resend / Nodemailer (Emails transaccionales): Envío de confirmaciones de reserva y recordatorios.

### Base de Datos (MongoDB + Mongoose)


#### Colección: Usuarios

| Campo | Tipo | Requerido | Notas / Restricciones |
| :--- | :--- | :--- | :--- |
| `id` | String | Sí | — |
| `nombre` | String | Sí | — |
| `email` | String | Sí | Único (`unique`) |
| `contraseñaHash` | String | Sí | — |
| `ciudad` | String | Sí | — |


#### Colección: Partidos

| Campo | Tipo | Requerido | Notas / Restricciones |
| :--- | :--- | :--- | :--- |
| `id_organizador` | ObjectId | Sí | Referencia a `Usuarios` `ìd` |
| `modo` | String | Sí | Valores permitidos: `'F5'`, `'F7'`, `'F11'` |
| `nombreLocalizacion` | String | Sí | Referencia a `Pistas` `nombre` |
| `direccionLocalizacion` | String | Sí | Referencia a `Pistas` `direccion` |
| `hora` | Date | Sí | — |
| `precioTotal` | Number | Sí | — |
| `precioPorJugador` | Number | Sí | — |
| `maximoJugadores` | Number | Sí | — |
| `jugadoresConfirmados` | Array | No | Array de jugadores inscritos |
| `estadoPago` | String | No | Valores: `'pendiente'`, `'pagado'` (Valor por defecto: `'pendiente'`) |
| `estado` | String | No | Valores: `'abierta'`, `'completa'`, `'cancelada'` (Valor por defecto: `'abierta'`) |


#### Colección: Pistas

| Campo | Tipo | Requerido | Notas / Restricciones |
| :--- | :--- | :--- | :--- |
| `id` | String | Sí | — |
| `nombre` | String | Sí | — |
| `direccion` | String | Sí | Único (`unique`) |
| `ciudad` | String | Sí | — |



| Nombre | Frontend | Backend | Base de datos | Despliegue |
| :--- | :--- | :--- | :--- |:--- |
| `Indalecio` | X |   |   | x |
| `Daniel` | X | x |   | x |
| `Cristian` | x | x | X | x |
| `Jordi` | x | x | X | x |



# 3.  Evaluación de capacidades del equipo.


### Inventario de habilidades

-   Cristian: Conocimientos apropiados de bases de datos relaciones y algunos de no relaciones, conocimientos de programación básicos, título de SMR.

-   Indalecio: Conocimientos en cálculo avanzado, programación orientada a objetos y git/github.

-   Jordi:Conocimientos básicos de programación, experiencia en base de datos relacionales, y básicos de github.

-   Daniel: conocimientos de Diseño, manejo de programas suite Adobe. Desarrollo de la identidad visual de la marca.


### Lagunas de conocimiento

El grupo necesita adquirir conocimientos de las herramientas principales (MERN), dado que acabamos de empezar el curso y carecemos de estos conocimientos, aunque vamos a investigar por nuestra cuenta.

### Viabilidad del proyecto

Parecía tener buena viabilidad, pero después de la charla con el profesor, hemos identificado una falla a resolver en cuanto al tema de los datos de los polideportivos, necesitaremos encontrar la disponibilidad de las pistas.

# 4.  Identificación de riesgos técnicos.

### Análisis de riesgos

-   Base de datos: privacidad de los jugadores, acceso a métodos de pago

-   Potencial abuso de la plataforma: reservar horarios de forma indiscriminada, no proporcionar información real sobre el nivel de habilidad, etc.

-   Que los usuarios reserven a la misma vez en nuestra página y en la página municipal del ayuntamiento.

-   Si por casualidad de la vida los participantes de un partido acaban entablando amistad un grupo grande, tal vez dejarían de usar la aplicación y se hablarian simplemente entre ellos

-   Que los usuarios que no estén muy familiarizados con la interfaz de la web, puedan llegar a tener dificultades a la hora de interactuar con la aplicación.

### Estrategia de mitigación

-   Proteger los datos personales mediante contraseñas cifradas, autenticación segura y permisos de acceso. Para los pagos, utilizar una pasarela externa y evitar almacenar información bancaria en nuestra base de datos.

-   Establecer límites de reservas por usuario, exigir el pago para confirmar las plazas y permitir valoraciones y reportes para detectar comportamientos inadecuados o niveles de juego falsos.

-   Comprobar si los polideportivos permiten consultar su disponibilidad en tiempo real mediante una API. Si no es posible, contactar con las instalaciones para buscar alternativas y mostrar claramente si una reserva está confirmada o pendiente.

-   Ofrecer funciones útiles para organizar partidos, gestionar pagos y repetir encuentros con amigos, además de facilitar la búsqueda de nuevos jugadores.

-   Diseñar una web intuitiva y adaptable a móviles, con procesos sencillos y mensajes claros. Realizar pruebas con usuarios para detectar y corregir problemas antes del lanzamiento.

Prioridad principal: Resolver la disponibilidad de las pistas deportivas, ya que es el mayor problema para la viabilidad del proyecto. También será fundamental garantizar la seguridad de los datos y evitar las reservas abusivas.
