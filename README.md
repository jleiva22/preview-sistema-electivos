# Sistema de Gestión y Registro de Electivos Escolares

Este repositorio actúa como vitrina técnica y documentación de arquitectura para el sistema web de inscripción automatizada de asignaturas electivas, desarrollado para optimizar los procesos de matrícula y selección académica en una institución de educación media.

> **Nota de Confidencialidad:** El código fuente original de este proyecto se encuentra en un repositorio privado por razones de propiedad y seguridad de la institución. En este espacio público se detalla la documentación, decisiones de diseño, modelo de datos y capturas de la solución.

---

## El Desafío
El establecimiento educativo gestionaba la inscripción de asignaturas electivas de forma manual o mediante herramientas genéricas, lo que generaba duplicidad de datos, colisiones de cupos, falta de trazabilidad y una alta carga administrativa.

**Objetivo:** Desarrollar una plataforma web centralizada que automatizara el proceso de postulación y asignación de electivos, asegurando una experiencia intuitiva para los estudiantes y un panel de control eficiente para los administradores de la institución.

---

## 🛠️ Stack Tecnológico Utilizado

El proyecto fue construido bajo una arquitectura Monolítica Elegante utilizando las siguientes tecnologías:

*   **Backend:** Laravel (PHP) - Aprovechando su robusto sistema de enrutamiento, ORM (Eloquent), middlewares de seguridad y sistema de migraciones.
*   **Base de Datos:** MariaDB / MySQL - Diseñada de forma relacional para garantizar la integridad referencial de las inscripciones.
*   **Frontend:** Blade Templates estructurado con componentes dinámicos y estilizado mediante CSS/Tailwind (para asegurar un diseño responsivo y accesible desde dispositivos móviles).
*   **Control de Versiones:** Git & GitHub.

---

## 🏗️ Arquitectura y Componentes Clave

### 1. Modelo de Datos (Esquema Relacional)
La base de datos fue normalizada para soportar las reglas de negocio del colegio. Las entidades principales incluyen:
*   `Users` (Roles diferenciados: Administradores, Profesores, Estudiantes).
*   `Electives` (Asignaturas, cupos máximos, descripción, profesor a cargo).
*   `Enrollments` (Tabla pivote con control de marcas de tiempo para registrar la postulación exacta).

### 2. Características Principales Implementadas
*   **Autenticación y Roles:** Control de acceso mediante Middlewares para asegurar que los estudiantes solo accedan a sus formularios de inscripción y los administradores a las métricas.
*   **Control de Concurrencia y Cupos:** Implementación de lógica a nivel de backend para verificar la disponibilidad de cupos en tiempo real *antes* de confirmar la inscripción, evitando la sobreventa de cupos en asignaturas de alta demanda.
*   **Panel de Administración (Dashboard):** Visualización del estado de las inscripciones, reportes de alumnos rezagados y exportación de listas de cursos.

---

## 🎯 Aprendizajes y Desafíos Técnicos

*   **Gestión de Concurrencia:** Uno de los mayores retos fue prever el escenario de cientos de estudiantes intentando inscribirse al mismo tiempo al abrirse el proceso. Se refinó la lógica de validación de Laravel para procesar las peticiones de forma segura y eficiente.
*   **Lógica de Negocio Flexible:** Diseñar el sistema pensando en que los requisitos de los electivos cambian año a año, permitiendo a los administradores crear, editar o pausar asignaturas de manera dinámica desde la interfaz sin alterar el código base.

---

## 📸 Demostración Visual

### Panel Principal del Estudiante
![Vista Estudiante](img/vista-alumno1.png)

### Panel de Postulacion del Estudiante
![Vista Estudiante](img/vista-alumno-2.png)
*Interfaz limpia enfocada en la facilidad de uso para el alumno.*

### Dashboard del Super Administrador
![Vista SuperAdmin](img/super-admin-dashboard.png)

### Panel de procesos de postulacion - Admin y SuperAdmin
![Vista Postulacion](img/panel-postulacion.png)

### Panel de configuracion para Areas, sectores y electivos
![Config Procesos](img/Config-Areas-y-electivos.png)

### Tabla de Logs SuperAdmin
![Tabla logs](img/tabla-logs.png)
---

## ✉️ Contacto y Demostración en Vivo
Si deseas conocer más detalles sobre la implementación del código, la optimización de las consultas SQL con Eloquent o ver una demostración guiada de la plataforma en funcionamiento, no dudes en contactarme.
