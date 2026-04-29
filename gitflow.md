# Proyecto

## Flujo de desarrollo

Este repositorio utiliza un flujo de trabajo basado en ramas para separar **testing** y **producción**.

### Ramas

- `main` → Producción
- `testing` → Testing / Preproducción
- `feature/*` o `fix/*` → Desarrollo de nuevas funcionalidades o correcciones

### Flujo

1. Crear una rama nueva desde `testing`.
2. Desarrollar el cambio en la rama creada.
3. Abrir Pull Request hacia `testing`.
4. Probar y validar en el ambiente de testing.
5. Abrir Pull Request de `testing` hacia `main`.
6. Al hacer merge en `main`, el cambio pasa a producción.

No se permiten pushes directos a `main` ni `testing`.

---

## Protección de ramas

- `main` y `testing` están protegidas con Branch Protection Rules.
- Todos los cambios llegan mediante Pull Requests.
- `main` requiere aprobación antes de merge.

---

## Despliegue

El proyecto se despliega usando **Vercel** o **Coolify** con dos ambientes:

| Ambiente     | Rama     | Dominio |
|-------------|----------|---------|
| Producción  | `main`   | dominio.com |
| Testing     | `testing`| testing.dominio.com |

Cada ambiente despliega automáticamente su rama correspondiente.

---

## Base de datos

Existen dos bases de datos separadas:

- Base de datos de producción
- Base de datos de testing

Las variables de entorno de cada ambiente apuntan exclusivamente a su base de datos correspondiente.

**Nunca se debe compartir la base de datos entre ambientes.**

---

## Reglas generales

- Todo cambio debe pasar por `testing` antes de llegar a `main`.
- Se requiere aprobación antes de producción.
- Mantener ramas actualizadas y limpias.
