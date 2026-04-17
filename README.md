# Olimpiadas 2025 — Agencia de Turismo

Plataforma web completa desarrollada en equipo para una Olimpíada Escolar. Permite a usuarios explorar, buscar y comprar paquetes turísticos con flujo de pago real. Cada integrante tuvo un rol definido dentro del desarrollo.

🔗 [github.com/JesusBaute/Olimpiadas_2025](https://github.com/JesusBaute/Olimpiadas_2025)

## Mi rol — Backend, base de datos y autenticación

- Diseño, creación y optimización de la base de datos relacional (MySQL)
- Implementación del sistema de registro, login y autenticación con JSON Web Tokens (JWT)
- Gestión de sesiones mediante cookies e implementación de roles (usuario / administrador)
- Integración del sistema de pagos con la API de Mercado Pago
- Conexión completa entre base de datos y backend (Node.js + Express)

## Stack

JavaScript, Node.js, Express.js, MySQL, JWT, Mercado Pago API, HTML, CSS, Docker, Nginx

## Funcionalidades

### Cliente
- Registro, login y gestión de sesión
- Exploración del catálogo de paquetes turísticos
- Carrito de compras
- Pago con Mercado Pago
- Panel de pedidos propios y cancelaciones

### Administrador
- Panel de administración
- Creación y gestión de paquetes
- Visualización y gestión de pedidos (entregar / anular)
- Vista de clientes y su historial de compras

## Cómo probarlo localmente

### Requisitos

- [Docker](https://www.docker.com/) instalado y corriendo

### Pasos

1. Clonar el repositorio:
```bash
git clone https://github.com/JesusBaute/Olimpiadas_2025
cd Olimpiadas_2025
```

2. Levantar los contenedores:
```bash
docker-compose up -d
```

3. Abrir el navegador en:
```
http://localhost
```

4. Para apagar:
```bash
docker-compose down
```

> Para resetear la base de datos por completo (borra todos los datos):
> ```bash
> docker-compose down -v
> ```

> Si querés probar el flujo de pago real, reemplazá el valor de `MP_ACCESS_TOKEN` en `docker-compose.yml` con tu propio token de Mercado Pago. Sin configurarlo, el resto de la app funciona igual.

## Usuarios de prueba

| Rol     | Email            | Contraseña |
|---------|------------------|------------|
| Cliente | usuario@demo.com | usuario123 |
| Admin   | admin@demo.com   | admin123   |

## Estructura del proyecto

```
├── src/
│   └── app.js           # Backend (rutas, lógica, conexión a DB)
├── static/
│   ├── index.html       # Página principal con catálogo
│   ├── carrito.html     # Carrito de compras
│   ├── user.html        # Panel del usuario (mis pedidos)
│   ├── admin.html       # Panel de administración
│   ├── log.html         # Login
│   ├── register.html    # Registro
│   ├── css/             # Estilos
│   ├── js/              # Scripts del frontend
│   └── img/             # Imágenes
├── database.sql         # Estructura y datos iniciales de la DB
├── docker-compose.yml   # Configuración de contenedores
├── Dockerfile           # Imagen del backend
└── nginx.conf           # Configuración del servidor estático
```
