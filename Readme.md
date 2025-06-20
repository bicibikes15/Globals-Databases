<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/database/database-original.png" alt="Databases Logo" width="120"/>
  <h1 align="center">Stack Global de Bases de Datos by DigitAllFran</h1>
  <p>
    <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
    <img src="https://img.shields.io/badge/PGVector-0099cc?style=for-the-badge" alt="PGVector"/>
    <img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white" alt="Redis"/>
    <img src="https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB"/>
    <img src="https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white" alt="MariaDB"/>
    <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker"/>
  </p>
</div>

> [!NOTE]
> **Arsenal de datos centralizado**  
> Un stack de bases de datos de alto rendimiento, diseñado para servir como la fundación única y segura de tu ecosistema DigitAllFran.

> [!TIP]
> **Arquitectura y estrategia**
> - Todas las bases de datos expuestas internamente en la red `digitallfran_net`
> - Integración directa con [Traefik](https://github.com/bicibikes15/Traefik) y cualquier stack de DigitAllFran
> - Gestión visual opcional con [Portainer](https://github.com/bicibikes15/Portainer-Stack-Traefik)

> [!IMPORTANT]
> **Guerreros incluidos en este arsenal**
> - **PostgreSQL (`postgres_global`)**: El General. Puerto: `5432`
> - **PGVector (`pgvector_global`)**: El Rastreador IA. Puerto: `5433`
> - **Redis (`redis_global`)**: El Mensajero Veloz. Puerto: `6379`
> - **MongoDB (`mongodb_global`)**: El Cambiante. Puerto: `27017`
> - **MariaDB (`mariadb_global`)**: El Clásico para WordPress/Laravel. Puerto: `3306`

> [!IMPORTANT]
> **Instalación**
> 1. **Clona el repositorio:**
>    ```
>    git clone https://github.com/bicibikes15/Globals-Databases.git
>    cd Globals-Databases
>    ```
> 2. **Crea la red externa compartida (si no existe):**
>    ```
>    docker network create digitallfran_net
>    ```
> 3. **Configura los secretos:**
>    ```
>    cp .env.example .env
>    # Edita .env y pon tus contraseñas seguras.
>    ```
> 4. **Despliega el arsenal:**
>    ```
>    docker compose up -d
>    ```
> 5. **Verifica que todo esté corriendo:**
>    ```
>    docker ps
>    # Deberías ver todos los contenedores y puertos listos para tus apps.
>    ```

> [!WARNING]
> **¿Conectando apps?**  
> Usa el nombre del contenedor como host (ej. `postgres_global`, `redis_global`, etc.) en tus aplicaciones conectadas a la misma red.

> [!NOTE]
> **¿Todo funcionando?**  
> Si puedes conectar tus apps y acceder a las bases de datos, ¡tienes tu arsenal centralizado listo para microservicios, bots y automatización!

---

<div align="center">
  <a href="https://digitallfran.co" target="_blank">
    <img src="https://digitallfran.co/logo.svg" alt="DigitAllFran Logo" width="90"/><br>
    <b>¿Necesitas soporte, migraciones o una arquitectura de datos a la medida?</b><br>
    <span style="font-size:1.1em;">
      <strong>¡Visita <u>digitallfran.co</u> y agenda tu consulta!</strong>
    </span>
  </a>
</div>
