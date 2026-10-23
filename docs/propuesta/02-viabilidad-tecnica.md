# Fase 2 · Viabilidad técnica · Futlobby

## Introducción
Para hacer realidad nuestra plataforma de organización de partidos de fútbol amateur, desarrollaremos un MVP funcional utilizando el stack MERN (MongoDB, Express, React y Node.js). Tras evaluar los recursos disponibles y las capacidades del equipo, el proyecto es viable técnicamente, aunque el riesgo principal radica en la gestión de la disponibilidad de las pistas y la sincronización en tiempo real de las inscripciones concurrentes de los jugadores.

## 1. Requisitos funcionales
| ID | Requisito | MoSCoW |
|---|---|---|
| RF-01 | El usuario puede registrarse con un perfil de jugador | Must |
| RF-02 | El usuario puede iniciar/cerrar sesión | Must |
| RF-03 | El usuario con rol de organizador puede crear un partido especificando fecha, hora, ubicación manual de la pista, tipo de fútbol y plazas | Must |
| RF-04 | El usuario con rol de organizador puede definir el precio total del campo y la cuota individual por jugador | Must |
| RF-05 | El usuario puede buscar partidos públicos filtrando por ciudad/zona, fecha, horario y nivel requerido | Must |
| RF-06 | El usuario puede unirse a un partido público disponible realizando el pago con tarjeta (simulado con Stripe API) reteniendo el dinero de forma segura | Must |
| RF-07 | El organizador puede cancelar la inscripción a un partido dentro del margen de tiempo permitido (24 horas) | Should |
| RF-08 | El usuario puede visualizar los partidos disponibles en una lista | Should |
| RF-09 | La aplicación puede enviar notificaciones de confirmación, avisos o cancelaciones usando Resend | Should |
| RF-10 | El usuario puede valorar el nivel de juego de los rivales y compañeros al finalizar un partido | Should |
| RF-11 | El usuario puede consultar el perfil de un jugador con su nivel medio ponderado y estadísticas básicas | Should |
| RF-12 | Automatización de tarea programada a las 24h del partido si el cupo no está completo para notificar al organizador | Should |
| RF-13 | El usuario puede registrar polideportivos e instalaciones deportivas con sus campos disponibles | Could |
| RF-14 | El usuario puede visualizar los partidos disponibles en una lista y en un mapa interactivo (Leaflet y OpenStreetMap) | Could |
| RF-15 | El usuario puede filtrar partidos según nivel | Could |
| RF-16 | El usuario puede consultar el historial de partidos jugados y cobros/pagos realizados | Could |
| RF-17 | El usuario puede visualizar la clasificación y ranking local de jugadores por zona | Won't |
| RF-18 | El usuario puede reservar pistas de forma directa a través de la plataforma | Won't |

### El MVP
#### Recorrido
1. El usuario entra a la plataforma, se registra con su perfil de jugador e inicia sesión.
2. El usuario organizador crea un partido rellenando los datos del encuentro (fecha, hora, ubicación de la pista ya reservada externamente, tipo de fútbol y plazas) y definiendo el precio.
3. El jugador busca partidos por su zona, selecciona el encuentro deseado y realiza el pago con tarjeta mediante la pasarela integrada, bloqueando y registrando el dinero en el backend hasta completarse el cupo.

#### Requisitos del MVP
- RF-01, RF-02, RF-03, RF-04, RF-05 y RF-06 (Todos los correspondientes a la categoría Must Have).

## 2. Requisitos técnicos
### Frontend
| Biblioteca | Para qué | Por qué esta |
|---|---|---|
| `react-router-dom` | Navegación SPA | Permite crear rutas dinámicas y vistas protegidas sin recargar la página. |
| `zustand` | Gestión de estado global | Solución ligera y sin boilerplate para almacenar datos de usuario y filtros. |
| `tailwindcss` + `shadcn/ui` | Interfaz y estilos | Clases de utilidad rápidas para maquetar directamente en el JSX. |
| `axios` | Peticiones HTTP | Simplifica peticiones frente a fetch y permite usar interceptores para el token JWT. |

### Backend
#### Autenticación y roles
- **Autenticación:** JSON Web Tokens (JWT) mediante cookies HttpOnly para prevenir ataques XSS.
- **Roles:** 
  - *Jugador:* Busca, se une y valora partidos.
  - *Organizador:* Crea eventos y administra plazas.
  - *Administrador:* Gestiona reportes, usuarios y centros deportivos.

#### Servicios externos
| Servicio | Para qué | Límite gratuito |
|---|---|---|
| Resend / Nodemailer | Envío de correos transaccionales (confirmaciones y recordatorios) | Plan gratuito disponible para correos transaccionales iniciales. |
| Stripe API | Simulación de pagos seguros y retención de fondos | Tarifa por transacción estándar / modo pruebas gratuito. |

