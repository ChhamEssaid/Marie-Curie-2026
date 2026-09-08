# STRAT-TRACE — estado actual v9.9

Edición científica v9.9 finalizada el **8 de septiembre de 2026, 04:55, Europe/Madrid**. Snapshot de publicación: **8 de septiembre de 2026, 08:25:07, Europe/Madrid**. El Word y el PDF conservan exactamente los bytes de la edición revisada.

## Documento desde el que continuar

- [Propuesta Word v9.9](STRAT_TRACE_Proposal_v9.9.docx).
- [PDF de control v9.9](STRAT_TRACE_Proposal_v9.9.pdf), diez páginas.
- [Cambios de esta revisión](CAMBIOS_v9.9.md).
- [Cobertura observacional comprobada](AUDITORIA_COBERTURA_BE7.md).
- [Notas de preparación y envío](NOTAS_PARA_EL_ENVIO.md), fuera de Part B1.

El título científico sigue siendo **STRAT-TRACE — Source-tagged ⁷Be for process-aware aerosol model evaluation**. Los nombres de los archivos se mantienen simples. Esta versión parte directamente de v9.7; v9.8 fue descartada por el investigador y no se reincorporan sus recortes opcionales. Ninguna versión anterior se sobrescribe.

## Cambios incorporados

1. **Mentoría concreta.** Zhuyun Ye sigue como supervisora principal. Jesper **Heile** Christensen, Senior Researcher de AU y desarrollador principal de DEHM, aporta mentoría complementaria en desarrollo del modelo, diseño de sensibilidades e interpretación modelo–observación. Su experiencia publicada en asimilación química respalda esta función; no se le atribuye una especialización no comprobada en todos los métodos de inferencia previstos. El investigador ha identificado a Jesper para este papel. No se afirma una relación jerárquica directa con Zhuyun.
2. **Supervisión y formación.** Reuniones semanales con Ye, revisiones trimestrales con Christensen y plan de carrera acordado en M1, revisado cada seis meses. Ye coordina la formación específica en problemas inversos. Christensen asesora también la componente DEHM de la futura propuesta.
3. **Carrera independiente.** Para M24, preparar concepto científico, colaboraciones y presupuesto de una propuesta posterior sobre transporte y eliminación de ⁷Be por tamaños de partícula con DEHM. Se menciona NERD de Novo Nordisk como posible convocatoria futura, si se cumplen sus reglas. Las nuevas medidas corresponden a financiación posterior; no se añaden campañas ni configuraciones a la MSCA. Se mantienen dos envíos de manuscritos como objetivo, la publicación de herramientas y los 24 PM.
4. **Evidencia observacional.** La sección 1.1 cuantifica más de 54.000 registros en aire de 83 series identificadas por nombre durante 2009–2024 tras comprobaciones iniciales. CTBTO mantiene el acuerdo firmado, con entrega de datos pendiente. Estos registros no son pares aire–deposición ni 83 emplazamientos ya homogeneizados.
5. Se actualizan coherentemente las tablas de formación y WP5, y se añaden las referencias institucionales y bibliográficas [24]–[26].

## Diseño científico que se conserva

