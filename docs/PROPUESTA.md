# Propuesta de proyecto · Futlobby

**Integrantes:** Daniel, Indalecio, Cristian y Jordi  
**Fecha:** Octubre 2026

## Índice
1. [Introducción](#introducción)
2. [El problema](#1-el-problema)
3. [Viabilidad técnica](#2-viabilidad-técnica)
4. [Objetivos y alcance](#3-objetivos-y-alcance)
5. [Recursos](#4-recursos)

## Introducción
Este proyecto nace para resolver las dificultades organizativas y de gestión a las que se enfrentan los equipos de desarrollo al coordinar sus entornos de trabajo y metodologías. Dirigido tanto a estudiantes como a profesionales del sector, la propuesta de valor radica en un ecosistema ágil y centralizado que optimiza el flujo de desarrollo de software. 

El MVP (Mínimo Producto Viable) se centra en una arquitectura cliente-servidor robusta que permite la gestión de tareas mediante flujos de trabajo automatizados, un sistema de calidad restrictivo y un control de versiones unificado. El stack tecnológico está fundamentado en Node.js para el ecosistema general, empleando herramientas modernas como Vitest, Supertest y Postman para asegurar la integridad de la API RESTful. Los objetivos principales son garantizar una entrega de software consistente, minimizar los tiempos de bloqueo del equipo y mantener un estándar de calidad común. El equipo se compone de cuatro perfiles técnicos especializados: Daniel (Diseño UI/UX), Indalecio (Programación y API), Cristian (Arquitectura y Modelado de Datos) y Jordi (Mantenimiento e infraestructura CI/CD).

## 1. El problema
Para consultar el análisis detallado del problema, el público objetivo y la justificación del proyecto, accede al siguiente documento:
[docs/propuesta/01-problema.md](propuesta/01-problema.md)

## 2. Viabilidad técnica
Para consultar el análisis del stack tecnológico, las justificaciones de las herramientas de desarrollo elegidas y los requisitos del sistema, accede al siguiente documento:
[docs/propuesta/02-viabilidad-tecnica.md](propuesta/02-viabilidad-tecnica.md)

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
