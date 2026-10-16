# Fase 4 · Recursos · <estudio>
## Introducción
## 1. Las personas
### Roles técnicos
  | Persona | Rol | De qué responde |
### Responsables por módulo
  | Módulo | Requisitos (RF) | Responsable | Apoyo |
  | FRONTEND LEAD |  | Daniel | Indalecio |
  | BACKEND LEAD |  | Indalecio | Cristian |
  | DATABASE MANAGER |  | Cristian | Jordi |
  | DESPLIEGUE |  | Jordi | Daniel |
### Comunicación     (enlace al contrato)

## 2. La tecnología
### Stack, servicios y APIs   (enlace a la fase 2)

### Herramientas de desarrollo
Como IDE vamos a usar Visual Studio Code v.1.142, aunque si vemos que es necesario cambiaremos a uno más potente como IntelliJ IDEA.

Misma versión de Node.js para los cuatro, en este caso optamos por v24.22.0 siendo la última versión Long Time Support en el momento en el que redactamos el apartado de herramientas.

Testeo de API con Postman 12.32.4.0 y los test se harán con Vitest v5.0.5 y Supertest v7.3.1.

## 3. La gestión
### Tablero
[Tablero del proyecto](https://github.com/users/ccarjim2909/projects/7)
### Ramas
- main
- develop
- features
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
│   │   └── 02-viabilidad-tecnica.md
│   └── CONTRATO.md           # Acuerdo o contrato del equipo
├── server/
│   └── README.md             # Documentación del lado del servidor
├── .gitignore                # Archivos y carpetas excluidos de Git
└── README.md                 # Presentación general del proyecto
```
