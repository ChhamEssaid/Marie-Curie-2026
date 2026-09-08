# Cobertura observacional comprobada — STRAT-TRACE v9.11

Comprobación del 8 de septiembre de 2026, conservada sin nuevos recuentos en v9.11. Se ha leído el CSV original sin modificarlo. La v9.10 conserva la formulación robusta «más de 54.000 registros de 83 series» para 2009–2024. Los originales permanecen sin modificar.

## Fuente y criterio

Fuente: C:/Users/Master/Downloads/Be7_en_aire_all_stations_1.csv.
SHA-256: a2a9df8aad0a0e6c519b028b2702023756a7aebe320f147a4d1e5d1f21b36030.

El año corresponde al punto medio UTC del intervalo. El filtro básico exige concentración numérica no negativa, intervalo de duración positiva y unidad explícita equivalente a Bq/m³. No se corrigen datos ni se infieren unidades. Las series se cuentan por LOC_NAME, todavía sin armonizar todos los alias y traslados. Los recuentos representan disponibilidad, no un panel metrológicamente validado.

## Resultados verificados

| Alcance | Registros | Series identificadas por nombre |
| --- | ---: | ---: |
| Archivo completo, bruto | 72.943 | 91 |
| 1986–2024, filtro básico | 66.150 | 85 |
| 1986–2005, filtro básico | 8.736 | 21 |
| 2009–2024, filtro básico | 54.246 | 83 |
| 1986, filtro básico | 159 | 4 |

En 2009–2024, el número anual de series con registros pasa por valores entre 48 y 77. Hay 29 series con algún registro en cada uno de esos 16 años; esto no significa cobertura completa de cada año.

Las cuatro series de 1986 son Berlin (12 registros), Braunschweig (12), Risoe (55) y Wien_Hohe_Warte (80). Berlin, Braunschweig y Risoe tienen algún registro cada año de 1986–2005. Ninguna etiqueta tiene registros en todos los años de 1986–2024; no se ha demostrado validación homogénea de tres ciclos solares.

Una comprobación conservadora adicional excluye todas las filas con claves normalizadas nombre/inicio/fin repetidas, así como los intervalos superiores a 366 días. Conserva 54.124 registros y 83 series en 2009–2024; 65.992 registros y 85 series en 1986–2024. Por ello, «más de 54.000 registros de 83 series» es una formulación robusta para el periodo reciente.

## Aclaración del recuento de 87 series de aire

En 2009–2024 se obtienen **87** etiquetas LOC_NAME con valor numérico no negativo e intervalo positivo antes de exigir unidad. Al exigir unidad explícita equivalente a Bq/m³ quedan **83**. Las cuatro etiquetas adicionales son Cattenom, Civaux, Saint_Aignan_Grandlieu y Tomblaine: se conserva su disponibilidad nominal, pendiente de recuperar la unidad; no se inventa ni se asigna automáticamente. La diferencia no significa cuatro estaciones eliminadas del archivo fuente.

## Disponibilidad conjunta de aire y deposición: 43 series corroboradas

El investigador confirma 43 estaciones europeas con ambas variables. La revisión de archivos locales respalda ese alcance:

| Fuente de deposición | Evidencia comprobada | Cruce con el archivo de aire |
| --- | --- | --- |
| deposicion_all_stations.csv | 7.923 filas, 42 nombres; 7.431 registros con punto medio en 2009–2024 | Los 42 nombres tienen aire con unidad explícita en ese periodo. |
| Original DWD 2009-2026_Be-7_Prec_corr2.xlsx, hoja Precipitation data | Brocken: 43 registros numéricos no negativos con intervalo positivo, enero de 2009–enero de 2019 | Brocken tiene 721 registros de aire con unidad explícita desde 2011 en el archivo completo. |

Los 42 nombres del CSV se enlazan corrigiendo únicamente mayúsculas y espacios exteriores: 40 coinciden literalmente; Bad_lippspringe/Bad_Lippspringe y Stuttgart con/sin espacio final completan el cruce. Brocken no está en ese CSV de deposición y constituye la serie adicional. Para Brocken hay años con registros de ambas variables en 2011, 2012, 2013, 2017 y 2018.

Esto corrobora **al menos 43 series con ambas variables disponibles en la colección europea**, sin resolver todavía todas las identidades, traslados ni ventanas emparejadas. No son 43 estaciones continuas durante los 16 años ni 7.431 pares comparables. El criterio anual por punto medio puede asignar a 2024 una muestra cuyo extremo final entra en 2025. WP1 conservará las fechas reales y fijará el subconjunto de evaluación conjunta.

No se ha reconstruido flujo ni combinado fracciones de colector. Los originales DWD conservan métodos, incertidumbres y límites de detección que deben acompañar las comparaciones. La deposición disponible sostiene ya el diseño conjunto; la preparación y homogeneización constituyen el trabajo previsto.

Hashes de los archivos adicionales, leídos sin modificación:

- deposicion_all_stations.csv: `d71e58bdcdfd211276d23b7fd9e42db376f017a0e082aee80396d0a371c70090`.
- 2009-2026_Be-7_Prec_corr2.xlsx: `e08326eb056f71af501af9e57dee036149680fc4bfc89fa4d3670f2fb76e2762`.

## Extensión CTBTO y alcance de los recuentos

Según el investigador, los registros CTBTO previstos son diarios, de alrededor de 80 sitios distribuidos mundialmente y principalmente desde 2000. Estima aproximadamente 30 sitios comunes al archivo europeo. El acuerdo está firmado y la entrega está pendiente; ni las estaciones ni los solapamientos han podido comprobarse en archivos recibidos.

La unión aproximada 87 + 80 − 30 ≈ 137 depende de esas estimaciones y de la definición de estación. No equivale a 137 estaciones ya disponibles, dentro de DEHM, simultáneas o con deposición. Part B1 conserva 83 series de aire con cribado inicial y 43 de la base conjunta europea, y describe CTBTO como extensión diaria esperada sin sumar redes.

La [descripción pública de CTBTO](https://www.ctbto.org/our-work/monitoring-technologies/radionuclide-monitoring) sitúa la red nominal de radionúclidos en 80 estaciones. El alcance útil del archivo contratado se verificará en su propia entrega. La firma y la resolución prevista del acuerdo particular proceden de la confirmación del investigador, no de ese catálogo general.

## Incorporación a v9.10

Las secciones 1.1 y 1.2 presentan las 43 estaciones con ambas variables, el archivo europeo principalmente obtenido por JRC, la aportación DWD y la extensión CTBTO diaria. WP1 establece los intervalos comparables y los segmentos estables. El recuento de 79 ubicaciones de la comparación preliminar de resolución sigue siendo una población distinta. Ningún original observacional se publica en este paquete.
