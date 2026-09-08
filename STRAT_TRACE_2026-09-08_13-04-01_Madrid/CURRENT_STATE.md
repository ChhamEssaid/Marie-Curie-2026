# STRAT-TRACE — v9.11 candidata a versión final

Carpeta de revisión: **8 de septiembre de 2026, 13:04:01, Europe/Madrid**. Cierre del paquete: **2026-09-08T13:17:33+02:00**. Nueva revisión de v9.10; versiones anteriores intactas.

## Documento desde el que continuar

- [Propuesta Word v9.11](STRAT_TRACE_Proposal_v9.11.docx).
- [PDF de control v9.11](STRAT_TRACE_Proposal_v9.11.pdf), diez páginas revisadas.
- [Cambios](CAMBIOS_v9.11.md).
- [Auditoría de cobertura](AUDITORIA_COBERTURA_BE7.md).
- [Notas para el envío](NOTAS_PARA_EL_ENVIO.md), fuera de la propuesta.

Título científico: **STRAT-TRACE — Source-tagged ⁷Be for process-aware aerosol model evaluation**. Zhuyun Ye sigue como supervisora principal y Jesper Heile Christensen como mentor complementario. Se conservan las cuatro mejoras de v9.10, las 43 series conjuntas, CTBTO diario esperado, el plan de carrera y la mentoría aprobada. La v9.8 descartada no se reincorpora.

## Cambios de v9.11

1. **Apertura más sobria.** Se conserva el título científico exacto y se simplifica su tipografía. La presentación muestra Essaid Chham, Aarhus University, Zhuyun Ye y la duración de 24 meses. Se retiran las etiquetas visibles «European Postdoctoral Fellowship» y «Part B1»; la modalidad administrativa y la estructura MSCA no cambian.
2. **Cabecera y pie.** STRAT-TRACE queda a la izquierda y Essaid Chham alineado al extremo derecho en todas las páginas. Se retiran la institución y la línea decorativa de la cabecera. El pie contiene solo el número de página.
3. **Metodología accesible.** Después de la ecuación y sus definiciones se explica que, tras verificar el presupuesto dentro de la tolerancia, se comparan concentraciones y deposición con los intervalos reales de medida para comprobar la discriminación entre aporte y eliminación.
4. **Párrafos más breves.** Se separa el inventario reciente de la cobertura histórica/CTBTO en 1.1, y los controles de producción de su interpretación en 1.2. Se compactan las frases repetidas de verificación y resultados para conservar diez páginas sin reducir letra ni márgenes del cuerpo.
5. **Impacto más concreto.** La sección 2.3 explica que las pruebas conjuntas comprueban la consistencia entre concentración y deposición y evalúan si los errores compensatorios son una explicación plausible. Se precisa la utilidad de la nota observacional para orientar mediciones; la transferencia a otros contaminantes sigue requiriendo validación posterior.
6. **Dos ajustes de precisión.** «Will resolve this question» pasa a «will test these explanations» y se aclara que los compañeros de producción variable/fija comparten meteorología y operadores dentro de cada ajuste húmedo.

Se mantienen reuniones semanales con Ye y revisiones trimestrales con Christensen, con sus responsabilidades. No se inventa una dedicación horaria adicional. Los controles, tablas, ecuación nativa y fuentes bibliográficas permanecen. La opción Zheng sigue documentada como alternativa a valorar, sin sustituir el contorno central.

## Estado de la candidata final

La revisión editorial y visual está completada: diez páginas, cabecera y numeración correctas, todas las fuentes incrustadas y ninguna tabla cortada. Se han conservado el tamaño de letra y los márgenes del cuerpo, y las diez tablas son idénticas a v9.10. El Word no contiene comentarios ni cambios pendientes de aceptar. La denominación «candidata final» pertenece al estado de trabajo, no aparece como etiqueta de borrador en la propuesta.

Las comprobaciones administrativas y de coherencia con el formulario/CV permanecen en las notas de envío. No se ha presentado la candidatura ni enviado ningún correo. El alcance de esta revisión es documental; no se han ejecutado nuevas simulaciones.

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

## Datos y procedencia — estado vigente

