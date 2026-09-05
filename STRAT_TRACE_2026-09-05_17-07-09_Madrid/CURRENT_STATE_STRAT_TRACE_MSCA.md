# CURRENT_STATE — STRAT-TRACE / MSCA

Versión actual: propuesta v5 con evidencia de resolución, 5 de septiembre de 2026, carpeta 16:18:38 Europe/Madrid.

## Configuraciones actualmente válidas

- **Experimento controlado:** condición de contorno superior constante, preferentemente `C_top = 1`, sin emisiones en capas inferiores. En DEHM, el techo está aproximadamente en `100 hPa`; por ello, el diagnóstico representa transporte desde el límite superior del modelo hacia la troposfera, no el flujo físico completo a través de la tropopausa.
- **`STRAT_PASSIVE`:** misma condición superior; transporte resuelto, convección y mezcla, sin deposición húmeda ni seca. Incluir la misma pérdida de primer orden que en `STRAT_AEROSOL`; el tiempo de vida común se fijará mediante piloto y sensibilidades para evitar acumulación indefinida.
- **`STRAT_AEROSOL`:** misma condición superior, transporte y pérdida de primer orden que `STRAT_PASSIVE`, con deposición húmeda y seca adicional. El contraste entre ambos diagnostica la eliminación por deposición.
- **Modelos principales:** DEHM y GEOS-Chem como dos sistemas independientes; la concordancia entre ambos define robustez y la divergencia cuantifica incertidumbre estructural.
- **Meteorologías:** DEHM con WRF/ERA5 y GEOS-Chem con MERRA-2 como configuraciones de referencia. `MERRA-2 → WRF → DEHM` es el experimento de atribución más realista. `ERA5 → GEOS-Chem` queda solo como opción, pendiente de viabilidad técnica.
- **Diagnóstico Lagrangiano:** HYSPLIT será el diagnóstico meteorológico independiente de los esquemas internos de transporte del CTM para episodios seleccionados. Se usarán ensembles de trayectorias y, donde sea viable, partículas; una trayectoria individual no será evidencia cuantitativa.
- **Emparejamiento meteorológico:** comparar `DEHM/WRF-ERA5 ↔ HYSPLIT/WRF-ERA5` y `GEOS-Chem/MERRA-2 ↔ HYSPLIT/MERRA-2`, condicionado a un piloto de conversión de entradas y coordenadas verticales. Comparar además `HYSPLIT/ERA5 ↔ HYSPLIT/MERRA-2` para sensibilidad al reanálisis con algoritmo Lagrangiano fijo.
- **Límite interpretativo:** HYSPLIT es independiente de la advección numérica, convección, difusión/mezcla y PBL del CTM, pero no es independiente de la meteorología que lo fuerza; no es verdad absoluta ni equivalente directo de `TT(z)`.
- **Restricción observacional:** usar ⁷Be observado y simulado para comprobar si las señales del experimento idealizado tienen manifestación real; no usar su producción variable como fuente del experimento controlado.

## Unidades

- Trazador principal: adimensional y normalizado, `C* = C/C_top`, con `C_top = 1`.
- Niveles diagnósticos: `hPa`; prioritarios `500`, `700`, `850 hPa` y superficie/PBL.
- Penetración superficial: `P_surface = C_PASSIVE,surface / C_source` (adimensional).
- Supervivencia superficial: `S_surface = C_AEROSOL,surface / C_PASSIVE,surface` (adimensional).
- Depósito acumulado dividido por aporte acumulado, con unidades y dominio compatibles: adimensional. Flujo de deposición dividido por carga: tasa de eliminación (tiempo⁻¹), no fracción. Definir explícitamente el denominador y la integración temporal.
- Eventos: frecuencia en `eventos año⁻¹`; duración en horas o días; profundidad en `hPa`; tiempo de vida y retrotrayectorias en días.
- Timing Lagrangiano por evento: horas o días entre segmentos emparejados; reportar mediana, rango intercuartílico y dispersión del ensemble.

