# CURRENT_STATE — STRAT-TRACE / MSCA

Estado de trabajo al **7 de septiembre de 2026**. La **v9.4** es la propuesta de referencia para continuar; v9.2 y v9.3 se conservan como antecedentes. Este documento distingue decisiones de diseño, información aportada por el investigador y resultados pendientes de ejecución.

## Configuraciones actualmente válidas

- **Un solo modelo: DEHM**, química reducida, meteorología WRF/ERA5, resolución de referencia de 75 km, 29 capas y techo próximo a 100 hPa. La capa 1 corresponde a superficie y el índice aumenta hacia arriba. Se mantienen transporte, mezcla, decaimiento físico y deposición húmeda/seca.
- Tres configuraciones controladas: referencia **R, αw = 1**; **W−, αw = 0,5**; **W+, αw = 2**. Se escalan los coeficientes de eliminación húmeda antes de la integración. Las configuraciones comparten años, meteorología y restantes procesos; estos factores son contrastes de sensibilidad, no mejoras ya demostradas ni intervalos de confianza.
- Producción **CRAC:Be variable en el tiempo** para la comparación con observaciones. Compañeros de **producción fija**, con estructura latitud–altitud preservada, permiten diagnosticar la respuesta atmosférica. Los diagnósticos normalizados deben contrastarse con esos compañeros; una corrección escalar no garantiza eliminar los efectos de la fuente.
- Cada tratamiento de producción incluye **seis etiquetas más un total independiente**: UPPER (p < 300 hPa), MIDDLE (300 ≤ p < 700 hPa), LOWER (p ≥ 700 hPa), TOP, LATERAL e INITIAL. Son 14 trazadores si ambos tratamientos se ejecutan juntos. Las etiquetas registran producción o ruta de entrada, no la última altura ni el último cruce de la tropopausa.
- Los controles fijos repiten climatologías anuales de concentración en TOP/LATERAL; sus transferencias reales siguen dependiendo de la meteorología y se contabilizan. La interpretación se centra en diferencias **interanuales a tiempos equivalentes del calendario**. Si no se controla la variabilidad externa, la atribución se limita a las etiquetas de producción interna y trata las fronteras por separado.
- Los contrastes de aporte reponderan UPPER y TOP dentro de cada configuración y tratamiento, después de verificar linealidad y reconstrucción. No modifican los operadores de transporte. Se exige cierre del presupuesto y seguimiento de INITIAL durante el arranque anterior a 1986.
- El plan mantiene la estructura MSCA y una duración de **24 meses**. La estimación es **117/120 años-configuración** para tres configuraciones durante 39/40 años. La producción fija añade especies o, si requiere ejecuciones separadas, otros 117/120 años-configuración; el arranque y una reserva adicional del 20 % se contabilizan aparte. Son previsiones que WP1 debe contrastar con ensayos de rendimiento, no costes medidos.

## Unidades

| Variable | Convención actual |
|---|---|
| Concentración de actividad en aire, C | mBq m⁻³; media sobre el intervalo real de muestreo, ponderada por caudal cuando sea posible. |
| Deposición, D | Bq m⁻² acumulados sobre su propio intervalo de recogida. Para los colectores DWD descritos, comparar deposición total, húmeda + seca. |
| Registros en Bq L⁻¹ | Convertir únicamente con lluvia coincidente en L m⁻², conservando método, incertidumbre y convención de decaimiento. |
| Inventario N | Número de átomos; producción, transferencias y pérdidas se expresan como tasas compatibles con el paso temporal y el volumen de control. |
| Fracciones de origen | Cₖ/Ctotal y Dₖ/Dtotal, adimensionales y con umbrales mínimos del denominador. |
| Diagnóstico de eliminación | ∫Lwet dt / ∫N dt, unidades de tiempo⁻¹. |
| Contraste preliminar de resolución | 100 × (fina/gruesa − 1), en %, calculado con medias estacionales emparejadas y después mediana espacial. |

No equiparar valores ausentes con cero; conservar las no detecciones como observaciones censuradas. Los intervalos de aire y deposición pueden diferir: simular cada uno sobre su soporte real.

## Periodos

- **Simulación principal: 1986–2024/2025**; finalizar en 2025 si las entradas meteorológicas y de producción son consistentes, o en 2024 en caso contrario. Las tres configuraciones y ambos tratamientos comparten el periodo. El arranque queda antes del inicio analizado.
- Cubre tres ciclos solares completos, **22–24 (septiembre de 1986–diciembre de 2019)**, y las fases ascendente y máxima del ciclo 25, todavía incompleto. No describir el ciclo 25 como completo ni asegurar qué proporción de su duración final se ha cubierto.
- **Aclaración del investigador del 7 de septiembre de 2026:** existen datos experimentales en una estación desde **1986** y mayor cobertura de estaciones desde **2006**. Faltan en este paquete los nombres e inventarios detallados por variable, método, fechas, lagunas y permisos. Esta disponibilidad no demuestra pares continuos concentración–deposición ni lluvia diaria desde 1986.
- **2009–2024** permanece como base reciente de deposición y periodo específico de la Tabla 2; **no es un límite universal de las observaciones**. La correspondencia DWD documenta precipitación diaria desde 2009. El cambio de colector de 2018 debe conservarse como estrato metodológico.
- Comparar solamente intervalos válidos por estación y variable. Emplear subconjuntos estables de estaciones/métodos y pesos de agregación fijos; separar cambios atmosféricos de cambios en la red. Bloquear años de evaluación antes del ajuste y incorporar datos posteriores mediante una extensión predefinida.