- **DEHM único**, configuración reducida de 75 km y 29 capas, techo próximo a 100 hPa. Se conservan transporte, mezcla, decaimiento y deposición húmeda/seca.
- **Tres ajustes de eliminación húmeda** con meteorología, periodo y demás operadores comunes. Cada ajuste incluye producción variable y producción fija. Etiquetas por región de producción y entrada de frontera, más total independiente. Verificar reconstrucción y presupuestos antes de interpretar fracciones o reponderaciones.
- **1986–2024/2025** como ventana principal: 39/40 años naturales, tres ciclos solares completos 22–24 y fases ascendente y máxima del ciclo 25 todavía incompleto. Finalizar en 2025 donde las entradas sean consistentes, en otro caso 2024. El arranque precede al periodo analizado.
- **2009–2024** sigue como base reciente de deposición y evaluación conjunta donde se verifiquen pares. Los registros históricos aportan pruebas temporales dentro de sus segmentos y variables válidos; no se afirma validación homogénea de tres ciclos solares.
- **Producción CRAC:Be variable** para comparar con observaciones; compañeros de producción fija y controles normalizados para diagnosticar dependencia de la fuente. La normalización no se presupone equivalente a eliminar todos los efectos espaciales o retardados de producción.
- **Frontera superior:** n_top = Q_CRAC(100 hPa, latitud, tiempo)/λ₇, en átomos kg⁻¹ de aire. Q se expresa en átomos kg⁻¹ s⁻¹. Es una aproximación local de equilibrio producción–decaimiento, dependiente de latitud y actividad solar. TOP contabiliza el aporte realizado por la frontera; UPPER + TOP no representa toda la contribución estratosférica. La concentración fija de frontera no significa flujo fijo de masa.
- Los controles de producción fija conservan el vínculo entre Q fija y TOP. LATERAL repite una climatología anual; el flujo realizado sigue dependiendo de la meteorología y se contabiliza. Si no puede controlarse su variabilidad, limitar la atribución como describe el protocolo.
- Contabilidad por paso temporal, unidades y signos explícitos, transferencias internas iguales y opuestas, términos de cambio de banda y almacenamiento. Cierre del dominio obligatorio. Tolerancia propuesta inferior al 0,1 % por encima de un umbral absoluto, y diez veces menor que la respuesta interpretada.
- Selección y evaluación en bloques independientes, ventanas reales de muestreo, errores y dependencia espacial/temporal. Objetivo de recuperación sintética ≥80 % con falsa discriminación ≤5 %; es un criterio previsto, no un resultado. Conservar resultados de no discriminación cuando corresponda.
- Comparación preliminar de resolución de la Tabla 2: **79 ubicaciones de muestreo del modelo**, JJA 2009–2024, posibles celdas compartidas; medianas espaciales de 100 × (fina/gruesa − 1): concentración +5,9 %, deposición +13,6 %, precipitación −45,9 %. No confundir con el inventario de 83 series observadas.

## Datos y procedencia

El archivo europeo de aire procede principalmente de **JRC**, conservando atribución a los programas nacionales originales. **DWD** aporta medidas de aerosol/deposición y metadatos de estaciones, métodos, unidades y precipitación. El acuerdo **CTBTO**, firmado por Chham y Ye según confirma el investigador, prevé ampliar el archivo internacional, principalmente desde aproximadamente 2000. Los datos CTBTO aún no se han recibido; no sumar una red esperada de más de 80 estaciones al inventario europeo ni dar por confirmada su cobertura utilizable.

CSV fuente local, solo lectura: `C:/Users/Master/Downloads/Be7_en_aire_all_stations_1.csv`. SHA-256: `a2a9df8aad0a0e6c519b028b2702023756a7aebe320f147a4d1e5d1f21b36030`. El archivo completo contiene 72.943 filas y 91 nombres. El filtro de valor, intervalo y unidad conserva 54.246 registros de 83 nombres en 2009–2024; al excluir grupos de duplicados ambiguos e intervalos superiores a 366 días quedan 54.124 registros y los mismos 83 nombres. Las cuatro series de 1986 son Berlin, Braunschweig, Risoe y Wien_Hohe_Warte. Ver auditoría para fechas, alcance y limitaciones.

El inventario de aire no demuestra pares con deposición. WP1 verifica alias, traslados, continuidad, unidades, ventanas, métodos y solapamientos entre proveedores. La transición DWD de 2018 se trata como estrato de método. Los detalles técnicos de fracciones de muestra quedan en notas de trabajo, fuera de Part B1. No atribuir a una fracción de filtro una medición independiente de deposición seca atmosférica sin comprobar el colector.

La recuperación histórica adicional de DWD sigue en curso; no contar archivos en papel o series anunciadas como datos nuevos recibidos. Las observaciones restringidas se solicitan a los proveedores y no se redistribuyen sin permiso.

## Recursos y productos

