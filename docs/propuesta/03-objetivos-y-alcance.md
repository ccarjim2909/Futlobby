
# Fase 3 · Objetivos y alcance · <estudio>
## Introducción

En este documento se redacta los objetivos y alcance de nuestra aplicación
## 1. Objetivos
### Objetivo general
Conseguir que un grupo de personas desconocidas puedan crear una sala para juegar al futbol
### Objetivos específicos
| ID | Objetivo SMART | Qué se mide | Valor de éxito | Cómo se comprueba |
| :--- | :--- | :--- | :--- | :--- |
| 01 | Un usuario sea capaz de crear la sala para jugar el partido en menos de 2 minutos | El tiempo que tarda | Es capaz de hacerlo en el tiempo determinado | Con testers elegidos al azar |
| 02 | Un usuario sea capaz de unirse a la sala que desee en menos de 1 minuto | El tiempo que tarda | Es capaz de hacerlo en el tiempo determinado | Con testers elegidos al azar |
| 03 | El porcentaje de partidos cancelados sea menos del 20% | Porcentaje de partidos cancelados respecto al total de partidos creados | Menos del 20% de partidos cancelados | Comprobándolo al final del primer mes calculando cuántos se cancelaron de todos los que se crearon |
## 2. Alcance
### El MVP
[Enlace a la fase 2](docs/propuesta/03-objetivos-y-alcance.md)
### Plataforma
La plataforma que usaremos será el móvil ya que el desarrollo de una web responsiva con el stack MERN permite un despliegue inmediato en producción a través de Render y compatibilidad universal con cualquier sistema operativo.
### Usuarios y datos
La estrategia de datos se rige por la consistencia, la geolocalización dirigida y la privacidad: 
- Usuarios y datos: Un primer piloto controlado de 22 usuarios dentro de la app.
- Usuarios estrictamente de la provincia de Cádiz, 
- Se almacenará exclusivamente: Nombre, correo electrónico, contraseña encriptada, nivel de juego y datos de los polideportivos.
### Lo que no haremos
  | Qué | Por qué |  
  
Reserva de pistas en la aplicación:
  - Finalmente hemos decidido eliminar la opción de reserva dentro de la aplicación, esto hace que nuestra app sea una plataforma de organización de partidos

Algoritmo de Matchmaking basado en Inteligencia Artificial: 
  - No se programará ya que la asignación de niveles se basará en filtros relacionales simples introducidos por el propio usuario.
### Ampliaciones futuras   (lista numerada, en orden)
Si se dispusiera de más tiempo la primera idea a implementar sería:
- Un sistema de chat multimedia en tiempo real para que los jugadores puedan organizar bien los partidos dentro de nuestra aplicación.
- Sistema de Valoración Post-Partido (Match Rating): Mecanismo de reputación para puntuar la puntualidad y deportividad de los rivales, bloqueando la fuga a grupos de WhatsApp externos al retener el historial y nivel del jugador en nuestra plataforma. 