### Base de datos
#### Colección: usuarios

| Campo | Tipo | Requerido | Notas / Restricciones |
| :--- | :--- | :--- | :--- |
| `_id` | ObjectId | Sí | Identificador único genérico |
| `nombre` | String | Sí | — |
| `email` | String | Sí | Único (`unique`) |
| `contraseñaHash` | String | Sí | — |
| `ciudad` | String | Sí | Permite filtrar/sugerir partidos locales |
| `nivel` | String | Sí | Ej. `'Principiante'`, `'Intermedio'`, `'Avanzado'` |


#### Colección: pistas

| Campo | Tipo | Requerido | Notas / Restricciones |
| :--- | :--- | :--- | :--- |
| `_id` | ObjectId | Sí | Identificador único genérico |
| `nombre` | String | Sí | — |
| `direccion` | String | Sí | — |
| `ciudad` | String | Sí | — |


#### Colección: partidos

| Campo | Tipo | Requerido | Notas / Restricciones |
| :--- | :--- | :--- | :--- |
| `_id` | ObjectId | Sí | Identificador único genérico |
| `organizador_id` | ObjectId | Sí | Referencia (`ref`) a `usuarios` |
| `pista_id` | ObjectId | Sí | Referencia (`ref`) a `pistas` |
| `ciudad` | String | Sí | Desnormalizado o derivado de la pista para búsquedas rápidas |
| `modo` | String | Sí | Valores: `'F5'`, `'F7'`, `'F11'` |
| `nivel` | String | Sí | Nivel requerido para el partido |
| `hora` | Date | Sí | Fecha y hora de inicio |
| `precioTotal` | Number | Sí | — |
| `precioPorJugador` | Number | Sí | — |
| `maximoJugadores` | Number | Sí | — |
| `jugadoresConfirmados` | Array[Object] | No | Subdocumentos para gestionar inscripciones e inscritos individuales |
| `jugadoresConfirmados.$.usuario_id` | ObjectId | Sí | Referencia (`ref`) a `usuarios` |
| `jugadoresConfirmados.$.estadoPago` | String | Sí | Valores: `'pendiente'`, `'pagado'` (Por defecto: `'pendiente'`) |
| `jugadoresConfirmados.$.fechaInscripcion` | Date | Sí | Fecha en la que se unió el jugador |
| `estado` | String | No | Valores: `'abierta'`, `'completa'`, `'cancelada'` (Por defecto: `'abierta'`) |


### Infraestructura
| Parte | Dónde se despliega | Condiciones del plan gratuito |
|---|---|---|
| Frontend | Vercel o Netlify | Plan Hobby/Free con despliegue continuo con GitHub, SSL automático y 100 GB/mes. |
| Backend | Render | Plan Free Web Service (512 MB RAM). Entra en suspensión tras 15 minutos de inactividad (tarda 30-50s en despertar). |
| Base de datos | MongoDB Atlas | Cluster gratuito permanente con límite estricto de 512 MB (requiere optimizar documentos y evitar archivos pesados). |

## 3. Capacidades del equipo
### Inventario
| Persona | React | Node + Express | MongoDB | Git |
|---|---|---|---|---|
| Indalecio | No | Sí | Sí | Sí |
| Daniel | Sí | No | No | Sí |
| Cristian | Sí | No | Sí | Sí |
| Jordi | No | Sí | No | Sí |

### Lagunas
El grupo carece de dominio avanzado en el stack MERN completo al haber empezado recientemente el curso, por lo que requerirá investigación independiente y tiempo de aprendizaje diario.

### ¿Es realista?
Sí, el proyecto es viable y realista tras acotar el alcance del MVP, aunque requiere resolver el problema de la disponibilidad de pistas externas y afianzar las capacidades técnicas del equipo en las dos primeras semanas.

## 4. Riesgos técnicos
| Riesgo | Tipo | Mitigación |
|---|---|---|
| Plazos de entrega y curva de aprendizaje MERN | Desarrollo / Tiempo | Reservar las dos últimas semanas exclusivamente para bugs/despliegue y dedicar tiempo diario al aprendizaje guiado. |
| Concurrencia (Dos usuarios reservando la última plaza a la vez) | Concurrencia en BD | Bloquear el documento del partido durante la actualización de plaza y aplicar restricciones atómicas. |
| Suspensión del servidor gratuito en Render | Infraestructura | Enviar peticiones HTTP periódicas o pings al servidor para evitar que entre en modo spin-down. |
| Falta de disponibilidad en tiempo real de las pistas deportivas | Negocio / Datos | Permitir la ubicación manual de pistas ya reservadas externamente y revisar alternativas para el futuro. |