**JRC** es la vía principal de obtención del archivo europeo de aire, según el investigador, con atribución conservada a los programas nacionales. **DWD** aporta medidas de aerosol, deposición y metadatos. **CTBTO** aportará la extensión de aire con acuerdo ya firmado por Chham y Ye; la entrega permanece pendiente.

**43 estaciones europeas con ambas variables disponibles:** afirmación del investigador corroborada por 42 series en `deposicion_all_stations.csv` que tienen aire en el archivo recibido, más **Brocken**, presente en el original DWD `2009-2026_Be-7_Prec_corr2.xlsx` y en aire. No describir la deposición como un recurso inexistente o meramente esperado. WP1 establece ventanas comparables, continuidad y segmentos de método; 43 no significa 43 estaciones continuas durante cada año ni un número de intervalos ya emparejados.

**87 frente a 83 series de aire:** 87 nombres tienen valores numéricos no negativos e intervalos positivos en 2009–2024 antes de exigir unidad; 83 cumplen además la unidad explícita equivalente a Bq/m³. Se conservan más de 54.000 registros de 83 series en Part B1. Cattenom, Civaux, Saint_Aignan_Grandlieu y Tomblaine requieren recuperar la unidad en los metadatos de origen. No se infiere ni se corrige el CSV. Las cuatro series con datos en 1986 son Berlin, Braunschweig, Risoe y Wien_Hohe_Warte.

**CTBTO diario:** el investigador confirma esta resolución prevista y estima alrededor de 80 sitios, principalmente desde 2000, con aproximadamente 30 comunes al archivo europeo. Los países y años útiles se verifican al recibir la entrega y dentro de la cobertura DEHM. La operación aproximada 87 + 80 − 30 = 137 es una expectativa de unión nominal de aire, no una red recibida, simultánea ni de pares aire–deposición; no se utiliza como recuento principal de la propuesta.

La transición DWD de 2018 se mantiene como estrato de método. Los originales DWD incluyen columnas de incertidumbre y límites de detección; conservarlas al preparar los datos. Los detalles técnicos se reservan al protocolo, sin sobrecargar Part B1. La recuperación histórica adicional sigue en curso. Las observaciones restringidas se solicitan al proveedor; no se redistribuyen en este paquete.

## Opción de contorno de Zheng — valoración y siguiente decisión

El investigador propone utilizar concentraciones de ⁷Be de los resultados de Zheng alrededor de 100 hPa. Su respuesta afirmativa confirma la posibilidad de obtener los campos tridimensionales adecuados; no especifica los años exactos. Esta revisión conserva en Part B1 la formulación central Q/λ y documenta la alternativa aquí, sin presentar una sustitución ya decidida.

La alternativa es científicamente razonable: un modelo global con mayor extensión vertical puede aportar concentraciones que incorporen transporte, mezcla y decaimiento del reservorio situado por encima del techo de DEHM. Esta es una inferencia física, no una mejora de resultados ya medida. Mantener un campo externo prescrito permitiría conservar DEHM como único modelo de los experimentos controlados. TOP seguiría midiendo entrada de frontera, no todo el origen estratosférico, y el techo de DEHM seguiría cerca de 100 hPa.