- Respuesta preliminar de resolución: `100 × (media_fina/media_gruesa − 1)` (%), calculada por ubicación antes de obtener medianas espaciales. No es un tiempo ni un flujo vertical.
- `qtotal`: agua por capa empleada para diagnosticar dónde se forma precipitación. La figura usa medias sin ponderación entre las capas indicadas; no calcula la ponderación efectiva de formación de lluvia ni un balance de carga de ⁷Be.

## Periodos

- Objetivo multidecadal: al menos `30–40 años`.
- Ventana preferente común: `1980–2025`, condicionada por la disponibilidad de MERRA-2 desde 1980.
- Alternativa más corta si lo exige la disponibilidad homogénea: `1990–2025`.
- Retrotrayectorias/partículas HYSPLIT: aproximadamente `5–10 días`, únicamente para episodios seleccionados de alto `SPI` y casos contrastantes; no para cada hora de toda la simulación.
- Marco MSCA previsto: proyecto ejecutable en `24 meses`.

- Evidencia preliminar de ⁷Be: DEHM JJA 2009–2024, 79 ubicaciones; GEOS-Chem JJA 2015–2016, 76 ubicaciones para concentración/perfiles y 32 para deposición. Son muestras y periodos propios de cada modelo.
- La prueba de atribución por resolución empezará con 2015–2016, periodo común a ambos archivos, y soporte espacial armonizado.

## Rutas importantes

- `ERA5 → WRF → DEHM` — configuración DEHM de referencia.
- `MERRA-2 → GEOS-Chem` — configuración GEOS-Chem de referencia.
- `MERRA-2 → WRF → DEHM` frente a `MERRA-2 → GEOS-Chem` — comparación con el mismo reanálisis de gran escala, aunque no con meteorología idéntica.
- `WRF/ERA5 → DEHM` frente a `WRF/ERA5 → HYSPLIT` — contraste entre respuesta completa del CTM y pathway/timing permitido por la meteorología emparejada.
- `MERRA-2 → GEOS-Chem` frente a `MERRA-2 → HYSPLIT` — contraste equivalente para el sistema global, pendiente del piloto técnico de entrada HYSPLIT.
- `ERA5/MERRA-2 → HYSPLIT` — sensibilidad al reanálisis manteniendo fijo el algoritmo Lagrangiano.
- Segmentos de timing: `source/lower stratosphere → UTLS/tropopause`, `UTLS → 500 hPa`, `500 → 850 hPa`, `850 hPa → PBL/surface`.
- `fuente estratosférica constante → transporte descendente → concentración superficial → supervivencia → deposición húmeda/seca` — cadena causal principal.
- Propuesta actual: `C:\Users\Master\.codex\.chatgpt-projects\g-p-6a9950a5749481919e3702e75efe5c65\STRAT_TRACE_proposal_2026-09-05_16-18-38\STRAT_TRACE_MSCA_PROPOSAL_v5_resolution_evidence.docx`.
- Figura integrada: `C:\Users\Master\.codex\.chatgpt-projects\g-p-6a9950a5749481919e3702e75efe5c65\STRAT_TRACE_proposal_2026-09-05_16-18-38\STRAT_TRACE_preliminary_resolution_evidence.png`.
- Figura y resúmenes de procedencia: `C:\Users\Master\.codex\.chatgpt-projects\g-p-6a9950a5749481919e3702e75efe5c65\STRAT_TRACE_mechanism_figures_2026-09-05_15-17-12`.
- Fuente vertical GEOS-Chem: `G:\Mi unidad\D E N M A R K\Paper 7Be DEHM\comparacion de resoluciones GEOS\GEOS_VERTICAL_PROFILES_ORIGINAL_ALL_CONFIGS_INCLUDING_MINDS_201501_to_201706.csv`.
- Comparación GEOS-Chem usada: `GEOS_FREJA_2x25_LP67` frente a `GEOS_FREJA_4x5`; latitud > 40°N.
- Cachés DEHM: `G:\Mi unidad\D E N M A R K\Paper 7Be DEHM\cache_monthly_7Be_qtotal_precip`.

