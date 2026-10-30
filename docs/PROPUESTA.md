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
Para consultar los objetivos generales, específicos, las funcionalidades del MVP y los límites establecidos para el proyecto, accede al siguiente documento:
[docs/propuesta/03-objetivos-y-alcance.md](propuesta/03-objetivos-y-alcance.md)

## 4. Recursos
Para consultar la matriz de responsabilidades, los roles técnicos del equipo, las herramientas de desarrollo validadas y el plan de gestión de ramas/tableros, accede al siguiente documento:
[docs/propuesta/04-recursos.md](propuesta/04-recursos.md)
