# Fase 4 · Recursos · <estudio>
## Introducción
## 1. Las personas

### Roles técnicos 

<table>
  <thead>
    <tr>
      <th>Persona</th>
      <th>Rol</th>
      <th>De qué responde</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Daniel</strong></td>
      <td>Diseño</td>
      <td>UI / UX</td>
    </tr>
    <tr>
      <td><strong>Indalecio</strong></td>
      <td>Programación</td>
      <td>Código y API</td>
    </tr>
    <tr>
      <td><strong>Cristian</strong></td>
      <td>Arquitectura software</td>
      <td>Estructura y modelo datos</td>
    </tr>
    <tr>
      <td><strong>Jordi</strong></td>
      <td>Mantenimiento</td>
      <td>CI / CD</td>
    </tr>
  </tbody>
</table>
  
### Responsables por módulo  
<table>
  <thead>
    <tr>
      <th>Módulo</th>
      <th>Requisitos (RF)</th>
      <th>Responsable</th>
      <th>Apoyo</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>FRONTEND LEAD</strong></td>
      <td>Vistas e interfaz gráfica, integración API</td>
      <td>Daniel</td>
      <td>Indalecio</td>
    </tr>
    <tr>
      <td><strong>BACKEND LEAD</strong></td>
      <td>API RESTful y lógica</td>
      <td>Indalecio</td>
      <td>Cristian</td>
    </tr>
    <tr>
      <td><strong>DATABASE MANAGER</strong></td>
      <td>Esquemas, integridad y consultas</td>
      <td>Cristian</td>
      <td>Jordi</td>
    </tr>
    <tr>
      <td><strong>DESPLIEGUE</strong></td>
      <td>Automatización CI/CD, configuración server</td>
      <td>Jordi</td>
      <td>Daniel</td>
    </tr>
  </tbody>
</table>

### Comunicación

[Canales de comunicación estipulados en el contrato.](https://github.com/ccarjim2909/Montad-vuestro-estudio/blob/main/docs/CONTRATO.md#:~:text=Comunicaci%C3%B3n9)

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
