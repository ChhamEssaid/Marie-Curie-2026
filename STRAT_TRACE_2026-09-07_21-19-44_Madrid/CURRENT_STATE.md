# CURRENT_STATE — STRAT-TRACE / MSCA

Estado de trabajo al **7 de septiembre de 2026, 21:19:44, Europe/Madrid**. La **v9.5** es la propuesta de referencia para continuar. Este documento distingue decisiones de diseño, confirmaciones del investigador y resultados todavía pendientes de ejecución. Las versiones anteriores se conservan en sus carpetas originales.

## Configuraciones actualmente válidas

- **Un solo modelo: DEHM**, química reducida, meteorología WRF/ERA5, resolución de referencia de 75 km, 29 capas y techo próximo a 100 hPa. La capa 1 corresponde a superficie y el índice aumenta hacia arriba. Se mantienen transporte, mezcla, decaimiento físico y deposición húmeda/seca.
- Tres configuraciones controladas: referencia **R, αw = 1**; **W−, αw = 0,5**; **W+, αw = 2**. Se escalan los coeficientes de eliminación húmeda antes de la integración. Las configuraciones comparten años, meteorología y restantes procesos. Son contrastes de sensibilidad; sus resultados aún no están demostrados.
- Producción **CRAC:Be variable en el tiempo** para comparar con observaciones. Compañeros de **producción fija**, con estructura latitud–altitud preservada, permiten diagnosticar la respuesta atmosférica. Los diagnósticos normalizados se contrastan con esos compañeros: una corrección escalar no garantiza eliminar los efectos de la fuente.
- Cada tratamiento de producción incluye **seis etiquetas más un total independiente**: UPPER (p < 300 hPa), MIDDLE (300 ≤ p < 700 hPa), LOWER (p ≥ 700 hPa), TOP, LATERAL e INITIAL. Son 14 trazadores si ambos tratamientos se ejecutan juntos. Las etiquetas registran producción o ruta de entrada; no la última altura ni el último cruce de la tropopausa.
- Los controles fijos repiten climatologías anuales de concentración en TOP/LATERAL. Sus transferencias reales siguen dependiendo de la meteorología y se contabilizan. La interpretación se centra en diferencias **interanuales a tiempos equivalentes del calendario**. Si no se controla la variabilidad externa, la atribución se limita a las etiquetas de producción interna y trata las fronteras por separado.
- Los contrastes de aporte reponderan UPPER y TOP dentro de cada configuración y tratamiento, después de verificar linealidad y reconstrucción. No modifican los operadores de transporte. Se exige cierre del presupuesto y seguimiento de INITIAL durante el arranque anterior al periodo analizado.
- Se mantiene la estructura MSCA y una duración de **24 meses**. Tres configuraciones durante 39/40 años representan **117/120 años-configuración** con producción variable. Los compañeros fijos añaden especies cuando se integran conjuntamente o **otros 117/120 años-configuración** si se ejecutan por separado; en este último caso, el total es **234/240**, antes del arranque y la reserva del 20 %. WP2 suma 78/80 años-configuración para referencia y compañero fijo; WP3 suma 156/160 para las dos sensibilidades y sus compañeros, si se ejecutan por separado.
- **Confirmación del investigador, 7 de septiembre de 2026:** AU respalda la capacidad y el calendario de cálculo de la matriz completa propuesta, incluidos producción fija, arranque y reserva. Esta confirmación se incorpora como respaldo institucional aportado por el investigador. No se han inventado cuotas de CPU ni medidas de rendimiento. Los ensayos de WP1 ajustan la organización de las ejecuciones, las entradas/salidas y el almacenamiento; no constituyen una nueva condición de viabilidad computacional.

## Unidades

| Variable | Convención actual |
|---|---|
| Concentración de actividad en aire, C | mBq m⁻³; convertir los registros originales en Bq m⁻³ mediante el factor 1000. Promediar sobre el intervalo real de muestreo, ponderando por caudal cuando sea posible. |
| Deposición, D | Bq m⁻² acumulados sobre su propio intervalo de recogida. La componente del modelo debe corresponder a lo que mida el colector documentado. |
| Registros en Bq L⁻¹ | Convertir únicamente con lluvia coincidente en L m⁻², conservando método, incertidumbre y convención de decaimiento. |
| Inventario N | Número de átomos; producción, transferencias y pérdidas como tasas compatibles con el paso temporal y el volumen de control. |
| Fracciones de origen | Cₖ/Ctotal y Dₖ/Dtotal, adimensionales y con umbrales mínimos del denominador. |
| Diagnóstico de eliminación | ∫Lwet dt / ∫N dt, unidades de tiempo⁻¹. |
| Contraste preliminar de resolución | 100 × (fina/gruesa − 1), en %, calculado con medias estacionales emparejadas y después mediana espacial. |

