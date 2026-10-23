# Fase 4 · Recursos · <estudio>

## Introducción
Este documento detalla la asignación de recursos humanos y técnicos del equipo. Daniel, Indalecio, Cristian y Jordi desarrollan el proyecto distribuyéndose los módulos clave mediante un entorno basado en Node.js, Visual Studio Code y control de versiones en GitHub.

## 1. Las personas
### Roles técnicos

| Persona | Rol | De qué responde |
|---|---|---|
| **Daniel** | Diseño | UI / UX |
| **Indalecio** | Programación | Código y API |
| **Cristian** | Arquitectura software | Estructura y modelo datos |
| **Jordi** | Mantenimiento | CI / CD |

### Responsables por módulo

| Módulo | Requisitos (RF) | Responsable | Apoyo |
|---|---|---|---|
| **FRONTEND LEAD** | Vistas e interfaz gráfica, integración API | Daniel | Indalecio |
| **BACKEND LEAD** | API RESTful y lógica | Indalecio | Cristian |
| **DATABASE MANAGER** | Esquemas, integridad y consultas | Cristian | Jordi |
| **DESPLIEGUE** | Automatización CI/CD, configuración server | Jordi | Daniel |

### Comunicación
Ver [Contrato de equipo](../CONTRATO.md). El canal principal será WhatsApp para respuestas rápidas y alertas "@all" en emergencias.

## 2. La tecnología
### Stack, servicios y APIs
Ver [Fase 2 · Requisitos técnicos](02-viabilidad-tecnica.md#2-requisitos-técnicos).

### Herramientas de desarrollo

| Para qué | Herramienta |
|---|---|
| Editor y estilo | Visual Studio Code v.1.142 (Alternativa: IntelliJ IDEA) |
| Versión de Node | Node.js v24.22.0 (LTS) |
| Probar la API | Postman v12.32.4.0 |
| Tests | Vitest v5.0.5 y Supertest v7.3.1 |

## 3. La gestión
### Tablero
Ver nuestro [Tablero del proyecto](https://github.com/users/ccarjim2909/projects/7) en GitHub Projects para realizar el seguimiento de tareas e Issues.

### Ramas
* `main`: Código de producción completamente estable y testeado. Protegida contra pushes directos.
* `develop`: Integración de características terminadas. Base para las pruebas conjuntas.
* `feature/*`: Ramas individuales de trabajo para cada nueva funcionalidad antes del Pull Request.

### Estructura de carpetas
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
```
