# STRAT-TRACE v9.6 — notas de trabajo para el envío

Estado: **8 de septiembre de 2026, 00:02:23, Europe/Madrid**. Documento de trabajo separado de la propuesta; no forma parte de Part B1 ni del PDF de candidatura. Consultar [CURRENT_STATE](CURRENT_STATE.md) para el diseño vigente y [README](README.md) para el registro final de comprobaciones de esta entrega.

## Cambios de criterio incorporados

El investigador confirma el respaldo de AU a cualquier tiempo de cálculo propuesto para la matriz completa. Se trata como confirmación de capacidad y calendario, incluidos compañeros de producción fija, arranque y reserva. No queda una nueva solicitud de confirmación computacional pendiente. Los ensayos iniciales sirven para organizar la ejecución y precisar rendimiento y almacenamiento.

Los detalles del filtro, resina, nombres de método y armonización de muestras DWD permanecen en estas notas. En Part B1 basta describir la comparación con el observable adecuado, intervalos reales y control de cambios de método y emplazamiento. Se conserva el detalle técnico para preparar correctamente los datos sin sobrecargar la candidatura.

La auditoría del CSV sustituye la afirmación anterior de una estación desde 1986 por disponibilidad verificada de varias series históricas. La continuidad de entradas del modelo sigue pendiente de inventario, independientemente del respaldo computacional.

## Procedencia y ampliación JRC CTBTO DWD

**Confirmaciones del investigador incorporadas en v9.6:** la mayoría del archivo europeo de aire fue obtenida a través del JRC de la Comisión Europea; Chham y Zhuyun Ye han firmado un acuerdo CTBTO para acceder a más datos de ⁷Be. Se mantienen como hechos aportados por el investigador. No solicitar de nuevo confirmación de la firma.

JRC es la vía principal de obtención del archivo europeo; cada medida debe conservar su productor nacional y la procedencia de la extracción. La referencia REMdb documenta el contexto público del archivo JRC y sus metadatos: no demuestra por sí sola que todas las filas del CSV auditado procedan de un producto o identificador REMdb concreto. La aportación directa de DWD sigue siendo esencial para aerosoles, deposición, pares observacionales y metadatos de emplazamiento/colector.

CTBTO amplía los datos de **concentración en aire**, con cobertura esperada principalmente desde alrededor de 2000 y posibles estaciones en Europa, Canadá, Estados Unidos, China y otros lugares. Las fechas y países proceden de la expectativa comunicada; se verifican sobre el inventario recibido. La red oficial de radionúclidos contempla **80 estaciones nominales**. Ese número no determina las estaciones contratadas, entregadas, operativas durante cada año o utilizables para ⁷Be. La propuesta no promete más de 80 series continuas ni una validación mundial desde 1986.

WP1 cotejará JRC/DWD/CTBTO por identificadores, coordenadas e historia, intervalos y magnitudes para retirar duplicados sin borrar procedencia. Se seleccionan observaciones dentro de la cobertura y resolución útil de DEHM. Los registros de aire adicionales amplían pruebas de concentración y transferencia espacial; las pruebas conjuntas requieren deposición coincidente. Las entregas posteriores siguen la extensión predefinida, sin reajustar los bloques ya reservados.

El texto del contrato CTBTO no se ha examinado ni se publica en esta revisión. Aplicar sus condiciones concretas de ámbito, acceso, atribución y publicación al recibir los datos. La referencia pública vDEC describe el mecanismo general y sus condiciones; no se usa como prueba independiente del contrato particular ni se asume que reproduce todas sus cláusulas. Los originales restringidos permanecen bajo acceso controlado; compartir código, ejemplos sintéticos y resultados/metadatos permitidos.

Fuentes públicas consultadas: [JRC REMdb](https://remon.jrc.ec.europa.eu/About/Environmental-Monitoring/REMdb), [CTBTO radionuclide monitoring](https://www.ctbto.org/our-work/monitoring-technologies/radionuclide-monitoring) y [CTBTO vDEC](https://www.ctbto.org/resources/for-researchers-experts/vdec). La procedencia concreta del archivo y la firma del acuerdo se sustentan en las confirmaciones del investigador.

## Formulación confirmada del contorno superior

El investigador confirma que el contorno en aproximadamente 100 hPa prescribe **n_top = Q_CRAC(100 hPa, latitud, tiempo) / λ₇**, en **átomos kg⁻¹ de aire**. En esta notación n_top corresponde al N usado por el investigador para describir la concentración de frontera. El inventario Nₖ de los presupuestos representa, en cambio, el número total de átomos del volumen de control.

Q_CRAC debe estar en átomos kg⁻¹ s⁻¹ y λ₇ en s⁻¹; conservar la misma base de masa de aire. Si la producción original está por gramo de aire, multiplicar por 1000 para expresarla por kg. La concentración impuesta varía con la latitud y la actividad solar. La fórmula representa una **aproximación de equilibrio local entre producción y decaimiento**, sin resolver explícitamente acumulación y circulación de toda la atmósfera situada encima del techo. Cuando Q cambia se aplica ese equilibrio de forma local; no se reconstruye con ello toda la historia externa de transporte y decaimiento.

Las celdas resueltas reciben tasas de producción; el techo recibe una concentración prescrita. TOP contabiliza el aporte realizado por esta condición, separado de UPPER/MIDDLE/LOWER. Verificar en WP1 si la imposición entra como intercambio de flujo, reposición de inventario u otro operador, y registrar cada adición o retirada con el signo y etiqueta correspondientes. No añadir Q(100 hPa) como una segunda emisión volumétrica por el hecho de usarlo para calcular la frontera.

**Cambio de coherencia respecto a v9.5:** el control TOP fijo se calcula con el mismo Q_fija del compañero de producción fija, dividido por λ₇. La climatología anual se conserva como protocolo para LATERAL; su implementación concreta debe verificarse. Concentración fija no implica intercambio constante. Los contrastes interanuales a fechas equivalentes conservan la estacionalidad lateral.

En escenarios coherentes de producción, un cambio de Q que afecte a 100 hPa se propaga a la concentración TOP. Los contrastes que cambian solo TOP evalúan la aproximación de frontera. Usar los campos etiquetados tras verificar linealidad; no añadir nuevas configuraciones o modificar el transporte. Una sensibilidad de amplitud mide dependencia dentro de los contrastes ensayados y no demuestra por sí sola que se represente todo el reservorio estratosférico.

La conversión para comparar con actividad en aire es **A = λ₇ × ρ_aire × n**, en Bq m⁻³, usando densidad coherente con la base de masa del trazador; multiplicar por 1000 para mBq m⁻³. No convertir n directamente en actividad sin decaimiento y densidad. Documentar fórmula, unidades, frecuencia de actualización y archivos de frontera junto al código de producción.

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

La comunicación aportada por el investigador describe una posible recuperación de registros digitales antiguos hasta 1996 y registros en papel de 1980–1996 para **Offenbach, Hamburg, München y Berlin**. La disponibilidad adicional de esas hojas y documentos sigue pendiente de recepción e inventario; no se han auditado nuevos archivos DWD en v9.6. Al incorporarlos, cotejarlos con los registros ya existentes para evitar contar solapamientos como nuevas estaciones o nuevos años.

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
