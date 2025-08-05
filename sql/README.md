# 🗄️ Comandos SQL

Guía completa de comandos SQL para consultas, agregaciones, escritura y transacciones de bases de datos.

## 📚 Índice

- [📖 Consultas](./consultas.md) - Comandos de lectura y consulta
- [📊 Agregación](./agregacion.md) - Funciones de agregación y agrupación
- [✏️ Escritura](./escritura.md) - INSERT, UPDATE, DELETE
- [💾 Transacciones](./transacciones.md) - COMMIT, ROLLBACK

## 🚀 Comandos Esenciales

### Consultas Básicas
```sql
SELECT columnas FROM tabla WHERE condicion;
SELECT * FROM usuarios WHERE edad > 18;
SELECT nombre, email FROM clientes WHERE activo = 1;
```

### Filtros y Condiciones
```sql
WHERE columna = valor
WHERE columna IN (valor1, valor2)
WHERE columna LIKE '%patron%'
WHERE columna IS NULL
```

### Ordenamiento y Límites
```sql
ORDER BY columna ASC/DESC
LIMIT 10
OFFSET 20
```

## 🎯 Ejemplos Prácticos

### Consulta Completa
```sql
SELECT 
    u.nombre,
    u.email,
    COUNT(p.id) as total_posts
FROM usuarios u
LEFT JOIN posts p ON u.id = p.usuario_id
WHERE u.activo = 1
GROUP BY u.id
HAVING total_posts > 5
ORDER BY total_posts DESC
LIMIT 10;
```

### Agregación con Condiciones
```sql
SELECT 
    categoria,
    COUNT(*) as total,
    AVG(precio) as precio_promedio
FROM productos
WHERE stock > 0
GROUP BY categoria
HAVING total > 10
ORDER BY precio_promedio DESC;
```

## 💡 Mejores Prácticas

### Rendimiento
- Usa `EXPLAIN` antes de consultas complejas
- Indexa columnas frecuentemente consultadas
- Limita resultados con `LIMIT`
- Usa `SELECT` específico en lugar de `*`

### Seguridad
- Usa parámetros preparados para evitar SQL injection
- Valida datos de entrada
- Usa transacciones para operaciones críticas
- Haz backup antes de operaciones destructivas

### Legibilidad
- Usa alias descriptivos (`AS`)
- Formatea consultas con indentación
- Comenta consultas complejas
- Usa nombres de tabla/columna consistentes

## 🔧 Comandos de Diagnóstico

### `EXPLAIN` - Plan de Ejecución
```sql
EXPLAIN SELECT * FROM usuarios WHERE email = 'test@example.com';
```

### `DESCRIBE` - Estructura de Tabla
```sql
DESCRIBE usuarios;
-- o
SHOW COLUMNS FROM usuarios;
```

## 📖 Recursos Adicionales

- [SQL Tutorial](https://www.w3schools.com/sql/)
- [MySQL Documentation](https://dev.mysql.com/doc/)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [SQL Fiddle](http://sqlfiddle.com/) - Para probar consultas

---

*Basado en la guía de @midudev* 