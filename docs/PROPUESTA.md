# Propuesta de proyecto · Futlobby

**Integrantes:** Daniel, Indalecio, Cristian y Jordi  
**Fecha:** Octubre 2026

## Índice
- [Propuesta de proyecto · Futlobby](#propuesta-de-proyecto--futlobby)
  - [Índice](#índice)
  - [Introducción](#introducción)
  - [1. El problema](#1-el-problema)
  - [2. Viabilidad técnica](#2-viabilidad-técnica)
  - [3. Objetivos y alcance](#3-objetivos-y-alcance)
  - [4. Recursos](#4-recursos)

## Introducción

Futlobby es una plataforma web orientada a la organización de partidos de fútbol. Nace con la idea de facilitar que cualquier persona pueda encontrar gente con la que jugar al fútbol, sin depender de tener un grupo de amigos suficientemente grande o disponible para organizar un partido.

La aplicación permitirá a los usuarios crear partidos públicos, indicar las características del encuentro y publicar las plazas disponibles para que otros jugadores puedan unirse y pagar su parte. De esta forma, se pretende reducir las dificultades que supone organizar un partido, encontrar sustitutos cuando alguien cancela y reunir jugadores con niveles de habilidad similares.

El proyecto está dirigido principalmente a dos perfiles: las personas que habitualmente organizan partidos y necesitan ayuda para completar sus equipos, y aquellas que quieren jugar al fútbol pero no disponen de un grupo de conocidos con el que hacerlo.

Nuestro objetivo es ofrecer una herramienta sencilla que facilite la organización de partidos y permita aprovechar mejor las instalaciones deportivas disponibles.

## 1. El problema

Organizar partidos de fútbol amateur puede resultar complicado cuando no todos los integrantes de un grupo tienen disponibilidad o cuando una persona quiere jugar, pero no dispone de suficientes conocidos para completar un equipo.

Esta situación provoca que los organizadores tengan que dedicar tiempo a buscar jugadores, gestionar confirmaciones y resolver cancelaciones de última hora. Además, las personas que no pertenecen a un grupo habitual tienen dificultades para encontrar partidos a los que incorporarse.

Futlobby busca solucionar estas dificultades mediante una plataforma donde los organizadores puedan publicar las plazas disponibles y otros jugadores puedan encontrar partidos cercanos, consultar sus características y unirse pagando su parte.

La propuesta también contempla un sistema de valoraciones del nivel de juego para facilitar que los participantes encuentren encuentros más equilibrados.

Los principales usuarios afectados son:

- El organizador: necesita completar los partidos y evitar perder dinero cuando alguien cancela.

- El jugador sin grupo: quiere seguir jugando al fútbol sin depender de tener un grupo de amigos disponible.

- Los centros deportivos: pueden beneficiarse de una mayor ocupación de sus instalaciones y de una comunidad de jugadores más activa.

Nuestra propuesta de valor consiste en simplificar la organización de partidos, facilitar la incorporación de nuevos jugadores y reducir los problemas derivados de las cancelaciones.

## 2. Viabilidad técnica

El desarrollo de Futlobby es técnicamente viable utilizando el stack MERN (MongoDB, Express, React y Node.js). Estas tecnologías permiten desarrollar una aplicación web completa, separando la interfaz de usuario, la lógica del servidor y el almacenamiento de datos.

El frontend se desarrollará con React, mientras que el backend utilizará Node.js y Express para ofrecer una API REST que gestione los usuarios, los partidos y las inscripciones. MongoDB permitirá almacenar la información mediante colecciones y documentos, utilizando Mongoose para definir los modelos y facilitar las operaciones con la base de datos.

Entre las funcionalidades principales del MVP se encuentran:

- Registro e inicio de sesión de usuarios.

- Creación de partidos por parte de los organizadores.

- Búsqueda y consulta de partidos públicos.

- Inscripción de jugadores en partidos disponibles.

- Gestión del pago individual mediante una pasarela de pago integrada en modo de pruebas.


El proyecto presenta algunos riesgos técnicos que tendremos que controlar durante su desarrollo. Entre ellos destacan la gestión de inscripciones simultáneas cuando queda una única plaza disponible, la integración de la pasarela de pago y la disponibilidad de las instalaciones deportivas, que inicialmente deberán reservarse de forma externa.

La pasarela de pago gestionará las operaciones de cobro y devolución según su funcionamiento. Futlobby no custodiará directamente el dinero de los usuarios.

En cuanto a la infraestructura, se utilizarán servicios con planes gratuitos como Vercel o Netlify para el frontend, Render para el backend y MongoDB Atlas para la base de datos.

Consideramos que el proyecto es viable dentro del tiempo disponible

## 3. Objetivos y alcance
### Introducción

En este documento se redacta los objetivos y alcance de nuestra aplicación
### 1. Objetivos
#### Objetivo general
Conseguir que un grupo de personas desconocidas puedan crear una sala para juegar al futbol
#### Objetivos específicos
| ID | Objetivo SMART | Qué se mide | Valor de éxito | Cómo se comprueba |
| :--- | :--- | :--- | :--- | :--- |
| 01 | Un usuario sea capaz de crear la sala para jugar el partido en menos de 2 minutos | El tiempo que tarda | Es capaz de hacerlo en el tiempo determinado | Con testers elegidos al azar |
| 02 | Un usuario sea capaz de unirse a la sala que desee en menos de 1 minuto | El tiempo que tarda | Es capaz de hacerlo en el tiempo determinado | Con testers elegidos al azar |
| 03 | El porcentaje de partidos cancelados sea menos del 20% | Porcentaje de partidos cancelados respecto al total de partidos creados | Menos del 20% de partidos cancelados | Comprobándolo al final del primer mes calculando cuántos se cancelaron de todos los que se crearon |
### 2. Alcance
#### El MVP
##### Recorrido
1. El usuario entra a la plataforma, se registra con su perfil de jugador e inicia sesión.
2. El usuario organizador crea un partido rellenando los datos del encuentro (fecha, hora, ubicación de la pista ya reservada externamente, tipo de fútbol y plazas) y definiendo el precio.
3. El jugador busca partidos por su zona, selecciona el encuentro deseado y realiza el pago con tarjeta mediante la pasarela integrada, bloqueando y registrando el dinero en el backend hasta completarse el cupo.
#### Plataforma
La plataforma que usaremos será el móvil ya que el desarrollo de una web responsiva con el stack MERN permite un despliegue inmediato en producción a través de Render y compatibilidad universal con cualquier sistema operativo.
#### Usuarios y datos
La estrategia de datos se rige por la consistencia, la geolocalización dirigida y la privacidad: 
- Usuarios y datos: Un primer piloto controlado de 22 usuarios dentro de la app.
- Usuarios strictly de la provincia de Cádiz, 
- Se almacenará exclusivamente: Nombre, correo electrónico, contraseña encriptada, nivel de juego y datos de los polideportivos.
#### Lo que no haremos
| Qué | Por qué |
| :--- | :--- |
| **Reserva de pistas en la aplicación** | Finalmente hemos decidido eliminar la opción de reserva dentro de la aplicación, esto hace que nuestra app sea una plataforma de organización de partidos. |
| **Algoritmo de Matchmaking basado en Inteligencia Artificial** | No se programará ya que la asignación de niveles se basará en filtros relacionales simples introducidos por el propio usuario. |
#### Ampliaciones futuras (lista numerada, en orden)
Si se dispusiera de más tiempo la primera idea a implementar sería:
- Un sistema de chat multimedia en tiempo real para que los jugadores puedan organizar bien los partidos dentro de nuestra aplicación.
- Sistema de Valoración Post-Partido (Match Rating): Mecanismo de reputación para puntuar la puntualidad y deportividad de los rivales, bloqueando la fuga a grupos de WhatsApp externos al retener el historial y nivel del jugador en nuestra plataforma. 

## 4. Recursos
### Introducción
Este documento detalla la asignación de recursos humanos y técnicos del equipo. Daniel, Indalecio, Cristian y Jordi desarrollan el proyecto distribuyéndose los módulos clave mediante un entorno basado en Node.js, Visual Studio Code y control de versiones en GitHub.

### 1. Las personas
#### Roles técnicos

| Persona | Rol | De qué responde |
|---|---|---|
| **Daniel** | Diseño | UI / UX |
| **Indalecio** | Programación | Código y API |
| **Cristian** | Arquitectura software | Estructura y modelo datos |
| **Jordi** | Mantenimiento | CI / CD |

#### Responsables por módulo

| Módulo | Requisitos (RF) | Responsable | Apoyo |
|---|---|---|---|
| **FRONTEND LEAD** | Vistas e interfaz gráfica, integración API | Daniel | Indalecio |
| **BACKEND LEAD** | API RESTful y lógica | Indalecio | Cristian |
| **DATABASE MANAGER** | Esquemas, integridad y consultas | Cristian | Jordi |
| **DESPLIEGUE** | Automatización CI/CD, configuración server | Jordi | Daniel |

#### Comunicación
Ver [Contrato de equipo](CONTRATO.md). El canal principal será WhatsApp para respuestas rápidas y alertas "@all" en emergencias.

### 2. La tecnología
#### Stack, servicios y APIs
Ver [Fase 2 · Requisitos técnicos](propuesta/02-viabilidad-tecnica.md#2-requisitos-técnicos).

#### Herramientas de desarrollo

| Para qué | Herramienta |
|---|---|
| Editor y estilo | Visual Studio Code v.1.142 (Alternativa: IntelliJ IDEA) |
| Versión de Node | Node.js v24.22.0 (LTS) |
| Probar la API | Postman v12.32.4.0 |
| Tests | Vitest v5.0.5 y Supertest v7.3.1 |

### 3. La gestión
#### Tablero
Ver nuestro [Tablero del proyecto](https://github.com/users/ccarjim2909/projects/7) en GitHub Projects para realizar el seguimiento de tareas e Issues.

#### Ramas
* `main`: Código de producción completamente estable y testeado. Protegida contra pushes directos.
* `develop`: Integración de características terminadas. Base para las pruebas conjuntas.
* `feature/*`: Ramas individuales de trabajo para cada nueva funcionalidad antes del Pull Request.

#### Estructura de carpetas
```text
├── .github/
│   └── ISSUE_TEMPLATE/       # Plantillas personalizadas para los Issues
├── client/
│   └── README.md             # Documentación del lado del cliente
├── docs/
│   ├── propuesta/
│   │   ├── 00-brainstorming.md
│   │   ├── 01-problema.md
│   │   ├── 02-viabilidad-tecnica.md
│   │   ├── 03-objetivos-y-alcance.md
│   │   └── 04-recursos.md
│   ├── PROPUESTA.md
│   └── CONTRATO.md           # Acuerdo o contrato del equipo
├── server/
│   └── README.md             # Documentación del lado del servidor
├── .gitignore                # Archivos y carpetas excluidos de Git
└── README.md                 # Presentación general del proyecto