No equiparar valores ausentes con cero. Conservar las no detecciones como observaciones censuradas. Simular aire y deposición sobre sus respectivos intervalos reales. Los detalles de las fracciones de muestra DWD y de su armonización se conservan en las notas de trabajo, fuera de Part B1.

## Periodos

- **Simulación principal: 1986–2024/2025**, con 2025 incluido cuando las entradas sean consistentes. Las tres configuraciones y ambos tratamientos de producción comparten el periodo. El arranque queda antes del inicio analizado.
- Este objetivo abarca tres ciclos solares completos, **22–24 (septiembre de 1986–diciembre de 2019)**, y las fases ascendente y máxima del ciclo 25, todavía incompleto. No afirmar que todo el ciclo 25 está cubierto ni anticipar su duración final.
- **Inventario comprobado del CSV de aire:** cuatro series por nombre en 1986: **Berlin (12 registros), Braunschweig (12), Risoe (55) y Wien_Hohe_Warte (80)**. Los registros se asignan al año del punto medio del muestreo y tienen valor numérico, intervalo positivo y unidad declarada. Berlin y Braunschweig contienen doce intervalos mensuales; Risoe comienza en abril y Wien_Hohe_Warte tiene discontinuidades. Presencia durante un año no significa año completo ni emplazamiento homogéneo.
- En **1986–2005** aparecen **21 nombres distintos** a lo largo del periodo; Berlin, Braunschweig y Risoe están representados en todos esos años. No son 21 estaciones simultáneas o continuas. El criterio de valor, intervalo y unidad da **20 nombres en 2006 y 49 en 2009**. El archivo completo tiene 91 nombres y comienza en 1983, pero el objetivo de simulación sigue siendo 1986. Los nombres requieren armonización histórica antes de contarlos como estaciones físicas.
- **2009–2024** se mantiene como referencia reciente de deposición y evaluación conjunta donde existan pares válidos, así como periodo específico de la Tabla 2. La correspondencia DWD documenta precipitación diaria desde 2009. El CSV auditado contiene aire: no confirma deposición ni pares continuos concentración–deposición desde 1986.
- Los registros tempranos permiten comprobar respuestas a condiciones solares y meteorológicas distintas mediante segmentos de estación documentados. La discriminación conjunta en red se concentra en la cobertura reciente; la evaluación histórica utiliza los registros y variables realmente disponibles, con subconjuntos estables y pesos de agregación fijos.
- **Continuidad de entradas históricas pendiente de inventario:** WP1 verifica meteorología, producción y fronteras. Si una discontinuidad impide el objetivo completo, se conserva la matriz de tres configuraciones y dos tratamientos sobre un periodo común: **2009–2024 será el núcleo de contingencia una vez verificadas sus entradas**, con extensión retrospectiva continua donde lo permitan los archivos. Se actualizan expresamente la cobertura solar, los bloques de evaluación y el alcance de las conclusiones. La contingencia responde a continuidad de entradas, no a una falta de respaldo computacional de AU.
- Bloquear años de evaluación antes del ajuste y añadir datos posteriores mediante una extensión predefinida. Mantener el cambio metodológico de 2018 y los cambios de emplazamiento en el inventario.

## Rutas importantes

Las rutas de entrega son relativas a esta carpeta para continuar desde otro ordenador.

- **Editar a partir de:** [Word v9.5](STRAT_TRACE_MSCA_PROPOSAL_v9_5.docx).
- **Comprobar presentación:** [PDF v9.5](STRAT_TRACE_MSCA_PROPOSAL_v9_5.pdf).
- **Pendientes de candidatura y detalles de preparación científica:** [Notas para el envío v9.5](NOTAS_PARA_EL_ENVIO_v9_5.md).
- **Recuentos y controles del CSV:** [Auditoría de cobertura de ⁷Be](AUDITORIA_COBERTURA_BE7.md).
- **Contenido, revisión final e integridad:** [README](README.md) y [manifiesto SHA-256](MANIFEST_SHA256.json).
- **Antecedentes conservados en el repositorio:** [paquete v9.2–v9.4 del 7 de septiembre](../STRAT_TRACE_2026-09-07/). No sobrescribir estas versiones; crear una versión nueva en la siguiente revisión.
- **Fuente del inventario, en el ordenador de trabajo:** `C:\Users\Master\Downloads\Be7_en_aire_all_stations_1.csv`; SHA-256 `a2a9df8aad0a0e6c519b028b2702023756a7aebe320f147a4d1e5d1f21b36030`. Esta ruta local no implica que el archivo exista en el portátil.
- El paquete contiene documentos, auditoría y estado de trabajo. **No incluye el CSV original, las hojas DWD privadas, la correspondencia privada ni el código completo de DEHM.** Preservar originales y permisos cuando se incorporen al trabajo del portátil.

## Resultados ya demostrados

