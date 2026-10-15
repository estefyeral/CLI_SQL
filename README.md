# CLI SQL — Aprende SQL desde cero

Aplicación web interactiva tipo **Duolingo** para aprender **SQL** desde cero. Combina teoría clara con práctica real mediante un **mini motor de base de datos relacional en memoria**.

Es una app **autocontenida en un solo archivo HTML** (`sql-duo.html`): no necesita instalación, build ni servidor.

## Características

- **Fase de teoría** antes de cada minijuego. Cada tema se explica con la estructura obligatoria:
  1. ¿Qué es y qué hace?
  2. ¿Cómo funciona internamente?
  3. ¿Para qué sirve en la vida real?
  4. ¿Cómo se usa? (sintaxis + ejemplos visuales)
- **Fase de práctica tipo Duolingo**: preguntas de opción múltiple + consultas reales sobre una base de datos.
- **Mini motor SQL propio**: las consultas se ejecutan de verdad sobre un esquema relacional (proyección, filtrado, orden, agrupación, JOIN y DML).
- **Consola interactiva**: resultados en tabla ASCII, historial navegable con las flechas ↑ / ↓.
- **SQL libre (sandbox)**: practica cualquier consulta sin retos ni vidas.
- **Gamificación**: XP, vidas (❤️) y rachas diarias (🔥).
- **Persistencia** con `localStorage`: el progreso se guarda en el navegador.

## SQL soportado

- `SELECT` con columnas, `*`, alias `AS`
- `WHERE` con `=`, `<>`/`!=`, `<`, `>`, `<=`, `>=`, `AND`, `OR`, `NOT`, `LIKE`, `IN`, `IS [NOT] NULL`
- `ORDER BY ... ASC/DESC`, `LIMIT`
- `DISTINCT`
- Agregados `COUNT`, `SUM`, `AVG`, `MIN`, `MAX` + `GROUP BY`
- `INSERT INTO ... VALUES`, `UPDATE ... SET`, `DELETE FROM`
- `CREATE TABLE`, `DROP TABLE`
- `[INNER] JOIN ... ON`
- Metacomandos: `.tables`, `.schema`, `.help`, `DESCRIBE tabla`

## Base de datos de ejemplo (Tienda)

| Tabla | Columnas |
|-------|----------|
| `clientes` | id, nombre, ciudad, edad |
| `productos` | id, nombre, precio, stock, descuento |
| `pedidos` | id, cliente_id, producto_id, cantidad, fecha |

## Lecciones

| # | Lección | Contenido |
|---|---------|-----------|
| 1 | Primeros pasos | `SELECT *`, `.tables` |
| 2 | Elegir columnas | proyección |
| 3 | Filtrar | `WHERE`, operadores, `AND`/`OR` |
| 4 | Ordenar y limitar | `ORDER BY`, `LIMIT` |
| 5 | Valores únicos | `DISTINCT` |
| 6 | Insertar, actualizar y borrar | `INSERT`, `UPDATE`, `DELETE` |
| 7 | Agrupar y contar | `COUNT`, `SUM`, `GROUP BY` |
| 8 | Patrones y NULL | `LIKE`, `IS NULL` |
| 9 | Combinar tablas | `JOIN` |
| 10 | Crear tablas | `CREATE TABLE`, tipos y claves |

## Cómo usarla

**Opción 1 — Local:** descarga el repo y abre `sql-duo.html` en tu navegador (doble clic).

**Opción 2 — En línea:** accede a GitHub Pages.

## Tecnologías

- HTML + JavaScript vanilla (sin dependencias de build)
- [Tailwind CSS](https://tailwindcss.com/) vía CDN
- Google Fonts (Nunito)

## Estructura

```
cli-sql/
├── sql-duo.html   # La aplicación completa (motor SQL incluido)
├── index.html     # Redirección para GitHub Pages
└── README.md
```

## Cómo funciona la validación

La teoría y la práctica están desacopladas. El motor `runSQL(db, sql)` interpreta y ejecuta las consultas **de verdad** sobre una base de datos en memoria (filtra filas, proyecta columnas, agrupa, hace JOIN, inserta, actualiza, borra...). Cada reto valida el **resultado real** con una función `check(ctx)` que inspecciona el estado resultante (`ctx.tipo`, `ctx.resultado.columnas`, `ctx.resultado.filas`, `ctx.db`), no el texto tecleado.

---

Proyecto de práctica de desarrollo de software. ¡Aprende SQL jugando!
