# Stack Global de Bases de Datos by DigitAllFran

Este stack despliega un conjunto de bases de datos de alto rendimiento, diseñadas para servir como la **fundación centralizada** para múltiples aplicaciones y microservicios.

## Arquitectura y Estrategia

Este no es un simple conjunto de bases de datos; es el **arsenal de datos de tu ecosistema**. La estrategia es tener una única fuente de verdad para tus datos, accesible de forma segura y eficiente por tus otras aplicaciones (n8n, Chatwoot, etc.).

#### **Dependencia de Traefik (Indispensable para el Ecosistema)**

Si bien este stack puede funcionar solo, está diseñado para operar en conjunto con [**el stack de Traefik de DigitAllFran**](https://github.com/bicibikes15/Traefik). Al compartir la misma red (`digitallfran_net`), tus aplicaciones, que son expuestas al mundo a través de Traefik, pueden comunicarse con estas bases de datos de forma interna y segura, usando simplemente el nombre del contenedor (ej. `postgres_global`) como la dirección del host. Esta es la forma profesional y recomendada de estructurar tus servicios.

#### **Gestión con Portainer (Opcional)**

Para una gestión visual de todos tus contenedores, puedes usar [**el stack de Portainer de DigitAllFran**](https://github.com/bicibikes15/Portainer-Stack-Traefik). No es necesario para que las bases de datos funcionen, pero facilita enormemente la administración.

## Guerreros Incluidos en este Arsenal

-   **PostgreSQL (`postgres_global`):** El "General". Una base de datos relacional (SQL) robusta y versátil.
    * **Uso:** Ideal para la mayoría de tus aplicaciones que requieren datos estructurados y consistentes (ej. `n8n`, `Chatwoot`).
    * **Puerto:** `5432`

-   **PGVector (`pgvector_global`):** El "Rastreador". Una versión especializada de PostgreSQL para la era de la IA.
    * **Uso:** Indispensable para proyectos que involucran inteligencia artificial, embeddings, y búsqueda por similitud o semántica.
    * **Puerto:** `5433`

-   **Redis (`redis_global`):** El "Mensajero Veloz". Un almacén de datos en memoria ultrarrápido.
    * **Uso:** Perfecto para `caching` (acelerar tus aplicaciones), gestionar colas de tareas (como en `n8n`) y sesiones de usuario.
    * **Puerto:** `6379`

-   **MongoDB (`mongodb_global`):** El "Cambiante". Una base de datos NoSQL flexible.
    * **Uso:** Ideal para datos que no tienen una estructura fija, como perfiles de usuario complejos, logs, o APIs modernas (como `Evolution API`).
    * **Puerto:** `27017`

-   **MariaDB:** Base de datos relacional (compatible con MySQL). Contenedor Ideal para Wordpress, Laravel: `mariadb`. Puerto: `3306`.

## Instalación

**1. Clonar el Repositorio**
```bash
# Reemplaza 'tu-github' con tu nombre de usuario
git clone [https://github.com/tu-github/Globals-Databases.git](https://github.com/tu-github/Globals-Databases.git)
cd Globals-Databases

2. Crear la Red Externa Compartida

La red digitallfran_net debe existir para que este stack se comunique con Traefik y otras aplicaciones. El nombre estandarizado para todos los proyectos de DigitAllFran es digitallfran_net.

Bash

docker network create digitallfran_net
3. Configurar los Secretos

Copia la plantilla para crear tu archivo de secretos.

Bash

cp .env.example .env
Abre el archivo .env (nano .env) y establece tus propias contraseñas seguras.

4. Desplegar el Arsenal

Bash

docker compose up -d
Verificación
Ejecuta docker ps para ver los cuatro contenedores corriendo. Sus puertos estarán expuestos en el host, listos para recibir conexiones de tus otras aplicaciones en la misma red.

