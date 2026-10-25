# Presupuesto

## Introducción

Este documento está creado con la intención de extender con las tareas del módulo de proyecto.

## 1- Análisis de costes reales.

- Se actualiza al acabar cada sprint el documento con un seguimiento de las horas empleadas en cada tarea.

### Para llevar un control preciso por sprints, necesitamos llevar este coste anual a un coste por hora:
- Horas laborales teóricas al año: Tomando una jornada completa estándar de 40 horas semanales (aprox. 1.800 horas anuales descontando vacaciones y festivos).
- Coste por hora bruta teórica:
34.000€ / 1.800 = 18,89 €/hora

- Estimando un coeficiente de eficiencia/deductibilidad real del 75% (unas 1.350 horas netas productivas al año dedicadas directamente a tareas de desarrollo y sprints):
Coste por hora efectiva real:
34.000€ / 1.350 = 25,18 €/hora

### Costes fijos;
Vamos a realizar un desbglose básico de los costes fijos de materiales para que un programador tenga los recursos necesarios para llevar a cabo el trabajo planteado.

| Categoría | Descripción / Detalle | Coste Anual |
| --- | --- | --- |
| **Hardware (Amortizado)** | Portátil de desarrollo (ej. MacBook Pro o PC equivalente de gama media-alta, amortizado a 3 años: 1.200 € / 3) | 400 € |
| **Periféricos** | Monitor externo (27"), teclado, ratón, cascos con cancelación de ruido (amortizado a 3 años) | 150 € |
| **Licencias de Software & IDEs** | Licencias corporativas (JetBrains, GitHub Copilot, Jira/Confluence, Slack, paquete ofimática, etc.) | 600 € |
| **Infraestructura Cloud / Entornos** | Parte proporcional de entornos de desarrollo, bases de datos de prueba, servidores de integración continua (CI/CD) | 450 € |
| **Gastos Generales / Oficina** | Puesto físico en oficina (alquiler, luz, internet, café) o compensación por teletrabajo | 1.200 € |
| **TOTAL MATERIALES / OVERHEAD** | **Suma de costes fijos no salariales por año** | **2.800 €** |
  

## 2- Costes totales del proyecto
Se planteará el coste de desarrollo de cada sprint con una aproximación de la carga de trabajo de cada uno de ellos.

| Hito / Sprint | Fechas del Sprint | Horas Efectivas Aprox. | Coste del Sprint (Personal + Materiales) | Coste Acumulado Total |
| --- | --- | --- | --- | --- |
| **Sprint 1** | Finaliza 13 de marzo | ~52 h | 1.326,15 € | 1.326,15 € |
| **Sprint 2** | Finaliza 27 de marzo | ~52 h | 1.326,15 € | 2.652,30 € |
| **Sprint 3** | Finaliza 10 de abril | ~52 h | 1.326,15 € | 3.978,45 € |
| **Sprint 4** | Finaliza 24 de abril | ~52 h | 1.326,15 € | 5.304,60 € |
| **Sprint 5** | Finaliza 8 de mayo | ~52 h | 1.326,15 € | 6.630,75 € |
| **Sprint 6 (Último)** | Finaliza 22 de mayo | ~52 h | 1.326,15 € | **7.956,90 €** |

### Costes fijos:

| Categoría | Descripción / Detalle | Coste Anual |
| --- | --- | --- |
| **Hardware (Amortizado)** | Portátil de desarrollo (ej. MacBook Pro o PC equivalente de gama media-alta, amortizado a 3 años: 1.200 € / 3) | 400 € |
| **Periféricos** | Monitor externo (27"), teclado, ratón, cascos con cancelación de ruido (amortizado a 3 años) | 150 € |
| **Licencias de Software & IDEs** | Licencias corporativas (JetBrains, GitHub Copilot, Jira/Confluence, Slack, paquete ofimática, etc.) | 600 € |
| **Infraestructura Cloud / Entornos** | Parte proporcional de entornos de desarrollo, bases de datos de prueba, servidores de integración continua (CI/CD) | 450 € |
| **Gastos Generales / Oficina** | Puesto físico en oficina (alquiler, luz, internet, café) o compensación por teletrabajo | 1.200 € |
| **TOTAL MATERIALES / OVERHEAD** | **Suma de costes fijos no salariales por año** | **2.800 €** |

En esta tabla representamos los costes finales del desarrollo con los costes fijos y variables.

| Concepto | Coste Unitario (1 dev) | Coste Total Equipo (4 devs) |
| --- | --- | --- |
| **Costes Salariales Directos (Sueldo + SS)** | 7.310,76 € | 29.243,04 € |
| **Materiales, Licencias y Overhead (Prorrata 12 sem.)** | 646,14 € | 2.584,56 € |
| **COSTE TOTAL DEL DESARROLLO (6 Sprints)** | **7.956,90 €** | **31.827,60 €** |
## Retorno de inversión (ROI): 

Para este tipo de aplicación (similar a Padel Mates, Timpik, Playtomic o MatchApp), el modelo más efectivo combina:Comisión por jugador/partido (Take Rate): 

- Se cobra una pequeña comisión de gestión por cada plaza reservada (ej. 0,50 € / jugador / partido).
- Suscripción Premium / Pase de Juego (Opcional): Jugadores frecuentes pagan una tarifa mensual (ej. 3,99 €/mes) para evitar comisiones por partido y tener reserva prioritaria.
- Comisión de Instalaciones/Campos: Comisión por reserva del campo completo gestionado a través de la app con centros deportivos afiliados.

Para simplificar la simulación, basaremos el cálculo en la métrica clave: 
- Ingreso Medio por Partido Organizado y Monetizado (promedio de 1,50 € a 2,50 € netos por partido de 10-14 jugadores).
-
## 2. Escenarios de Recuperación de la Inversión (Payback)

- Inversión Inicial a Recuperar: 31.827,60 €(Asumiendo un coste mensual recurrente posterior de servidores/mantenimiento de ~300 €/mes). 
### Escenario Optimista: Crecimiento Rápido:
- Fuerte adopción local (una o dos ciudades grandes), alianzas iniciales con campos de fútbol sintético y boca a boca entre comunidades de futbolistas.Métricas Clave:Meses 1 - 3: 300 partidos/mes > Ingreso neto: ~600 €/mes 4 - 6: 1.200 partidos/mes + Suscripciones > Ingreso neto: ~2.800 €/mesMeses 7 - 12: 3.000 partidos/mes + Publicidad/Sponsors > Ingreso neto: ~6.500 €/mesIngresos Acumulados Año 1: ~50.000 € (descontando costes de infraestructura).Tiempo de recuperación (Payback): ~9 a 10 meses.
### Moderado:
- Penetración progresiva en una sola ciudad. Requiere esfuerzo constante de captación de usuarios (retención y creación de comunidad).Métricas Clave:Meses 1 - 3: 80 partidos/mes > Ingreso neto: ~160 €/mesMeses 4 - 6: 350 partidos/mes > Ingreso neto: ~750 €/mesMeses 7 - 12: 900 partidos/mes + Suscripciones > Ingreso neto: ~2.100 €/mesAño 2: 1.800 partidos/mes > Ingreso neto: ~3.800 €/mes. Ingresos Acumulados Año 1: ~15.000 €Tiempo de recuperación (Payback): ~18 a 22 meses (Año y medio aprox.).

### Escenario Pesimista: 
- Adopción Lenta / Fricción InicialPremisa: Problema del "huevo y la gallina" (si no hay bastantes usuarios buscando partido, los pocos que entran no encuentran partida y abandonan). Pocas conversiones a pago.Métricas Clave:Meses 1 - 6: 40 partidos/mes Ingreso neto: ~80 €/mesMeses 7 - 12: 150 partidos/mes > Ingreso neto: ~320 €/mesAño 2: 400 partidos/mes > Ingreso neto: ~900 €/mesIngresos Acumulados Año 1: ~2.400 €Tiempo de recuperación (Payback): > 36 a 42 meses (3 a 3,5 años) o necesidad de reestructurar la estrategia de monetización.

Lecciones aprendidas sobre gestión económica:

¿Fueron precisas las estimaciones iniciales?
¿Qué tareas costaron más de lo esperado? ¿Por qué?
Hubo costes imprevistos?
¿Qué haríais diferente en un próximo proyecto?

Documentación final:

Actualizad /docs/presupuesto.md con:
Tabla de costes reales por sprint.
Coste total del proyecto.
Comparación estimación inicial vs. coste real.
Análisis de desviaciones.
Valoración del producto y análisis de ROI.
Lecciones aprendidas.
