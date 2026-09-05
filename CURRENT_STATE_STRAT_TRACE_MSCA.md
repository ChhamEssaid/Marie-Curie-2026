# CURRENT_STATE — STRAT-TRACE / MSCA

## Configuraciones actualmente válidas

- **Experimento controlado:** condición de contorno superior constante, preferentemente `C_top = 1`, sin emisiones en capas inferiores. En DEHM, el techo está aproximadamente en `100 hPa`; por ello, el diagnóstico representa transporte desde el límite superior del modelo hacia la troposfera, no el flujo físico completo a través de la tropopausa.
- **`STRAT_PASSIVE`:** misma condición superior; sin química, deposición húmeda ni deposición seca. Diagnostica principalmente transporte. Debe incluirse una sensibilidad al tiempo de vida para evitar acumulación indefinida; el valor todavía no está fijado.
- **`STRAT_AEROSOL`:** misma condición superior; con deposición húmeda y seca. Diagnostica transporte + eliminación.
- **Modelos principales:** DEHM y GEOS-Chem como dos sistemas independientes; la concordancia entre ambos define robustez y la divergencia cuantifica incertidumbre estructural.
- **Meteorologías:** DEHM con WRF/ERA5 y GEOS-Chem con MERRA-2 como configuraciones de referencia. `MERRA-2 → WRF → DEHM` es el experimento de atribución más realista. `ERA5 → GEOS-Chem` queda solo como opción, pendiente de viabilidad técnica.
- **Diagnóstico Lagrangiano:** aplicar el mismo método a ERA5 y MERRA-2, preferentemente FLEXPART o LAGRANTO; HYSPLIT puede apoyar análisis de eventos con ensembles, pero no una cuantificación basada en una trayectoria individual.
- **Restricción observacional:** usar ⁷Be observado y simulado para comprobar si las señales del experimento idealizado tienen manifestación real; no usar su producción variable como fuente del experimento controlado.

## Unidades

- Trazador principal: adimensional y normalizado, `C* = C/C_top`, con `C_top = 1`.
- Niveles diagnósticos: `hPa`; prioritarios `500`, `700`, `850 hPa` y superficie/PBL.
- Penetración superficial: `P_surface = C_PASSIVE,surface / C_source` (adimensional).
- Supervivencia superficial: `S_surface = C_AEROSOL,surface / C_PASSIVE,surface` (adimensional).
- Eficiencia de eliminación: `E_removal = (D_wet + D_dry) / fuente o carga atmosférica` (fracción o porcentaje).
- Eventos: frecuencia en `eventos año⁻¹`; duración en horas o días; profundidad en `hPa`; tiempo de vida y retrotrayectorias en días.

## Periodos

- Objetivo multidecadal: al menos `30–40 años`.
- Ventana preferente común: `1980–2025`, condicionada por la disponibilidad de MERRA-2 desde 1980.
- Alternativa más corta si lo exige la disponibilidad homogénea: `1990–2025`.
- Retrotrayectorias: aproximadamente `5–10 días`, únicamente para episodios seleccionados; no para cada hora de toda la simulación.
- Marco MSCA previsto: proyecto ejecutable en `24 meses`.

## Rutas importantes

- `ERA5 → WRF → DEHM` — configuración DEHM de referencia.
- `MERRA-2 → GEOS-Chem` — configuración GEOS-Chem de referencia.
- `MERRA-2 → WRF → DEHM` frente a `MERRA-2 → GEOS-Chem` — comparación con el mismo reanálisis de gran escala, aunque no con meteorología idéntica.
- `ERA5/MERRA-2 → mismo modelo Lagrangiano` — diagnóstico de la contribución meteorológica a las diferencias de transporte.
- `fuente estratosférica constante → transporte descendente → concentración superficial → supervivencia → deposición húmeda/seca` — cadena causal principal.
- Los archivos preparados en la conversación anterior aparecen solo como referencias internas sin rutas locales recuperables; sus nombres/rutas deben reconstruirse al iniciar el proyecto.

## Resultados ya demostrados

- **Todavía no existen resultados propios de STRAT-TRACE:** no se ha ejecutado el experimento multidecadal.
- La literatura demuestra que los trazadores estratosféricos idealizados con fuente fija son una herramienta establecida para aislar cambios de transporte; por tanto, el trazador es el método, no la novedad.
- Mantener la fuente idéntica permite atribuir los cambios simulados a la meteorología y a la formulación del modelo, no a cambios en la producción del trazador.
- Los modelos pueden producir diferencias importantes de transporte incluso con forzamiento meteorológico comparable; ERA5 y MERRA-2 también difieren en UTLS/STE. La robustez entre modelos y reanálisis debe ser parte del resultado, no una suposición.
- Las intrusiones profundas pueden producir señal superficial, pero alcanzar la baja troposfera no garantiza alcanzar la superficie: la mezcla en la PBL y la eliminación son determinantes.
- La deposición de ⁷Be depende no solo de la precipitación acumulada, sino también de su frecuencia, intensidad, duración y del scavenging convectivo.
- La combinación `PASSIVE + AEROSOL` permite distinguir, de forma diagnóstica, mayor transporte descendente de mayor supervivencia o menor eliminación.

## Hipótesis abiertas

- La capacidad atmosférica para transportar una entrada estratosférica idéntica hasta la baja troposfera y la superficie ha cambiado entre 1980 y 2025.
- La frecuencia, intensidad, duración, estacionalidad y profundidad de las intrusiones estratosféricas presentan cambios multidecadales detectables.
- La eficiencia de deposición húmeda/seca y la supervivencia durante el descenso han cambiado aun con una fuente constante.
- Parte de las tendencias será robusta entre DEHM y GEOS-Chem y entre ERA5 y MERRA-2; otra parte será dependiente del modelo o reanálisis.
- Las diferencias entre `C_PASSIVE,surface` y `C_AEROSOL,surface` permitirán separar transporte de eliminación con suficiente claridad.
- Las señales idealizadas serán coherentes con episodios o patrones observados de ⁷Be.
- Quedan por fijar: tiempo de vida del `PASSIVE`, definición operativa de intrusión profunda, tratamiento del desplazamiento de la tropopausa, balance de masa y viabilidad/coste de las configuraciones cruzadas.

## Análisis descartados

- Presentar el proyecto como un estudio directo del “efecto del cambio climático sobre STE”. Primero se estudiarán cambios y variabilidad multidecadales; la atribución climática será posterior y condicionada a la robustez.
- Analizar solo cómo cambió la meteorología; el objetivo es medir la respuesta atmosférica a una entrada estratosférica idéntica.
- Usar únicamente ⁷Be real o una producción cosmogénica variable como trazador principal.
- Introducir fuentes artificiales en capas troposféricas inferiores.
- Usar un único trazador y confundir concentración superficial con deposición/removal.
- Prometer una separación perfecta entre meteorología y estructura del modelo o un diseño cruzado `2 × 2` completo antes de confirmar `GEOS-Chem + ERA5`.
- Calcular retrotrayectorias para cada hora de 30–40 años, usar trayectorias individuales largas de `15–20 días` o basar STE únicamente en `C > P95` sin criterios dinámicos adicionales.
- Vender el trazador idealizado como la principal novedad científica.

## Siguiente pregunta científica

**¿Ha cambiado entre 1980 y 2025 la capacidad de la atmósfera para transportar una cantidad idéntica de material estratosférico hasta la superficie y eliminarla mediante deposición, y qué parte de esos cambios es robusta entre DEHM y GEOS-Chem y entre ERA5 y MERRA-2?**

