# Necesidades de Financiación 

## Introducción
Este documento analiza los costes iniciales de puesta en marcha, la infraestructura técnica, el capital de trabajo y las fuentes de financiación disponibles para garantizar la viabilidad operativa y comercial del proyecto, conectándolo directamente con el presupuesto de desarrollo calculado de **31.827,60 €** para el equipo de 4 desarrolladores en 6 sprints.

---

## 1. Costes iniciales de desarrollo y modelo de asunción
- **Coste total de desarrollo (calculado en el presupuesto de 6 sprints):** 
  * El coste global del desarrollo asciende a **31.827,60 €**.
- **Afrontamiento sin financiación externa tradicional:**
  * **Sí.** Al tratarse de un proyecto académico y de *startup* inicial desarrollado por el propio equipo fundado (modalidad de *bootstrapping* y aportación de trabajo en equipo), el coste salarial directo es asumido inicialmente mediante "sweat equity" (capital en forma de trabajo). No requiere desembolso de caja inmediato para salarios, permitiendo enfocar la financiación externa o propia exclusivamente en los costes de infraestructura, marketing y lanzamiento.

---

## 2. Costes de infraestructura y servicios (Estimación mensual y anual)

| Concepto | Proveedor / Servicio | Plan / Uso | Coste Mensual Estimado | Coste Anual Estimado |
| :--- | :--- | :--- | :--- | :--- |
| **Hosting Backend** | Render | Web Service (Starter Plan - evita el spin-down de 512MB RAM) | ~7,00 € | 84,00 € |
| **Hosting Frontend** | Vercel | Plan Hobby / Pro (Gratuito en fases iniciales) | 0,00 € (Inicial) | 0,00 € |
| **Base de Datos** | MongoDB Atlas | Cluster M10 / Shared M2-M5 (Transacciones atómicas e inscripciones concurrentes) | ~9,00 € | 108,00 € |
| **Dominio Web** | Namecheap / GoDaddy | Dominio `.es` (`futlobby.es`) | ~1,25 € | 15,00 € |
| **Emails Transaccionales** | Resend / SendGrid | Plan Free (hasta 3.000 emails/mes) -> Plan Starter | 0,00 € (Inicial) / 15,00 € | 0,00 € - 180,00 € |
| **Pasarela de Pagos** | Stripe API | Comisión por transacción exitosa (1,5% + 0,25 € por inscripción) | Variable | Variable |
| **Almacenamiento / CDN** | Cloudinary / AWS S3 | Gestión de avatares de usuario e imágenes de polideportivos | 0,00 € | 0,00 € |
| **Monitorización y Logs** | Sentry / Logtail | Plan Developer / Free Tier | 0,00 € | 0,00 € |
| **TOTAL INFRAESTRUCTURA MÍNIMA FIJA** | — | — | **~17,25 € / mes** | **~207,00 € / año** |

---

## 3. Costes de marketing y lanzamiento
- **Publicidad Inicial y Difusión Local:**
  * **Meta Ads (Instagram / Facebook):** Campañas segmentadas orientadas a futbolistas amateurs (18-35 años). Presupuesto estimado: **150,00 € / mes** durante los primeros 3 meses (Total: **450,00 €**).
  * **Marketing de Cartelería:** Impresión de pósteres con códigos QR para tablones de anuncios en polideportivos locales y campos de F7/F5. Presupuesto estimado: **50,00 €**.
- **Diseño de Marca e Identidad Visual:**
  * Asumido por el equipo interno (Frontend & UX/UI Lead). Coste directo de caja: **0,00 €**.

---

## 4. Capital de trabajo y fondo de emergencia
- **Operación sin ingresos netos iniciales:**
  * Se estima que la plataforma operará **mínimo 6 meses** en fase de tracción y captación de usuarios en la provincia de Cádiz antes de alcanzar el punto de equilibrio operativo (coincidiendo con el escenario moderado/optimista de recuperación de inversión del presupuesto).
- **Cálculo de Fondo de Emergencia (6 meses de operación):**
  * Gastos Fijos de Infraestructura (6 meses x 17,25 €) = **103,50 €**
  * Campaña de Marketing e Impresión local = **500,00 €**
  * Fondo para Tasas de Registro de Marca (OEPM) y contingencias legales = **196,50 €**
  * **TOTAL CAPITAL DE TRABAJO Y FONDO DE EMERGENCIA:** **800,00 €**

---

## 5. Análisis de fuentes de financiación

1. **Autofinanciación ("Bootstrapping" / Ahorros Personales):**
   * Ventajas: Control absoluto del proyecto, sin endeudamiento financiero y sin presiones de inversores externos en fase MVP.
   * Aplicabilidad: **Alta.** Los 800 € necesarios para arrancar la infraestructura y el marketing inicial se dividen equitativamente entre los 4 integrantes (200 € por socio).
2. **Ayudas y Subvenciones Públicas:**
   * Programas analizados: Enisa Jóvenes Emprendedores (inviable en fase inicial por requerir estructura societaria consolidada y coinversión elevada); programas locales de asesoramiento de la Junta de Andalucía y CADE para microempresas tecnológicas.
3. **Préstamos Bancarios / ICO:**
   * Evaluación: Descartados por exigir avales personales y devengar intereses sin demostrar tracción comercial previa en facturación.
4. **Aceleradoras / Business Angels:**
   * Evaluación: Se contemplan a medio plazo (a partir del año 1 o 2), una vez validadas las métricas de partidos organizados y monetizados en Cádiz estimadas en el análisis de ROI del presupuesto.

---

## 6. Plan de financiación propuesto y justificación

- **Capital Total a Captar / Invertir en Caja:** **800,00 €**
- **Fuente de Financiación Elegida:** **Autofinanciación (Bootstrapping / Aportación Socios).**
- **Justificación:**
  * Gracias a la optimización de costes de infraestructura cloud elegida (Render + MongoDB Atlas por ~17,25 €/mes) y a que el coste de desarrollo de 31.827,60 € hemos asumido que el desembolso real en efectivo se reduce al mínimo imprescindible.
  * Aportar 200 € por cada uno de los 4 miembros del equipo elimina la dependencia de capital externo y permite validar el modelo de negocio con total agilidad.

- **Desglose de Inversión del Capital Inicial (800,00 €):**
  1. **Infraestructura Fija (1 año de servidores, BD y dominio):** 207,00 € (26%)
  2. **Estrategia de Marketing y Lanzamiento (Cádiz y Bahía):** 450,00 € (56%)
  3. **Registro de Marca en la OEPM:** 125,00 € (16%)
  4. **Reserva de Contingencias Técnicas:** 18,00 € (2%)