## Rutas importantes

Todas las rutas son relativas a esta carpeta para poder continuar desde otro ordenador.

- **Editar a partir de:** [Word v9.4](v9.4/STRAT_TRACE_MSCA_PROPOSAL_v9_4.docx).
- **Comprobar presentación:** [PDF v9.4](v9.4/STRAT_TRACE_MSCA_PROPOSAL_v9_4.pdf).
- **Pendientes de candidatura, recursos y metadatos:** [Notas para el envío v9.4](v9.4/NOTAS_PARA_EL_ENVIO_v9_4.md).
- **Antecedentes:** [v9.3](v9.3/) y [v9.2](v9.2/). Conservarlos sin sobrescribir; crear v9.5 para la siguiente revisión.
- **Contenido y comprobación de integridad:** [README](README.md) y [manifiesto SHA-256](MANIFEST_SHA256.json).
- Este paquete contiene documentos y el estado de trabajo; **no incluye los archivos científicos originales, los registros privados de estaciones ni el código completo de DEHM**. Sus ubicaciones y permisos deben completarse cuando se incorporen al trabajo del portátil.

## Resultados ya demostrados

- La v9.4 integra el periodo largo, la cobertura observacional aclarada, los controles de fuente, la mejora de redacción e impacto y las notas de trabajo separadas. El Word y el PDF se revisaron visualmente en sus diez páginas; el PDF tiene las fuentes incrustadas. Esta revisión documental **no ejecutó las nuevas simulaciones**.
- La implementación previa de ⁷Be en DEHM está descrita en el abstract EGU26-20989. No utilizar ese abstract como fuente de los porcentajes siguientes.
- **Tabla 2, análisis preparatorio suministrado por el investigador:** DEHM de 25 km respecto a 75 km, JJA 2009–2024, **79 ubicaciones de muestreo del modelo**, con posibles celdas compartidas: **+5,9 %** en concentración, **+13,6 %** en deposición total y **−45,9 %** en precipitación. Son contrastes del modelo con el alcance y cálculo indicados; no equivalen a 79 estaciones independientes ni a una validación de toda la red. Conservar su cálculo reproducible y procedencia privada.
- El investigador confirma acceso computacional existente. No se han medido en esta revisión horas de cálculo, memoria o almacenamiento de la matriz completa ni confirmado la continuidad de todo el archivo histórico WRF.

## Hipótesis abiertas

- **H1:** las modificaciones de eliminación húmeda generan respuestas dependientes del origen, superiores a la incertidumbre numérica y de muestreo.
- **H2:** las observaciones conjuntas de aire y deposición distinguen explicaciones que la concentración por sí sola deja sin resolver.
- **H3:** las explicaciones respaldadas por presupuestos mantienen habilidad conjunta en años y regímenes reservados; los controles de producción fija evalúan su dependencia de la fuente.
- La mayor deposición con menor lluvia motiva evaluar disponibilidad del trazador y exposición a eliminación; siguen abiertas las contribuciones relativas de producción, aporte de frontera, transporte, mezcla y eliminación.
- Falta demostrar reconstrucción y cierre de las etiquetas, sensibilidad a límites de presión, convergencia del arranque, discriminación sintética y transferencia a años/estaciones reservados. La tolerancia de reconstrucción propuesta es inferior al 0,1 % por encima de un umbral absoluto y al menos diez veces menor que la respuesta mínima interpretada. El objetivo de recuperación ≥80 % con falsa discriminación ≤5 % es un criterio propuesto, no un resultado obtenido.

## Análisis descartados

- Añadir otro modelo a la matriz central o presentar configuraciones alternativas de conversaciones anteriores como protocolo vigente.
- Afirmar que los contrastes preliminares prueban descenso más rápido, sesgo observacional, efecto climático o un resultado definitivo para todas las estaciones.
- Interpretar UPPER + TOP como contribución estratosférica completa: el techo próximo a 100 hPa y las bandas de presión no permiten esa equivalencia.
- Equiparar concentración de frontera fija con flujo de masa constante; atribuir la señal estacional completa a transporte/eliminación con fronteras estacionales; normalizar escalarmente la producción y asumir que se han eliminado todos sus efectos.
- Comparar periodos distintos entre configuraciones, extrapolar resultados fuera de la cobertura observada o ajustar usando los bloques reservados para evaluación.

## Siguiente pregunta científica

**¿En qué estaciones, años y regímenes las observaciones conjuntas de concentración y deposición permiten distinguir cambios de aporte atmosférico de cambios en eliminación húmeda, una vez controladas la producción solar, las fronteras y el muestreo?**

Para retomarlo: partir de v9.4 y las notas; completar el inventario de la estación desde 1986 y la red desde 2006; confirmar entradas y costes con el ensayo de WP1; verificar etiquetas, fronteras y arranque; fijar los bloques independientes antes de las simulaciones largas y del ajuste. Mantener separados hechos confirmados, hipótesis y tareas previstas. La elegibilidad y los restantes comprobantes de envío se gestionan en las notas, sin darlos por resueltos.
