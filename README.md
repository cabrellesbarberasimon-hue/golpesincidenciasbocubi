# Análisis de Golpes · Incidencias Bocubi

App web para analizar los artículos golpeados y perdidos en transporte, creada a partir del libro `ANALISIS_GOLPES_DESDE_MARZO_26.xlsx` (hojas *Análisis golpes*, *Hoja1* y *Hoja2*).

Abre `index.html` en el navegador: no necesita instalación ni servidor. Arranca con las 61 incidencias de *Hoja1*.

## Qué hace

| Pestaña | Equivale en el Excel a | Función |
|---|---|---|
| **Resumen** | Análisis golpes (resúmenes) y Hoja2 | Indicadores (incidencias, golpes, pérdidas de agencia, transporte y familia con más incidencias, provincias, clientes repetidos), barras por familia + modelo, transporte y provincia, evolución mensual y matriz transporte × provincia. Pulsa cualquier barra o celda para ver esas incidencias. |
| **Incidencias** | Hoja1 / detalle | Tabla con búsqueda y filtros por transporte, provincia, familia y tipo. Alta, edición y borrado en un panel lateral. |
| **Normalización** | Notas de la hoja *Análisis golpes* | Reglas editables que agrupan transportes (`TRANSP. MEDITERR. EXPRES, S.L.` → mediterraneo), localidades → provincia (`VIGO` → Pontevedra) y artículo → familia + modelo, más una lista de lo que falta por revisar. |

- **Periodo**: el selector de la cabecera filtra por *fecha albarán* (por defecto desde 01/03/2026, como el Excel; también desde febrero, año 2026, últimos 90 días, todo o rango personalizado).
- **Tipo**: «Pérdida» cuando el artículo dice *pierde agencia* / *perdida*; si no, «Golpe».
- **Familia + modelo**: gana el patrón que aparece antes en la descripción; se puede fijar a mano en cada incidencia.
- **Importar Excel…** lee una hoja con las columnas de *Hoja1* (`fecha albaran`, `ARTICULOS GOLPEADOS`, `Su número`…) y añade solo las incidencias nuevas. **Exportar Excel** genera *Detalle*, *Resumen* y *Transporte x Provincia* del periodo y filtros activos.

## Datos

Abierta localmente o en Vercel, la app guarda los datos en el navegador de cada usuario (`localStorage`); para compartirlos usa *Exportar / Importar Excel*. Publicada como artifact de claude.ai, usa una base de datos compartida por todo el equipo.

## Despliegue en Vercel

Es una página estática: no hay build. En Vercel, **Add New… → Project**, importa este repositorio, deja *Framework Preset* en **Other** y pulsa **Deploy**. La app queda en la dirección principal del proyecto.
