# STRAT-TRACE v9.5 — notas de trabajo para el envío

Estado: **7 de septiembre de 2026, 21:19:44, Europe/Madrid**. Documento de trabajo separado de la propuesta; no forma parte de Part B1 ni del PDF de candidatura. Consultar [CURRENT_STATE](CURRENT_STATE.md) para el diseño vigente y [README](README.md) para el registro final de comprobaciones de esta entrega.

## Cambios de criterio incorporados

El investigador confirma el respaldo de AU a cualquier tiempo de cálculo propuesto para la matriz completa. Se trata como confirmación de capacidad y calendario, incluidos compañeros de producción fija, arranque y reserva. No queda una nueva solicitud de confirmación computacional pendiente. Los ensayos iniciales sirven para organizar la ejecución y precisar rendimiento y almacenamiento.

Los detalles del filtro, resina, nombres de método y armonización de muestras DWD permanecen en estas notas. En Part B1 basta describir la comparación con el observable adecuado, intervalos reales y control de cambios de método y emplazamiento. Se conserva el detalle técnico para preparar correctamente los datos sin sobrecargar la candidatura.

La auditoría del CSV sustituye la afirmación anterior de una estación desde 1986 por disponibilidad verificada de varias series históricas. La continuidad de entradas del modelo sigue pendiente de inventario, independientemente del respaldo computacional.

## Cobertura observacional comprobada

Fuente: `Be7_en_aire_all_stations_1.csv`, 72.943 filas y 91 etiquetas de nombre, preservado sin modificaciones. Los nombres del archivo no equivalen automáticamente a estaciones físicas homogéneas. El archivo incluye datos desde 1983; el objetivo de simulación continúa siendo 1986–2024/2025.

| Serie en 1986 | Registros con año del punto medio en 1986 | Alcance comprobado |
|---|---:|---|
| Berlin | 12 | Doce intervalos mensuales; verificar historia de coordenadas. |
| Braunschweig | 12 | Doce intervalos mensuales. |
| Risoe | 55 | Desde abril; presencia no equivale a cobertura anual completa. |
| Wien_Hohe_Warte | 80 | Registros durante el año con discontinuidades. |

Estas cuatro series tienen valores numéricos, intervalos positivos y unidades declaradas de Bq m⁻³. Durante 1986–2005 aparecen 21 nombres distintos; Berlin, Braunschweig y Risoe tienen registros en cada año. No describir esos 21 nombres como una red simultánea o continua. Con el criterio de valor, intervalo y unidad explícita aparecen 20 nombres en 2006 y 49 en 2009.

El [informe de auditoría](AUDITORIA_COBERTURA_BE7.md) documenta criterios y recuentos anuales. Señala, entre otras incidencias, intervalos nulos o negativos, tres intervalos superiores a 366 días, unidades ausentes, duplicados y coordenadas que requieren comprobación. El inventario demuestra disponibilidad; falta completar el control metrológico y determinar los segmentos utilizables para comparación con el modelo.

**2009–2024** permanece como referencia reciente de deposición y evaluación conjunta donde existan pares válidos, y como periodo de la Tabla 2. El CSV auditado contiene aire y no demuestra deposición ni pares continuos desde 1986. Mantener separados la cobertura por variable, los años de simulación y el soporte de cada resultado.

## Preparación de los datos DWD — fuera de Part B1

La comunicación aportada por el investigador describe una posible recuperación de registros digitales antiguos hasta 1996 y registros en papel de 1980–1996 para **Offenbach, Hamburg, München y Berlin**. No se han recibido ni verificado esas hojas y documentos en esta revisión. Al incorporarlos, cotejarlos con los registros ya existentes para evitar contar solapamientos como nuevas estaciones o nuevos años.

La frase «hasta 2008» en la comunicación no basta para fijar los extremos exactos de los archivos: verificar fechas en las hojas originales. Los posibles huecos de aerosoles de 2010 y los registros de la base antigua deben identificarse por estación e intervalo. No interpretar una extracción en curso como disponibilidad completa ya confirmada.

Conservar explícitamente los cambios de emplazamiento comunicados: Berlin-Tempelhof → Potsdam (2011), Stuttgart → Rheinstetten (2010) y Stötten → Stuttgart (2018). Los pares Aachen/Aachen-Orsbach y Lingen/Lingen-Baccum se describen como alias en el correo; armonizarlos después de contrastar identificadores y metadatos. Un traslado físico requiere segmentos distintos aunque se mantenga un nombre de red.

Para el sistema de recogida descrito desde 2018, el agua pasa por filtro y resina de intercambio iónico; ambas fracciones se miden. La denominación de laboratorio «deposición seca» para la fracción insoluble del filtro **no demuestra una separación física entre flujo atmosférico seco y húmedo**. Antes de combinar `_Fil` y `_Ion`, comprobar que representan la misma muestra, intervalo y área de recogida, con unidades, normalización, corrección de decaimiento e incertidumbres compatibles. Tratar `NWG` como límite de detección y conservar las no detecciones como censura; no sustituirlas por cero. La elección de deposición húmeda o total del modelo debe basarse además en la exposición y funcionamiento documentados del colector.

