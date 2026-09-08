# Cobertura observacional comprobada — STRAT-TRACE v9.9

Comprobación del 8 de septiembre de 2026. Se ha leído el CSV original sin modificarlo. La v9.9 incorpora la formulación robusta «más de 54.000 registros de 83 series» para 2009–2024. Los originales permanecen sin modificar.

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

## Interpretación para la propuesta

El archivo cuantifica la disponibilidad de concentración en aire. No contiene deposición, por lo que el número de pares aire–deposición no se puede calcular a partir de este CSV. Debe establecerse con las hojas de deposición, ventanas comparables y metadatos. La v9.7 ya conserva 2009–2024 como base conjunta prevista y requiere pares verificados.

El investigador confirma que los datos CTBTO no se han recibido todavía y comunica una expectativa de más de 80 estaciones con distribución mundial. Este alcance esperado no forma parte del inventario recibido ni se suma automáticamente a las 83 series: podría haber solapamientos. La descripción pública oficial de la red de radionúclidos indica 80 estaciones apoyadas por 16 laboratorios. La posible diferencia entre el alcance del archivo solicitado y la red nominal deberá resolverse con el listado del acuerdo o la entrega. El texto propuesto conserva el acuerdo firmado y la ampliación mundial sin fijar todavía el recuento recibido.

Fuentes: [red de radionúclidos CTBTO](https://www.ctbto.org/our-work/monitoring-technologies/radionuclide-monitoring) y [acceso científico vDEC](https://www.ctbto.org/resources/for-researchers-experts/vdec).


## Incorporación a v9.9

La sección 1.1 integra el recuento reciente y conserva las cuatro series tempranas. El acuerdo CTBTO permanece firmado con entrega pendiente. El número de pares aire–deposición y la homogeneidad de estaciones se determinarán en WP1. No se incluye el CSV original en este paquete.
