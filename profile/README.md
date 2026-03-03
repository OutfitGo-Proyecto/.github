# 🚀 OutfitGo - Proyecto de Desarrollo Web (E-Commerce)

> **Plataforma E-Commerce Directa | Proyecto de Clase**

Este documento describe la visión, arquitectura y estructura del equipo para el desarrollo de la iteración final de **OutfitGo (Core Engine v2.0)**.

## 👥 El Equipo (Frontend & Backend)

OutfitGo es el resultado del esfuerzo conjunto de nuestro equipo para el proyecto de clase:
*   **Luis**
*   **Juan**
*   **Pablo**

## 🎯 Objetivo del Proyecto
Desarrollar una aplicación web moderna (SPA) que funcione como tienda de ropa directa. Hemos evolucionado de ser un agregador de precios a un **E-Commerce Directo**. El sistema cuenta con stock y precio propio para cada prenda, segmentación de audiencia y una experiencia de usuario increíblemente rápida.

*   **Propósito**: Crear una tienda online de ropa escalable y desplegada en la nube.
*   **Innovación**: Infraestructura Cloud Native y carga hiper-eficiente de relaciones complejas (Tallas, Colores, Categorías, Marcas).

## 🛠️ Stack Tecnológico (Arquitectura Headless)

El proyecto sigue una arquitectura **desacoplada CI/CD** para permitir el despliegue paralelo hacia nuestra instancia de Ubuntu en AWS.

### 🎨 Frontend (Interface & UX)
*   **Framework**: Angular 19.
*   **Enfoque**: Componentes Standalone, Componentes de Tarjetas de Producto Inteligentes.
*   **Regla de Negocio Front**: Manejo de `text-truncate` obligatorio, ya que las descripciones de las prendas enviadas por el backend miden siempre entre **300 y 500 caracteres**.

### ⚙️ Backend (Core Engine API)
*   **Framework**: Laravel 11 (API REST).
*   **Base de Datos**: MySQL 8.0 (con tablas pivot para tallajes dinámicos).
*   **Infraestructura**: Docker & Docker Compose en **AWS EC2**.
*   **Testing & CI**: Integración continua en `main` que despliega automáticamente a producción usando GitHub Actions y SCP.

## 🔄 Flujo de Trabajo y Sincronización

A lo largo del proyecto, Frontend y Backend nos sincronizamos de esta forma:
1.  **Endpoints Públicos**: Frontend consume la API RESTful en `http://34.229.141.169:8000/api/productos`.
2.  **CORS Abierto**: El Backend permite `[*]` en todos los orígenes para que podamos desarrollar en `localhost` simultáneamente sin bloqueos de red.
3.  **Pull Requests**: El código pasa por GitHub Actions. Si pasa la compilación en Frontend o los tests en Backend, se inyecta directamente vía SSH a Amazon Web Services.

## 📅 Roadmap de Hitos Alcanzados

*   [x] Diseño de Interfaz en Angular 19.
*   [x] Motor API Restful en Laravel 11.
*   [x] Migración Estructural Básica a E-commerce Directo (Precio y Stock Nativo).
*   [x] Segmentación Avanzada por Público (`adulto`, `infantil`, `unisex`) con sus respectivos tallajes coherentes generados desde Base de Datos.
*   [x] **Despliegues 100% Automatizados a Nube AWS EC2**.

---
*Desarrollado con ❤️ para nuestro proyecto de clase por Luis, Juan y Pablo.*