Estas verificaciones pertenecen al protocolo de preparación científica. La propuesta mantiene una descripción breve del emparejamiento de observables y controles metodológicos. No adjuntar al repositorio público las hojas, la correspondencia privada ni datos originales sujetos a permisos.

## Recursos, calendario y continuidad histórica

**Confirmación del investigador del 7 de septiembre de 2026:** AU respalda la capacidad y el calendario de toda la matriz propuesta, incluidos los diagnósticos de producción fija, el arranque y la reserva. Conservar esta atribución en el estado de trabajo; no inventar un certificado, contacto, cuota de CPU o rendimiento medido.

Tres configuraciones húmedas durante 39/40 años representan 117/120 años-configuración con producción variable. Si los compañeros fijos se calculan por separado, añaden 117/120 y el total es 234/240, antes de arranque y reserva del 20 %. Si se integran conjuntamente, el coste adicional corresponde a especies y diagnósticos y se cuantifica con los ensayos operativos. WP2 incluye referencia y compañero fijo; WP3 incluye las dos sensibilidades y sus compañeros. No atribuir a WP3 los 117/120 años adicionales completos.

WP1 inventaría entradas WRF/ERA5, producción y fronteras, y organiza ensayos con los 14 trazadores, presupuestos y entradas/salidas. Los ensayos concretan ejecución, memoria y almacenamiento. **El respaldo computacional no depende de obtener una confirmación adicional en MS1.**

La disponibilidad de ERA5 en un catálogo no demuestra que todo el archivo WRF y las demás entradas DEHM estén preparados. Si existen discontinuidades, mantener las tres configuraciones y ambos tratamientos de producción sobre el mismo periodo. Usar 2009–2024 como núcleo de contingencia una vez verificadas sus entradas y ampliar retrospectivamente de forma continua donde lo permitan los archivos. Actualizar cobertura de ciclos solares, bloques de evaluación y conclusiones. No afirmar huecos concretos en 1986–1995 sin un inventario que los demuestre.

## Resultados propios, impacto y referencias

La Tabla 2 conserva los resultados suministrados por el investigador: +5,9 % en concentración, +13,6 % en deposición total y −45,9 % en precipitación; comparación JJA 2009–2024 en 79 ubicaciones de muestreo del modelo, con posibles celdas compartidas. Conservar cálculo reproducible y procedencia. EGU26-20989 respalda la implementación descrita y no es la fuente de esos porcentajes.

La transferencia prevista mantiene dos artículos y las actividades de demostración, formación y comunicación dentro de los 24 meses. Reutilizar ejemplos, código y materiales entre actividades para que la difusión tenga una dedicación proporcionada. CAMS regional reúne once modelos, incluido DEHM; ese tamaño contextualiza una vía de transferencia y no implica once equipos comprometidos ni adopción garantizada. Conservar una distinción explícita entre destinatarios, invitaciones y compromisos existentes.

La ventana larga comprueba respuestas bajo condiciones solares y meteorológicas variadas. No afirmar que elimina toda incertidumbre de representatividad, que todas las observaciones cubren tres ciclos homogéneamente ni que el ciclo 25 está completo. No utilizar puntuaciones informales de 95–98/100 o probabilidades de financiación como evidencia de evaluación.

## Comprobaciones de candidatura

- Verificar con la oficina de proyectos la fecha pertinente del primer doctorado, el cálculo de experiencia investigadora equivalente a tiempo completo y las exclusiones documentadas. La fecha anual «2018» o la fecha de expedición del diploma, por sí solas, no resuelven la elegibilidad.
- Revisar la movilidad completa durante los 36 meses anteriores al cierre. Las visitas mencionadas en el CV no sustituyen ese historial.
- La convocatoria indica cierre el 9 de septiembre de 2026 a las 17:00 CEST. Comprobar la ficha y la hora de envío del portal.
- Comprobar coherencia de Part A, CV, formación, experiencia y capacidades del centro en Part B2 con el Part B1 definitivo.
- El procedimiento descrito por REA no prevé una defensa oral del candidato: las justificaciones decisivas deben figurar en los documentos presentados.
- **Control local completado:** PDF de diez páginas revisado visualmente en todas sus páginas, con todas las fuentes incrustadas y sin cortes ni desbordamientos. El README registra la entrega. Sigue pendiente revisar el archivo descargado del portal tras la presentación.

Fuentes oficiales consultadas durante la revisión: [REA y recursos de candidatura](https://rea.ec.europa.eu/funding-and-grants/horizon-europe-marie-sklodowska-curie-actions/horizon-europe-msca-how-apply_en), [plantilla de Part B](https://ec.europa.eu/info/funding-tenders/opportunities/docs/2021-2027/horizon/temp-form/af/af_he-msca-pf_en.pdf), [reglas MSCA PF](https://marie-sklodowska-curie-actions.ec.europa.eu/actions/postdoctoral-fellowships), [procedimiento de evaluación](https://rea.ec.europa.eu/document/download/9bb9ae98-2757-49da-bc36-f99da97017ef_en?filename=MSCA+evaluation+in+Horizon+Europe.pdf), [documentación CAMS regional](https://confluence.ecmwf.int/spaces/CKB/pages/202173092/CAMS+Regional+European+air+quality+analysis+and+forecast+data+documentation) y [ciclos solares SILSO](https://www.sidc.be/index.php/SILSO/cyclesminmax).
