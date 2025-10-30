<h1 align="center">📊 Análisis de Eficiencia Logística y Comercial </h1>

---

## 1. Descripción del Proyecto 

En este proyecto reuní y analicé los datos de transporte y ventas correspondientes solo a 2024.  

Mi objetivo era **entender cómo estaban funcionando nuestras operaciones, detectar los puntos débiles y encontrar oportunidades para mejorar los resultados comerciales**.  
Durante el análisis me centré en tres cosas que considero clave:  

- **Ineficiencias logísticas 🚚**, porque impactan directamente en los costos y la eficiencia.  
- **Oportunidades de rentabilidad 💰**, comparando márgenes entre clientes y canales.  
- **Indicadores de desempeño del servicio 🕒**, para ver cómo estamos cumpliendo con los tiempos de entrega y la calidad del servicio.

El resultado final es un **dashboard interactivo en Excel**, que me permite ver de manera clara los indicadores más importantes tanto de logística como de ventas.

---

## 2. Herramientas y Metodología

en este análisis utilicé varias herramientas, la cual me ayudaron a organizar y procesar los datos:

**Power Query**  
Lo usé para limpiar y transformar los datos, y para calcular métricas como margen bruto, eficiencia y puntualidad.

**Excel**  
Aquí construí el **dashboard central** (*Dashboard_general*), con gráficos y tablas que facilitan explorar los resultados.

**VBA / Macros**  
Implementé algunos macros para que los filtros funcionen entre diferentes hojas y no tenga que preocuparme de que las fuentes de datos no estén relacionadas.

**Python (Pandas)**  
Generé los datasets que alimentan el dashboard. Cada uno tiene más de 2500 registros:  
- `logistica_2024.csv`  
- `ventas_2024.csv`  

Con esto puedo actualizar los análisis de forma rápida y mantener todo conectado.

---

## 3. Métricas Clave

Para poder analizar correctamente la operación y las ventas, definí algunas métricas fundamentales en Power Query. Estas me permiten medir la rentabilidad, eficiencia y puntualidad de forma clara y reproducible.

**Margen Bruto Logística**  

  Esta métrica me ayuda a ver cuánto ganamos realmente por cada transporte, después de descontar los costos variables principales:
```powerquery
[Tarifa_Cliente] - [Costo_Combustible] - [Costo_Mantenimiento]
```
  Con esto puedo identificar qué transportistas o rutas generan márgenes más bajos y dónde se podrían optimizar costos.

**Eficiencia de Combustible**

  Para entender cuánto estamos gastando en combustible por cada kilómetro recorrido, calculé:
```powerquery
[Costo_Combustible] / [Distancia_Km]
```
  Esto me permitió ver qué vehículos o rutas son menos eficientes y dónde podemos reducir consumo o mejorar planificación.

**Puntualidad**

Quería tener un indicador rápido que me mostrara si una entrega fue “Entregado” o “Con Retraso”, así que definí:

```powerquery
Si [Diferencia_Promesa] <= 0 y [Estado_Final] = "Entregado", entonces "A Tiempo", sino "Problemas"
```

Gracias a esto puedo filtrar rápidamente los envíos con problemas y analizar patrones de retraso o cancelaciones.

---

## 4. Hallazgos y Conclusiones

Durante el análisis he encontrado varios puntos importantes que me han ayudado a entender mejor la operaciónes logisticas y las ventas.

**Operaciones y Servicio (Logística)**

- Observé que el transportista ***[ID_T008]*** tiene un costo por kilómetro ***[0,10 eruos por kilometro]*** más alto que el promedio, lo que indica que debemos revisar su desempeño y evaluar posibles optimizaciones.

- La tasa de entregas a tiempo es del ***[66,20]%***, mientras que el ***[32,44]%*** de los retrasos se debe a cancelaciones. Esto me permitió identificar rutas o procesos que necesitan atención inmediata.

- Los vehículos ***[Camioneta]*** presentan el mayor costo de mantenimiento por kilómetro, lo que impacta directamente en la rentabilidad de la operación.

**Rendimiento Comercial (Ventas)**

- Identifiqué que tipo de cliente ***[Particular]*** fue el más rentable del año, con un margen promedio de ***[37,89]%***, pero existe una igualdad en los tipos de clientes.

- Identifiqué que el canal de ventas ***[Retail]*** fue el más rentable del año, con un margen promedio de ***[39,90]%***, lo que me ayuda a priorizar estrategias comerciales.

- El vendedor ***[VEND008]*** lideró en volumen de ingresos brutos.

- Noté que hay picos de ventas en ***[Enero]*** y en ***[Agosto]***, indicando patrones estacionales que se podrían aprovechar para planificar inventario y campañas.