## Resultados ya demostrados

- **El experimento idealizado multidecadal STRAT-TRACE aún no se ha ejecutado.** La evidencia nueva procede del trabajo en curso del solicitante con ⁷Be y constituye motivación y viabilidad, no resultados del experimento propuesto.
- DEHM (JJA, 25 frente a 75 km): medianas de respuesta de superficie +5,9%, deposición total +13,6%, precipitación −45,9%, qtotal capas 16–22 −19,2% y capas 23–27 −12,7%; 79 ubicaciones en todos esos diagnósticos.
- GEOS-Chem (JJA, 2° × 2,5° frente a 4° × 5°): concentración superficial +26,4% en 76 ubicaciones y deposición total +0,5% en 32; la mediana de deposición está cerca de cero.
- Los perfiles muestran enriquecimiento inferior y estructura vertical en la respuesta a la resolución. Demuestran sensibilidad de concentraciones; no miden directamente transporte vertical, rapidez ni sesgo frente a observaciones. Las ubicaciones no equivalen a celdas independientes.
- La literatura demuestra que los trazadores estratosféricos idealizados con fuente fija son una herramienta establecida para aislar cambios de transporte; por tanto, el trazador es el método, no la novedad.
- Mantener la fuente idéntica permite atribuir los cambios simulados a la meteorología y a la formulación del modelo, no a cambios en la producción del trazador.
- Los modelos pueden producir diferencias importantes de transporte incluso con forzamiento meteorológico comparable; ERA5 y MERRA-2 también difieren en UTLS/STE. La robustez entre modelos y reanálisis debe ser parte del resultado, no una suposición.
- Las intrusiones profundas pueden producir señal superficial, pero alcanzar la baja troposfera no garantiza alcanzar la superficie: la mezcla en la PBL y la eliminación son determinantes.
- La deposición de ⁷Be depende no solo de la precipitación acumulada, sino también de su frecuencia, intensidad, duración y del scavenging convectivo.
- La combinación `PASSIVE + AEROSOL` permite distinguir, de forma diagnóstica, mayor transporte descendente de mayor supervivencia o menor eliminación.
- La literatura metodológica demuestra que HYSPLIT puede calcular trayectorias/dispersiones y ensembles meteorológicos, que la velocidad vertical normalmente procede del campo meteorológico de entrada y que las trayectorias son sensibles a la resolución, interpolación, movimiento vertical y meteorología elegida.
- La literatura también demuestra que una trayectoria individual no representa el volumen finito, la mezcla, la turbulencia o la convección experimentados por un trazador; por ello, el diseño requiere ensembles/partículas y una jerarquía explícita de incertidumbre.

- Abalos et al. (2026) documenta un sesgo de edad del aire en los CCM evaluados. La edad integra advección y mezcla. Ese diagnóstico no atribuye automáticamente el sesgo a DEHM ni a GEOS-Chem.

## Hipótesis abiertas