AU ha confirmado, según el investigador, capacidad y calendario para toda la matriz y la reserva del 20 %. Se mantienen 117/120 años-configuración con producción variable y hasta 234/240 con compañeros fijos ejecutados por separado. Los trazadores concurrentes se contabilizan mediante el ensayo previsto; WP2 conserva 78/80 y WP3 156/160 años-configuración si las ejecuciones son separadas.

A 6 MB por archivo horario, seis ejecuciones de 1986–2024/2025 equivalen a aproximadamente 12,3/12,6 TB para ese conjunto de variables. Los más de 600 TB citados son capacidad institucional, no espacio exclusivo del proyecto. El DMP M3 y los ensayos WP1 concretan campos etiquetados, episodios 3D, entradas, copias, puntos de reinicio, retención y mantenimiento.

Productos curados diarios/mensuales, datos que sustentan publicaciones y herramientas reutilizables con DOI, metadatos FAIR y licencias compatibles con AU y dependencias. Interfaz ligera para descargar subconjuntos publicados por periodo, zona, variable y resolución disponible, sin autorización personal por descarga. El código DEHM mantiene su régimen propio. Toda esta labor se integra en los 5 PM de WP5; no existe todavía una interfaz implementada.

## Pendientes científicos y de candidatura

- Verificar en WP1 continuidad de meteorología, producción y fronteras históricas. La contingencia mantiene todos los ajustes y ambos tratamientos sobre el periodo continuo común verificado más largo, priorizando 2009–2024. Actualizar a la vez cobertura solar y bloques de evaluación. La contingencia responde a entradas, no a dudas sobre el respaldo de AU.
- Ejecutar comprobaciones de etiquetas, cierre, linealidad, arranque, sensibilidad de fronteras, recuperación y evaluación independiente. No se han ejecutado nuevas simulaciones en esta revisión documental.
- Inventariar entregas CTBTO y pares aire–deposición. El acuerdo no vuelve a presentarse como pendiente de firma.
- NERD se cita como vía posible de financiación futura; verificar condiciones de la convocatoria aplicable cuando corresponda. No se garantiza elegibilidad futura ni concesión, ni se condiciona la MSCA a ese resultado.
- Mantener los comprobantes administrativos y la elegibilidad de la candidatura en las notas de envío. Ninguna puntuación informal equivale a evaluación oficial ni probabilidad de financiación.

## Archivo y sincronización

Esta carpeta es la **referencia v9.9 para continuar el trabajo**. La [v9.7 original](../STRAT_TRACE_2026-09-08_00-50-33_Madrid/) permanece en el repositorio. Procedencia local, fuera de este snapshot: la copia v9.7 con nombres simples se conserva en `STRAT_TRACE_2026-09-08_01-33-56_Madrid`; la edición local v9.9 de origen, en `STRAT_TRACE_2026-09-08_04-43-50_Madrid`.

**Repositorio de referencia:** [ChhamEssaid/Marie-Curie-2026](https://github.com/ChhamEssaid/Marie-Curie-2026), rama `main`, carpeta `STRAT_TRACE_2026-09-08_08-25-07_Madrid`. El investigador solicita actualizar GitHub el 8 de septiembre de 2026. Este snapshot se prepara desde la rama remota que contiene v9.7 y excluye el commit local de v9.8 descartado. Los documentos anteriores se preservan; el README y el CURRENT_STATE de entrada apuntan a v9.9. El resultado del envío y su commit se verifican en el registro local de publicación.

**Correo:** no se ha enviado ningún mensaje. El identificador del borrador anterior devuelve 404 y no aparece entre los borradores recientes inspeccionados. No se han modificado otros borradores ni creado otro para sustituirlo. Los archivos de esta carpeta están preparados para adjuntar cuando se retome el correo.

El paquete compartible contiene propuesta, PDF, estado, cambios, auditoría y notas. No incorpora el CSV original, datos DWD/CTBTO, contratos, correos privados ni código DEHM. `work/` conserva únicamente auxiliares de edición y control locales y queda excluido del paquete compartible.
