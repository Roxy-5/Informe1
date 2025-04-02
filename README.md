![](https://github.com/Roxy-5/Informe1/blob/main/images.jpg)

🛸 Informe1

Análisis de datos de la tabla.

🌍 Cómo usar

1. Clona este repositorio.
2. Instala las dependencias necesarias.
3. Ejecuta el proyecto.

🪐 Autor

Rocío Ramírez

🌌 Proceso llevado a cabo para la limpieza y corrección:

Calculo la media y el máximo de revenue.
Elimino valores nulos de budget y calculo su media y máximo.
Calculo los valores nulos de cada columna: 11 en total.
Le doy valor desconocido a los valores nulos de type.
Relleno los valores nulos de conversion_rate.
Controlo y elimino las fechas locas de start_date y end_date. 
Reemplazo los valores de roi y conversion_rate con comas por puntos y los convierto en decimal.
Reemplazo los valores de budget y revenue con comas por puntos y los convierto a numérico.
Elimino los duplicados de todas las columnas.
Delimito target_audience a los valores 'b2b' y 'b2c' y elimino los nulos.
Obtengo los valores únicos de channel para ver errores ortográficos: no hay errores.
Identifico duplicados de channel y los mantengo.
Convierto revenue y budget a numérico y los no válidos los convierto en 0.
Calculo el beneficio neto.
Detecto outliers en budget con el método IQR y Z-score: 1008 y 9999999.
Detecto outliers en revenue con el método IQR y Z-score: ninguno.
Calculo el porcentaje de valores faltantes por columna: 0.
Elimino en budget y revenue los símbolos de moneda y separadores de miles para convertirlos a decimales.
Normalizo el texto conviertiendo type a minúsculas y eliminando espacios adicionales.
Corrijo las categorías de type y sus valores únicos.
Extraigo los componentes temporales de start_date y end_date.
Creo categorías de rendimiento en ROI y en la tasa de conversión.
Elimino valores nulos de conversion_rate y evito las divisiones por cero.
Creo una variable binaria para ROI positivo, para conversión alta (0,3) y presupuesto alto (100000).
Verifico los tipos de datos de todas las columnas.
Calculo ROI esperado en budget y revenue y lo comparo con el existente en el DataFrame filtrando las inconsistencias: 1.
Inspecciono las inconsistencias y vuelvo a calcular el ROI en budget y revenue: sin inconsistencias.
Propongo 4 validaciones y filtro las inconsistencias: 4 inconsistencias.
Vuelvo a calcular los valores nulos de todas las columnas: 0.
Calculo los promedios de 'b2b' y 'b2c'.

Respuestas a las preguntas del cliente:

¿Qué canal de marketing se utiliza con mayor frecuencia?: Promotion.
¿Qué canal genera mejor ROI?: Referral.
¿Qué tipo de campaña genera más ingresos en promedio?: Social media.
¿Qué campaña tiene mejor conversión?: Webinar.
¿Qué campaña genera el mejor roi?: Social media.
¿Cuál audiencia genera mejor roi?: b2b.
¿Qué presupuesto genera más roi?: 71941.12.
¿Hay diferencias significativas en la tasa de conversión entre audiencias B2B y B2C?: No.
¿Qué campaña tiene el mayor beneficio neto (net_profit)?: Social media.
Calcular métricas clave por tipo de campaña.
Visualizar el beneficio neto promedio por tipo de campaña.
¿Existe correlación entre el presupuesto (budget) y los ingresos (revenue)?: Hay correlación negativa muy débil (-0.05).
¿Qué campañas tienen un ROI mayor a 0.5 y ingresos encima de 500,000?
¿Existen patrones estacionales o temporales en el rendimiento de las campañas?: 
Patrones mensuales:
Enero y noviembre: Meses clave con alto rendimiento en términos de ROI y tasa de conversión, lo que los hace ideales para maximizar las inversiones.
Diciembre: Aunque el ROI es bajo, el beneficio neto es elevado, probablemente impulsado por campañas estacionales de fin de año.
Patrones trimestrales:
Q1 (enero-marzo): El mejor trimestre en cuanto a rendimiento global, representando una oportunidad óptima para campañas estratégicas.
Q4 (octubre-diciembre): El trimestre con el desempeño más bajo, tanto en términos de tasa de conversión como de beneficio neto, lo que sugiere áreas a mejorar.
Patrones anuales:
2023: Año destacado con el mejor rendimiento en ROI y tasa de conversión.
2025: Desempeño inferior, posiblemente influenciado por datos incompletos o parciales.

🌋 Hallazgos

1. Análisis mensual:
Los meses con el ROI más alto son enero (32.82) y noviembre (32.25).
El mes con el ROI más bajo es diciembre (16.76).
Tasa de conversión:
La tasa de conversión más alta ocurre en enero (0.615).
La tasa de conversión más baja ocurre en febrero (0.494).
Beneficio neto:
El beneficio neto más alto ocurre en agosto (519,653.66).
El beneficio neto más bajo ocurre en julio (304,665.33).
Conclusión mensual:
Enero y noviembre parecen ser meses de alto rendimiento en términos de ROI y tasa de conversión.
Diciembre tiene un ROI bajo, pero el beneficio neto es relativamente alto, lo que podría deberse a campañas de fin de año con altos presupuestos.

2. Análisis trimestral:
El trimestre con el ROI más alto es Q1 (27.45).
El trimestre con el ROI más bajo es Q3 (23.60).
Tasa de conversión:
La tasa de conversión más alta ocurre en Q1 (0.575).
La tasa de conversión más baja ocurre en Q4 (0.523).
Beneficio neto:
El beneficio neto más alto ocurre en Q2 (486,097.40).
El beneficio neto más bajo ocurre en Q4 (435,875.28).
Conclusión trimestral:
Q1 (enero-marzo) es el trimestre con el mejor rendimiento general, con el ROI y la tasa de conversión más altos.
Q4 (octubre-diciembre) tiene el rendimiento más bajo en términos de tasa de conversión y beneficio neto, lo que podría deberse a campañas de alto presupuesto con menor eficiencia.

3. Análisis anual:
El ROI más alto ocurre en 2023 (26.59).
El ROI más bajo ocurre en 2025 (1.67), aunque este año parece tener pocos datos.
Tasa de conversión:
La tasa de conversión más alta ocurre en 2025 (0.65).
La tasa de conversión más baja ocurre en 2022 (0.519).
Beneficio neto:
El beneficio neto más alto ocurre en 2022 (465,649.82).
El beneficio neto más bajo ocurre en 2025 (125,000.00).
Conclusión anual:
2023 muestra un mejor rendimiento general en términos de ROI y tasa de conversión.
2025 tiene un rendimiento significativamente más bajo, pero esto podría deberse a un número limitado de datos.

4. Recomendaciones estratégicas
Enero y noviembre: Maximizar la inversión en campañas durante estos meses para aprovechar el ROI y las tasas de conversión superiores.
Diciembre: Optimizar la eficiencia de las campañas para aumentar el ROI, capitalizando el alto beneficio neto de este mes.
Q1: Priorizar el lanzamiento de campañas clave durante este trimestre de alto rendimiento.
Q4: Evaluar y ajustar estrategias de campaña para mejorar la eficiencia, enfocados en aumentar la tasa de conversión y los beneficios netos.