El [artículo de Zheng et al. (2023)](https://gmd.copernicus.org/articles/16/7037/2023/) utiliza GEOS-Chem 14.0.2 con MERRA-2, 72 niveles hasta 0,01 hPa y analiza 2008–2018 después de seis años de arranque. El [archivo público enlazado](https://zenodo.org/records/8372652) incluye model_output_P16spa.zip. No se ha descargado ni inspeccionado ese archivo voluminoso: no se da por demostrada la disponibilidad pública de la variable, frecuencia o cobertura 1986–2025 requerida.

Antes de elegirlo como contorno central, concretar periodo y frecuencia, coordenadas de presión, unidades/base de masa, interpolación, arranque, tratamiento CRAC:Be y coherencia temporal con la meteorología DEHM. Usar exactamente el mismo campo en los tres ajustes húmedos. Si ya se entrega en átomos kg⁻¹ de aire, no volver a dividir por λ. Si se entrega actividad por volumen, convertir con n = A/(λ × ρ_aire), manteniendo la base de masa correcta.

El compañero de producción fija requiere también un control coherente de TOP: fijar solo la producción interna mientras se deja una frontera solarmente variable no elimina toda la variabilidad externa. Una climatología repetida elimina la variabilidad interanual impuesta y conserva la estacionalidad; no equivale por sí sola a un modelo global con producción fija.

Recomendación registrada: empezar con una sensibilidad acotada sobre el periodo común disponible que evalúe la aproximación local de equilibrio. Decidir después, con inventario y controles definidos, si se propone la sustitución completa. No añadir nuevas ejecuciones de GEOS-Chem a la matriz MSCA ni atribuir cobertura histórica no confirmada.

## Recursos y productos

AU ha confirmado, según el investigador, capacidad y calendario para toda la matriz y la reserva del 20 %. Se mantienen 117/120 años-configuración con producción variable y hasta 234/240 con compañeros fijos ejecutados por separado. Los trazadores concurrentes se contabilizan mediante el ensayo previsto; WP2 conserva 78/80 y WP3 156/160 años-configuración si las ejecuciones son separadas.

A 6 MB por archivo horario, seis ejecuciones de 1986–2024/2025 equivalen a aproximadamente 12,3/12,6 TB para ese conjunto de variables. Los más de 600 TB citados son capacidad institucional, no espacio exclusivo del proyecto. El DMP M3 y los ensayos WP1 concretan campos etiquetados, episodios 3D, entradas, copias, puntos de reinicio, retención y mantenimiento.

Productos curados diarios/mensuales, datos que sustentan publicaciones y herramientas reutilizables con DOI, metadatos FAIR y licencias compatibles con AU y dependencias. Interfaz ligera para descargar subconjuntos publicados por periodo, zona, variable y resolución disponible, sin autorización personal por descarga. El código DEHM mantiene su régimen propio. Toda esta labor se integra en los 5 PM de WP5; no existe todavía una interfaz implementada.

## Pendientes científicos y de candidatura

- Completar en WP1 el inventario histórico de meteorología, producción y fronteras y mantener el periodo común previsto en la contingencia. El respaldo computacional de AU ya está confirmado por el investigador.
- Armonizar los intervalos de las 43 series conjuntas y conservar cambios de emplazamiento, unidades, métodos, incertidumbres y límites de detección. La disponibilidad está corroborada; la validación metrológica y el emparejamiento final siguen como tareas de WP1.
- Recibir e inventariar CTBTO: fechas, resolución efectiva, cobertura y duplicados. No volver a pedir confirmación de la firma del acuerdo.
- Concretar los archivos y años de Zheng antes de decidir una modificación del contorno central; conservar coherencia entre producción variable y fija.
- Ejecutar los controles de reconstrucción, masa, arranque, linealidad, recuperación y evaluación independiente previstos. No se han ejecutado nuevas simulaciones en esta revisión documental.
- Seguir las notas administrativas de envío y revisar el archivo descargado del portal tras presentarlo. Ninguna valoración informal garantiza puntuación o financiación.

## Archivo y sincronización

Esta carpeta es la **referencia v9.11 para continuar o preparar el envío**. La [v9.10](../STRAT_TRACE_2026-09-08_12-22-52_Madrid/) y las demás versiones históricas permanecen intactas. Fuente Word v9.10, SHA-256: `b87fd8d939f2d67efae8a5ebd69a2f9fcc299f021d4f9f56ab6fef2c2f51328a`.

Repositorio autorizado: [ChhamEssaid/Marie-Curie-2026](https://github.com/ChhamEssaid/Marie-Curie-2026), rama `main`, carpeta `STRAT_TRACE_2026-09-08_13-04-01_Madrid`. Los archivos de entrada del repositorio apuntan a esta candidata final. El resultado de publicación se comprueba contra el commit remoto y los archivos del manifiesto, y se registra localmente.

El paquete compartible contiene Word, PDF, estado, cambios, auditoría, notas, README y manifiesto. Los auxiliares de `work/` quedan locales. No se adjuntan datos originales restringidos, contratos, correspondencia privada ni código DEHM.