- La capacidad atmosférica para transportar una entrada estratosférica idéntica hasta la baja troposfera y la superficie ha cambiado entre 1980 y 2025.
- La sensibilidad a la resolución podría incluir tiempos de descenso demasiado cortos en DEHM o GEOS-Chem. Debe probarse con `STRAT_PASSIVE`, `TT(z)`, flujos/tendencias y referencias de episodios; una malla gruesa no representa la verdad atmosférica.
- Menor scavenging, cambios de suministro lateral, meteorología resuelta y representatividad de celdas también pueden contribuir al enriquecimiento; queda por cuantificar su importancia.
- Se priorizarán periodo/dominio común, agregación conservativa y coordenadas verticales emparejadas; un enriquecimiento del pasivo acompañado de menor tiempo apoyaría una contribución del transporte, mientras que un cambio restringido a aerosol/SSI favorecería la eliminación.
- La frecuencia, intensidad, duración, estacionalidad y profundidad de las intrusiones estratosféricas presentan cambios multidecadales detectables.
- La eficiencia de deposición húmeda/seca y la supervivencia durante el descenso han cambiado aun con una fuente constante.
- Parte de las tendencias será robusta entre DEHM y GEOS-Chem y entre ERA5 y MERRA-2; otra parte será dependiente del modelo o reanálisis.
- Las diferencias entre `C_PASSIVE,surface` y `C_AEROSOL,surface` permitirán separar transporte de eliminación con suficiente claridad.
- Las señales idealizadas serán coherentes con episodios o patrones observados de ⁷Be.
- Para episodios meteorológicamente controlados, el timing segmentado del CTM será consistente, dentro de la dispersión, con HYSPLIT forzado por la meteorología emparejada.
- Una divergencia `CTM ↔ HYSPLIT` puede localizar sensibilidad a procesos o numerics del CTM, pero no identifica por sí sola una causa; una divergencia `HYSPLIT/ERA5 ↔ HYSPLIT/MERRA-2` indicará dependencia meteorológica/reanálisis.
- Quedan por fijar: tiempo de vida del `PASSIVE`, definición operativa de intrusión profunda, tratamiento del desplazamiento de la tropopausa, balance de masa y viabilidad/coste de las configuraciones cruzadas.
- Quedan por fijar para HYSPLIT: disponibilidad/conversión de WRF-ERA5 y MERRA-2, coordenada vertical común, número de miembros, ventanas iniciales, criterio de emparejamiento de eventos y definición exacta del tiempo entre segmentos.

## Análisis descartados

- Presentar el proyecto como un estudio directo del “efecto del cambio climático sobre STE”. Primero se estudiarán cambios y variabilidad multidecadales; la atribución climática será posterior y condicionada a la robustez.
- Analizar solo cómo cambió la meteorología; el objetivo es medir la respuesta atmosférica a una entrada estratosférica idéntica.
- Usar únicamente ⁷Be real o una producción cosmogénica variable como trazador principal.
- Introducir fuentes artificiales en capas troposféricas inferiores.
- Usar un único trazador y confundir concentración superficial con deposición/removal.
- Prometer una separación perfecta entre meteorología y estructura del modelo o un diseño cruzado `2 × 2` completo antes de confirmar `GEOS-Chem + ERA5`.
- Calcular retrotrayectorias para cada hora de 30–40 años, usar trayectorias individuales largas de `15–20 días` o basar STE únicamente en `C > P95` sin criterios dinámicos adicionales.
- Presentar HYSPLIT como observación, verdad meteorológica o validación directa de `TT(z)`; comparar un tiempo de trayectoria puntual con una media/edad Euleriana como si fueran la misma magnitud.
- Vender el trazador idealizado como la principal novedad científica.
- Presentar el sesgo de edad de los CCM como demostrado en DEHM/GEOS-Chem, equiparar GEOSCCM con GEOS-Chem o concluir rapidez excesiva solo a partir de concentraciones/deposición.
- Afirmar que la deposición aumenta de forma clara en ambos modelos a partir de esta figura, o comparar sus porcentajes como si periodos y soporte espacial fueran idénticos.

## Siguiente pregunta científica

**¿Ha cambiado la entrega y eliminación superficial de una señal estratosférica idéntica entre 1980 y 2025; la sensibilidad de DEHM y GEOS-Chem a la resolución refleja un descenso excesivamente rápido o cambios de supervivencia; y en qué segmento sitúan la discrepancia los trazadores, las observaciones y los ensembles HYSPLIT meteorológicamente emparejados?**