- La auditoría del CSV verificó **72.943 registros, 91 nombres de estación y cuatro series en 1986**. Conservó el original e identificó incidencias de fechas, unidades, duplicados y coordenadas. Es un inventario de disponibilidad, no una validación metrológica completa ni un panel de evaluación ya aprobado.
- El investigador confirma el respaldo de AU a capacidad y calendario para toda la matriz propuesta. Este respaldo no equivale a un ensayo de rendimiento realizado ni verifica por sí solo la continuidad de los archivos históricos.
- La implementación previa de ⁷Be en DEHM está descrita en EGU26-20989. No utilizar ese abstract como fuente de los porcentajes siguientes.
- **Tabla 2, análisis preparatorio suministrado por el investigador:** DEHM de 25 km respecto a 75 km, JJA 2009–2024, **79 ubicaciones de muestreo del modelo**, con posibles celdas compartidas: **+5,9 %** en concentración, **+13,6 %** en deposición total y **−45,9 %** en precipitación. Son contrastes del modelo con ese alcance y cálculo; no equivalen a 79 estaciones independientes ni a una validación de toda la red. Conservar su cálculo reproducible y procedencia privada.
- **Revisión documental de v9.5 completada:** Word generado sin alterar v9.4; PDF de diez páginas revisado visualmente página por página, sin cortes ni desbordamientos. Las diez fuentes utilizadas están incrustadas. La revisión independiente del contenido confirma coherencia de periodos, recursos, tratamientos de producción y alcance observacional. No se han ejecutado las nuevas simulaciones.

## Hipótesis abiertas

- **H1:** las modificaciones de eliminación húmeda generan respuestas dependientes del origen, superiores a la incertidumbre numérica y de muestreo.
- **H2:** las observaciones conjuntas de aire y deposición distinguen explicaciones que la concentración por sí sola deja sin resolver.
- **H3:** las explicaciones respaldadas por presupuestos mantienen habilidad conjunta en años y regímenes reservados; los controles de producción fija evalúan su dependencia de la fuente.
- La mayor deposición con menor lluvia motiva evaluar disponibilidad del trazador y exposición a eliminación. Siguen abiertas las contribuciones relativas de producción, aporte de frontera, transporte, mezcla y eliminación.
- Falta demostrar reconstrucción y cierre de las etiquetas, sensibilidad a límites de presión, convergencia del arranque, discriminación sintética y transferencia a años/estaciones reservados. La tolerancia de reconstrucción propuesta es inferior al 0,1 % por encima de un umbral absoluto y al menos diez veces menor que la respuesta mínima interpretada. La recuperación ≥80 % con falsa discriminación ≤5 % es un objetivo, no un resultado obtenido.
- La posible recuperación DWD de registros digitales antiguos y papel de 1980–1996 sigue pendiente de recepción, verificación y cotejo con lo ya disponible. No contar esos materiales como datos nuevos incorporados ni como pares aire–deposición confirmados.

## Análisis descartados

- Añadir otro modelo a la matriz central o presentar configuraciones antiguas como protocolo vigente.
- Mantener la descripción de una única estación desde 1986; confundir nombres de archivo con estaciones físicas homogéneas; interpretar presencia anual como cobertura completa; o atribuir al CSV de aire una validación histórica de deposición.
- Afirmar que los contrastes preliminares prueban descenso más rápido, sesgo observacional, efecto climático o un resultado definitivo para todas las estaciones.
- Interpretar UPPER + TOP como contribución estratosférica completa: el techo próximo a 100 hPa y las bandas de presión impiden esa equivalencia.
- Equiparar concentración de frontera fija con flujo de masa constante; atribuir toda la estacionalidad a transporte/eliminación con fronteras estacionales; o asumir que una normalización escalar elimina todos los efectos de producción.
- Comparar periodos distintos entre configuraciones, extrapolar validación fuera de la cobertura observada o ajustar con los bloques reservados para evaluación.
- Convertir valoraciones informales de 95–98 puntos en una puntuación contrastada o una probabilidad de financiación. El respaldo computacional de AU está confirmado por el investigador y no debe volver a presentarse como permiso pendiente.

## Siguiente pregunta científica

**¿En qué estaciones, años y regímenes las observaciones conjuntas de concentración y deposición permiten distinguir cambios de aporte atmosférico de cambios en eliminación húmeda, una vez controladas la producción solar, las fronteras y el muestreo?**

Para retomarlo: partir de v9.5 y las notas; convertir el inventario histórico en segmentos de estación y variable verificados; inventariar la continuidad de entradas, aplicar la contingencia declarada solo si hace falta y organizar las ejecuciones con el respaldo computacional ya confirmado; verificar etiquetas, fronteras y arranque; fijar los bloques independientes antes del ajuste. Mantener separados hechos confirmados, hipótesis y tareas previstas. La elegibilidad y los restantes comprobantes de envío se gestionan en las notas.
