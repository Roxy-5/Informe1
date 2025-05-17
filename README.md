![](https://github.com/Roxy-5/Informe1/blob/main/images.jpg)

### 🛸 Informe1

Análisis de datos de la tabla.

### 🌍 Cómo usar

1. Clona este repositorio.
2. Instala las dependencias necesarias.
3. Ejecuta el proyecto.

### 🪐 Autor

Rocío Ramírez

### 🌌 Proceso llevado a cabo para la limpieza y corrección:
- Se carga el archivo CSV con `pd.read_csv()`, usando `on_bad_lines='skip'` para ignorar filas problemáticas.
- Se visualizan las primeras y últimas filas (`head()`, `tail()`), el número de filas y columnas (`shape`), los tipos de datos (`info()`, `dtypes`), y se revisan duplicados y valores nulos (`duplicated().sum()`, `isna().sum()`).
- Se convierte la columna `'date'` a tipo `datetime` con `errors='coerce'` para manejar fechas inválidas.
- Se elimina la columna `'campaign_name'` y otras columnas constantes, completamente nulas o de baja variabilidad.
- Se identifican columnas con pocos valores únicos o con valores nulos.
- Se convierten las columnas `'budget'` y `'revenue'` a numérico, eliminando símbolos y separadores de miles, y reemplazando valores no válidos con `NaN`.
- Se rellenan valores nulos en `'budget'` y `'revenue'` con 0.
- Se eliminan filas donde `'budget'` es menor o igual a 0.
- Se eliminan filas duplicadas.
- Se convierten a minúsculas y se eliminan espacios extra en columnas como `'type'` y `'target_audience'`.
- Se corrigen valores erróneos en `'type'` usando un diccionario de reemplazo y coincidencias aproximadas (`difflib.get_close_matches`).
- Se asegura que `'target_audience'` solo tenga valores `'b2b'` o `'b2c'`, eliminando filas con otros valores.
- Se convierten `'start_date'` y `'end_date'` a tipo `datetime` con manejo de errores.
- Se eliminan filas con fechas no válidas en `'start_date'` y `'end_date'`.
- Se reemplazan comas por puntos en `'roi'` y `'conversion_rate'` y se convierten a `float`.
- Se rellenan valores nulos en `'conversion_rate'` con 0 o un valor específico.
- Se calcula el beneficio neto (`net_profit`), el costo por conversión y variables binarias para ROI positivo, conversión alta y presupuesto alto.
- **Validaciones:**  
  - `'revenue'` no puede ser menor que `'budget'`.
  - `'roi'` debe ser consistente con `'budget'` y `'revenue'`.
  - `'conversion_rate'` debe estar entre 0 y 1.
  - `'start_date'` debe ser anterior a `'end_date'`.
- Se recalcula `'roi'` cuando hay inconsistencias y se marcan las filas problemáticas.
- Se eliminan o corrigen filas con inconsistencias lógicas.
- Se detectan outliers en `'budget'` y `'revenue'` usando ambos métodos y se revisan los valores extremos.
- Se asegura que todas las columnas tengan el tipo de dato correcto.
- Se extraen mes, trimestre y año de las fechas para análisis estacional.
- Se crean categorías para `'roi'` y `'conversion_rate'` usando `pd.cut()`.
- **¿Qué se corrige en este proceso?:**
  - Conversión y validación de tipos de datos.
  - Relleno y eliminación de valores nulos.
  - Corrección de valores inconsistentes y normalización de texto.
  - Eliminación de duplicados y columnas innecesarias.
  - Validaciones lógicas y corrección de métricas.
  - Detección y revisión de outliers.
  - Preparación de nuevas variables y categorías para análisis.

### 🚀 Respuestas a las preguntas del cliente:

1. **¿Qué canal de marketing se utiliza con mayor frecuencia?:** Promotion. ![image](https://github.com/user-attachments/assets/43b5ffa4-2267-42de-83ec-2e192614ef7a)

2. **¿Qué canal genera mejor ROI?:** Referral. ![image](https://github.com/user-attachments/assets/6bd65272-9d6d-462e-804f-7efad3ec3ff5)

3. **¿Qué tipo de campaña genera más ingresos en promedio?:** Social media. ![image](https://github.com/user-attachments/assets/ae2724a7-c5c9-4866-9b61-ddee4d203f66)

4. **¿Qué campaña tiene mejor conversión?:** Webinar. ![image](https://github.com/user-attachments/assets/a839fd6d-377d-476e-89b6-4ed26c3731ce)

5. **¿Qué campaña genera el mejor ROI?:** Social media. ![image](https://github.com/user-attachments/assets/ce4901f8-8cc5-421f-bfd3-16580f5bc5d7)

6. **¿Cuál audiencia genera mejor ROI?:** b2b. ![image](https://github.com/user-attachments/assets/7136d3ed-d367-4721-a3be-fcc31988ad4c)

7. **¿Qué presupuesto genera más ROI?:** 71941.12. ![image](https://github.com/user-attachments/assets/65627dae-a8fc-4d38-9ab2-5e8c60b1f678) 

8. **¿Hay diferencias significativas en la tasa de conversión entre audiencias B2B y B2C?:** No. ![image](https://github.com/user-attachments/assets/a718f1a3-5769-4121-81fa-e586e48e93b5) ![image](https://github.com/user-attachments/assets/2b23db49-2b8f-480c-9ca6-833ce4a4af26) ![image](https://github.com/user-attachments/assets/2759b451-db99-4594-8693-90c039c8d7d8)

9. **¿Qué campaña tiene el mayor beneficio neto (net_profit)?:** Social media.
10. **Calcular métricas clave por tipo de campaña.**
    ![image](https://github.com/user-attachments/assets/03ebe76a-d04b-44ff-afab-c898bff445b3)
11. **Visualizar el beneficio neto promedio por tipo de campaña.**
    ![image](https://github.com/user-attachments/assets/f3f94b36-a66e-458c-802d-fe60ef54eac0)
    
12. **¿Existe correlación entre el presupuesto (budget) y los ingresos (revenue)?:** Hay correlación negativa muy débil (-0.05). ![image](https://github.com/user-attachments/assets/668f1b01-20fa-4139-b329-2da06e55f4dc) ![image](https://github.com/user-attachments/assets/0c5b1f6d-1e9f-4a6b-b93e-d322164c4794)

13. **¿Qué campañas tienen un ROI mayor a 0.5 y ingresos encima de 500,000?** ![image](https://github.com/user-attachments/assets/4d89c183-dfe4-469e-a0cd-ce148627ffc0) ![image](https://github.com/user-attachments/assets/ae4f16f7-90f7-4719-945f-1ebe4f5ed2b2)

14. **¿Existen patrones estacionales o temporales en el rendimiento de las campañas?:** 
    - Patrones mensuales:
      - Enero y noviembre: Meses clave con alto rendimiento en términos de ROI y tasa de conversión, lo que los hace ideales para maximizar las inversiones.
      - Diciembre: Aunque el ROI es bajo, el beneficio neto es elevado, probablemente impulsado por campañas estacionales de fin de año.
    - Patrones trimestrales:
      - Q1 (enero-marzo): El mejor trimestre en cuanto a rendimiento global, representando una oportunidad óptima para campañas estratégicas.
      - Q4 (octubre-diciembre): El trimestre con el desempeño más bajo, tanto en términos de tasa de conversión como de beneficio neto, lo que sugiere áreas a       mejorar.
    - Patrones anuales:
      - 2023: Año destacado con el mejor rendimiento en ROI y tasa de conversión.
      - 2025: Desempeño inferior, posiblemente influenciado por datos incompletos o parciales. ![image](https://github.com/user-attachments/assets/ada752ce-c160-4b62-8113-ddc34f3c024c) ![image](https://github.com/user-attachments/assets/54e21bb0-a776-4227-870b-04660d2083cb) ![image](https://github.com/user-attachments/assets/7a8ad30b-4c9e-47b5-9e62-8738718e4739) ![image](https://github.com/user-attachments/assets/1ba3fd79-d9e5-4a01-ac87-5ad8359857ad)
 
### 🌋 Hallazgos

1. **Análisis mensual:**
- Los meses con el ROI más alto son enero (32.82) y noviembre (32.25).
- El mes con el ROI más bajo es diciembre (16.76).
- Tasa de conversión:
  - La tasa de conversión más alta ocurre en enero (0.615).
  - La tasa de conversión más baja ocurre en febrero (0.494).
- Beneficio neto:
  - El beneficio neto más alto ocurre en agosto (519,653.66).
  - El beneficio neto más bajo ocurre en julio (304,665.33).
- Conclusión mensual:
  - Enero y noviembre parecen ser meses de alto rendimiento en términos de ROI y tasa de conversión.
- Diciembre tiene un ROI bajo, pero el beneficio neto es relativamente alto, lo que podría deberse a campañas de fin de año con altos presupuestos.

2. **Análisis trimestral:**
- El trimestre con el ROI más alto es Q1 (27.45).
- El trimestre con el ROI más bajo es Q3 (23.60).
- Tasa de conversión:
  - La tasa de conversión más alta ocurre en Q1 (0.575).
  - La tasa de conversión más baja ocurre en Q4 (0.523).
- Beneficio neto:
  - El beneficio neto más alto ocurre en Q2 (486,097.40).
  - El beneficio neto más bajo ocurre en Q4 (435,875.28).
- Conclusión trimestral:
  - Q1 (enero-marzo) es el trimestre con el mejor rendimiento general, con el ROI y la tasa de conversión más altos.
  - Q4 (octubre-diciembre) tiene el rendimiento más bajo en términos de tasa de conversión y beneficio neto, lo que podría deberse a campañas de alto presupuesto con menor eficiencia.

3. **Análisis anual:**
- El ROI más alto ocurre en 2023 (26.59).
- El ROI más bajo ocurre en 2025 (1.67), aunque este año parece tener pocos datos.
- Tasa de conversión:
  - La tasa de conversión más alta ocurre en 2025 (0.65).
  - La tasa de conversión más baja ocurre en 2022 (0.519).
- Beneficio neto:
  - El beneficio neto más alto ocurre en 2022 (465,649.82).
  - El beneficio neto más bajo ocurre en 2025 (125,000.00).
- Conclusión anual:
  - 2023 muestra un mejor rendimiento general en términos de ROI y tasa de conversión.
  - 2025 tiene un rendimiento significativamente más bajo, pero esto podría deberse a un número limitado de datos.

### 🧭 Recomendaciones estratégicas

- **Enero y noviembre:**
  - Maximizar la inversión en campañas durante estos meses para aprovechar el ROI y las tasas de conversión superiores.
- **Diciembre:*
  - Optimizar la eficiencia de las campañas para aumentar el ROI, capitalizando el alto beneficio neto de este mes.
- **Q1:**
  - Priorizar el lanzamiento de campañas clave durante este trimestre de alto rendimiento.
- **Q4:**
  - Evaluar y ajustar estrategias de campaña para mejorar la eficiencia, enfocados en aumentar la tasa de conversión y los beneficios netos.
