# 📊 Análisis de Canasta de Precios SEPA

Este proyecto explora la base de datos pública de precios del programa SEPA para construir una **canasta de productos representativa** a nivel nacional, considerando:

- Cadenas de comercialización  
- Cobertura geográfica (provincias)  
- Disponibilidad en sucursales  
- Distribución de precios  

Los datos utilizados provienen de:
👉 https://datos.produccion.gob.ar/dataset/sepa-precios  

---

## 🎯 Objetivo

Generar una base consolidada de productos únicos (EAN) con métricas clave que permitan:

- Identificar productos con alta cobertura nacional  
- Analizar dispersión de precios  
- Comparar presencia entre cadenas  
- Construir una canasta robusta y representativa  

---

## 🗂️ Estructura del Proceso

El pipeline realiza los siguientes pasos:

1. **Carga de datos**
   - Archivo ZIP diario de SEPA
   - Archivo maestro de provincias

2. **Descompresión**
   - Extracción del ZIP principal
   - Detección automática de ZIPs por cadena (`sepa_*.zip`)

3. **Lectura de archivos**
   - `comercio.csv`
   - `sucursales.csv`
   - `productos.csv`

4. **Limpieza**
   - Eliminación de líneas inválidas
   - Normalización de encoding
   - Conversión de precios a numérico

5. **Enriquecimiento**
   - Join entre productos, sucursales y comercios
   - Mapeo de provincias

6. **Agregación**
   - Construcción de tabla de productos únicos (EAN)
   - Cálculo de métricas:
     - Precio mínimo, máximo, mediana, promedio
     - Coeficiente de variación
     - Cobertura por cadenas, provincias y sucursales

7. **Salida**
   - Exportación a Excel con múltiples hojas

---

## 📦 Output

Se genera un archivo:
