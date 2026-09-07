# Auditoría de cobertura de ⁷Be en aire — 7 de septiembre de 2026

## Alcance y fuente

Inventario del CSV suministrado por el investigador. El inventario se realizó sin modificar el CSV original y se conserva aquí como respaldo de la revisión v9.5. Este inventario verifica presencia de registros; no constituye una validación metrológica completa ni confirma pares aire–deposición.

- Fuente: `C:\Users\Master\Downloads\Be7_en_aire_all_stations_1.csv`.
- SHA-256: `a2a9df8aad0a0e6c519b028b2702023756a7aebe320f147a4d1e5d1f21b36030`.
- 72,943 filas; 91 etiquetas LOC_NAME; 95 nombres originales.
- Todas las filas identifican BE-7. Extremos del archivo: inicio 1983-11-30T23:00:00+00:00 y fin 2026-03-09T09:00:00+00:00.
- Las 106 combinaciones exactas nombre/coordenadas no equivalen a ese número de estaciones físicas: pueden reflejar redondeos, reubicaciones o errores de metadatos.

## Criterio de recuento

Cada registro se asigna al año del punto medio de su intervalo de muestreo. Se muestran por separado: presencia bruta; concentración numérica con intervalo positivo; y ese mismo criterio más unidad explícita de concentración de actividad por volumen. Ningún criterio implica año completo, representatividad espacial ni emplazamiento homogéneo. No se impuso un umbral de completitud anual ni se corrigieron fechas o coordenadas. Los intervalos muy largos se señalan para revisión.

Las fechas ISO se interpretan como ISO, y las fechas con barras como día/mes/año. Mezclar ambas con una inferencia global día/mes puede intercambiar componentes de las fechas ISO. Se han conservado las fechas UTC; algunas muestras de enero comienzan a las 23:00 UTC del 31 de diciembre anterior.

## Resultado de 1986

**Hay cuatro series identificadas por nombre en 1986, no una sola.** Todas tienen valores numéricos, intervalos positivos y unidad declarada Bq/m³.

| Etiqueta del CSV | Registros centrados en 1986 | Meses con punto medio | Primer inicio UTC | Último fin UTC |
| --- | --- | --- | --- | --- |
| Berlin | 12 | 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12 | 1985-12-31 | 1986-12-31 |
| Braunschweig | 12 | 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12 | 1985-12-31 | 1986-12-31 |
| Risoe | 55 | 4, 5, 6, 7, 8, 9, 10, 11, 12 | 1986-04-07 | 1986-12-10 |
| Wien_Hohe_Warte | 80 | 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12 | 1985-12-30 | 1986-12-29 |

Los meses enumerados indican presencia, no cobertura completa. Risoe comienza en abril; Wien_Hohe_Warte contiene discontinuidades dentro del año. Berlin y Braunschweig contienen doce intervalos mensuales de 1986. Contar únicamente el año inicial añadiría Helsinki, Bilthoven y Oberschleibheim por muestras iniciadas al final de diciembre de 1986 y centradas en enero de 1987; por eso no se presentan como otras tres series de 1986.

Berlin, Braunschweig y Risoe tienen algún registro con intervalo positivo en cada año de 1986–2005. Berlin cambia de coordenadas en el archivo, por lo que no se presenta como emplazamiento invariable. El nombre Risoe aparece con otras coordenadas en 2021 y vuelve a las anteriores en 2022: se debe verificar si es corrección, cambio de ubicación o error.

## Evolución anual del inventario

| Año del punto medio | Etiquetas brutas | Valor e intervalo positivo | Además, unidad explícita |
| --- | --- | --- | --- |
| 1986 | 4 | 4 | 4 |
| 1987 | 8 | 8 | 8 |
| 1988 | 9 | 9 | 9 |
| 1989 | 10 | 10 | 10 |
| 1990 | 9 | 9 | 9 |
| 1991 | 10 | 10 | 10 |
| 1992 | 9 | 9 | 9 |
| 1993 | 10 | 10 | 10 |
| 1994 | 9 | 9 | 9 |
| 1995 | 9 | 9 | 9 |
| 1996 | 8 | 8 | 8 |
| 1997 | 8 | 8 | 8 |
| 1998 | 7 | 7 | 7 |
| 1999 | 8 | 8 | 8 |
| 2000 | 11 | 11 | 11 |
| 2001 | 13 | 13 | 13 |
| 2002 | 16 | 15 | 15 |
| 2003 | 16 | 16 | 16 |
| 2004 | 15 | 14 | 14 |
| 2005 | 17 | 16 | 16 |
| 2006 | 22 | 20 | 20 |
| 2007 | 22 | 21 | 21 |
| 2008 | 24 | 23 | 23 |
| 2009 | 53 | 51 | 49 |
| 2010 | 52 | 50 | 48 |
| 2011 | 73 | 71 | 69 |
| 2012 | 80 | 78 | 75 |
| 2013 | 81 | 79 | 75 |
| 2014 | 82 | 81 | 77 |
| 2015 | 81 | 81 | 77 |
| 2016 | 78 | 78 | 74 |
| 2017 | 78 | 78 | 74 |
| 2018 | 80 | 80 | 76 |
| 2019 | 76 | 75 | 71 |
| 2020 | 75 | 74 | 70 |
| 2021 | 76 | 75 | 71 |
| 2022 | 74 | 74 | 70 |
| 2023 | 65 | 65 | 61 |
| 2024 | 64 | 64 | 60 |
| 2025 | 54 | 54 | 50 |

Las dos etiquetas que explican la diferencia 51→49 en 2009 son Cattenom y Civaux, cuyas unidades están vacías. No se infirieron unidades a partir de otras estaciones.

## Series representadas durante 1986–2005

Son 21 etiquetas distintas a lo largo de todo el periodo; no son 21 estaciones simultáneas ni continuas. Los extremos siguientes corresponden al año del punto medio, dentro del periodo auditado 1986–2005.

| Etiqueta | Registros | Primer año | Último año | Años representados | Años interiores ausentes |
| --- | --- | --- | --- | --- | --- |
| Alencon | 96 | 1995 | 2003 | 8 | 2002 |
| Barcelona | 263 | 2000 | 2005 | 6 | Ninguno entre esos extremos |
| Berlin | 239 | 1986 | 2005 | 20 | Ninguno entre esos extremos |
| Bilbao | 286 | 2000 | 2005 | 6 | Ninguno entre esos extremos |
| Bilthoven | 734 | 1987 | 2005 | 18 | 1992 |
| Braunschweig | 240 | 1986 | 2005 | 20 | Ninguno entre esos extremos |
| Freiburg | 885 | 1989 | 2005 | 17 | Ninguno entre esos extremos |
| Harku | 202 | 2002 | 2005 | 4 | Ninguno entre esos extremos |
| Helsinki | 2439 | 1987 | 2005 | 18 | 1992 |
| IVALO-ROVANIEMI | 424 | 1987 | 1995 | 9 | Ninguno entre esos extremos |
| Ivalo | 52 | 1999 | 1999 | 1 | Ninguno entre esos extremos |
| Madrid | 289 | 2000 | 2005 | 6 | Ninguno entre esos extremos |
| Malaga | 1 | 2005 | 2005 | 1 | Ninguno entre esos extremos |
| Milano | 186 | 1988 | 2005 | 9 | 1991, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2004 |
| Oberschleibheim | 36 | 1987 | 1989 | 3 | Ninguno entre esos extremos |
| Offenbach | 295 | 1991 | 2005 | 7 | 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000 |
| Risoe | 1089 | 1986 | 2005 | 20 | Ninguno entre esos extremos |
| Sacavem | 89 | 1991 | 2005 | 8 | 1994, 1995, 1996, 1997, 1998, 1999, 2000 |
| Sevilla | 263 | 2000 | 2005 | 6 | Ninguno entre esos extremos |
| Utena_SW | 47 | 2002 | 2005 | 4 | Ninguno entre esos extremos |
| Wien_Hohe_Warte | 581 | 1986 | 1997 | 12 | Ninguno entre esos extremos |

## Incidencias que deben resolverse en la preparación científica

- 699 intervalos de duración cero y 1 negativo. El negativo es Orsay: inicio 02/09/2025 y fin 09/01/2009. No se han reparado automáticamente.
- 8 valores de actividad ausentes; ninguna concentración numérica negativa o cero.
- 2915 unidades ausentes: Cattenom, Civaux, Saint_Aignan_Grandlieu y Tomblaine. Ninguna unidad ausente corresponde a registros anteriores a 2006.
- 1 duplicado exacto; 85 filas adicionales con la misma clave nombre/inicio/fin. No se eliminaron automáticamente: valores diferentes podrían exigir revisar procedencia o revisiones del registro.
- Tres intervalos superan 366 días: Bilbao (374), Granada (393), Romagnat (441). Revisar fechas con la fuente antes de utilizarlos en comparación con el modelo.
- Berlin contiene coordenadas 52.42667, 13.13333 durante 1985–1990, frente a 52.533333, 13.41666… en otros periodos. Ese cambio no debe interpretarse sin documentación histórica.
- Ivalo, en 1999, tiene exactamente las coordenadas 60.21, 25.06 también presentes en Helsinki. Verificar identidad y localización antes de asignar celdas del modelo.
- Unidades, incertidumbre, límites de detección, método, duplicados y representatividad requieren controles adicionales antes de determinar el panel de evaluación.

## Consecuencia para la propuesta

Sustituir «one station since 1986» y «early single-site evidence» por una descripción de varias series históricas y segmentos de estación comprobados. Cuatro series en 1986 es una afirmación de disponibilidad defendible, con los nombres Berlin, Braunschweig, Risoe y Wien_Hohe_Warte. El archivo da una base observacional real al periodo temprano, pero no garantiza tres ciclos completos de validación homogénea.

Mantener 2009–2024 como referencia reciente de deposición y evaluación conjunta donde existan pares válidos. El presente CSV contiene aire: no amplía por sí mismo la cobertura de deposición ni demuestra lluvia diaria desde 1986.

El correo DWD aportado describe una posible recuperación de archivo digital hasta 1996 y papel de 1980–1996 para Offenbach, Hamburg, München y Berlin. Debe presentarse como extensión por recuperar y verificar, cotejándola con lo ya disponible; no como cuatro estaciones nuevas confirmadas ni como pares completos ya incorporados.

El mismo correo define las fracciones _Fil y _Ion del sistema de recogida de precipitación. La etiqueta de laboratorio «deposición seca» para el filtro no demuestra por sí sola un flujo atmosférico de deposición seca. Antes de sumar fracciones se verifican identificador de muestra, intervalo, unidades, normalización, corrección de decaimiento y límites de detección. La comparación con deposición total o solo húmeda depende además de la exposición y funcionamiento del colector. Conservar los cambios de método de 2018 y tratar NWG como límite de detección.
