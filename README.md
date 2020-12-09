Historial de COVID en la comuna a elección
================

## 0.1 Paquetes necesarios

Para generar los informes reproducibles creados por este repositorio,
necesitamos instalar los paquetes *tidyverse*, *gganimate*, *ggrepel*.
*rmarkdown*, *gifski* y *lubridate*. Sin embargo si instalas los
paquetes *pacman* y *rmarkdown*, abres el documento `README.Rmd` y
apretas el botton **Knit**, el script se ocupará de instalar los
paquetes necesarios, para eso solo tienes que correr esto en tu consola:

``` r
install.packages("rmarkdown")
install.packages("pacman")
```

## 0.2 Que hacer con este repositorio

En este repositorio, lo único que necesitas hacer es en la linea 36 de
codigo, cambiar las comunas que aparecen como ejemplo por las que
quieras visualizar, y esto generará un *GIF* con la evolución de la
prevalencia de casos activos para las comunas seleccionadas y un informe
en PDF con las tendencias de la últimas dos semanas. Debes escribir los
nombres de las comunas tal y como aparecen en la tabla que aparece al
final de este
documento:

### 0.2.1 Comunas a revisar:

``` r
Comunas <- c("Punta Arenas", "La Florida", "Vina del Mar", "Nunoa", "Valparaiso", "Concon", "Talagante", "San Bernardo", "Macul", "Las Condes", "Valdivia")
```

Una vez que hayas cambiado las comunas de la linea 42, y apretes Knit,
aparecera un HTML con el gif de las comunas que seleccionaste:

![](README_files/figure-gfm/GIF-1.gif)<!-- -->

Este está actualizado en el último informe epidemiológico, la última
fecha includia fué 2020-12-07, a continuación vemos una tabla con las 5
comunas con mas casos en la útlitma fecha
disponible:

<table class="table table-striped table-hover" style="margin-left: auto; margin-right: auto;">

<thead>

<tr>

<th style="text-align:left;">

Region

</th>

<th style="text-align:left;">

Codigo region

</th>

<th style="text-align:left;">

Comuna

</th>

<th style="text-align:left;">

Codigo comuna

</th>

<th style="text-align:right;">

Poblacion

</th>

<th style="text-align:left;">

Fecha

</th>

<th style="text-align:right;">

Activos

</th>

<th style="text-align:right;">

Activos\_por\_100.000

</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;">

Magallanes y la Antartica

</td>

<td style="text-align:left;">

12

</td>

<td style="text-align:left;">

Punta Arenas

</td>

<td style="text-align:left;">

12101

</td>

<td style="text-align:right;">

141984

</td>

<td style="text-align:left;">

2020-12-07

</td>

<td style="text-align:right;">

378

</td>

<td style="text-align:right;">

266.22718

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Rios

</td>

<td style="text-align:left;">

14

</td>

<td style="text-align:left;">

Valdivia

</td>

<td style="text-align:left;">

14101

</td>

<td style="text-align:right;">

176774

</td>

<td style="text-align:left;">

2020-12-07

</td>

<td style="text-align:right;">

375

</td>

<td style="text-align:right;">

212.13527

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

05

</td>

<td style="text-align:left;">

Vina del Mar

</td>

<td style="text-align:left;">

05109

</td>

<td style="text-align:right;">

361371

</td>

<td style="text-align:left;">

2020-12-07

</td>

<td style="text-align:right;">

219

</td>

<td style="text-align:right;">

60.60254

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

05

</td>

<td style="text-align:left;">

Concon

</td>

<td style="text-align:left;">

05103

</td>

<td style="text-align:right;">

45889

</td>

<td style="text-align:left;">

2020-12-07

</td>

<td style="text-align:right;">

26

</td>

<td style="text-align:right;">

56.65846

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

05

</td>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

05101

</td>

<td style="text-align:right;">

315732

</td>

<td style="text-align:left;">

2020-12-07

</td>

<td style="text-align:right;">

167

</td>

<td style="text-align:right;">

52.89296

</td>

</tr>

</tbody>

</table>

## 0.3 Tendencia a disminución/aumento en las últimas 2 semanas

En la siguiente tabla se ordenen las comunas en orden acendente según la
tendencia de aumento de casos activos por cada 100.000 habitantes en las
últimas dos semanas, si los valores son negativos, esto implica una
disminución y si son positivos un aumento de casos.

<table>

<thead>

<tr>

<th style="text-align:right;">

Aumento por día

</th>

<th style="text-align:left;">

Comuna

</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:right;">

\-0.7382210

</td>

<td style="text-align:left;">

Concon

</td>

</tr>

<tr>

<td style="text-align:right;">

\-0.4657129

</td>

<td style="text-align:left;">

Punta Arenas

</td>

</tr>

<tr>

<td style="text-align:right;">

0.1452779

</td>

<td style="text-align:left;">

Talagante

</td>

</tr>

<tr>

<td style="text-align:right;">

0.2852582

</td>

<td style="text-align:left;">

Valparaiso

</td>

</tr>

<tr>

<td style="text-align:right;">

0.3220012

</td>

<td style="text-align:left;">

San Bernardo

</td>

</tr>

<tr>

<td style="text-align:right;">

0.3387129

</td>

<td style="text-align:left;">

Macul

</td>

</tr>

<tr>

<td style="text-align:right;">

0.4002528

</td>

<td style="text-align:left;">

La Florida

</td>

</tr>

<tr>

<td style="text-align:right;">

0.6489861

</td>

<td style="text-align:left;">

Las Condes

</td>

</tr>

<tr>

<td style="text-align:right;">

1.1325850

</td>

<td style="text-align:left;">

Vina del
Mar

</td>

</tr>

<tr>

<td style="text-align:right;">

1.2296745

</td>

<td style="text-align:left;">

Nunoa

</td>

</tr>

<tr>

<td style="text-align:right;">

1.9578174

</td>

<td style="text-align:left;">

Valdivia

</td>

</tr>

</tbody>

</table>

## 0.4 Lista de comunas

<div style="border: 1px solid #ddd; padding: 0px; overflow-y: scroll; height:200px; overflow-x: scroll; width:100%;  margin-left: auto; margin-right: auto;" class="table table-striped table-hover">

<table class="table table-striped table-hover" style="margin-left: auto; margin-right: auto;">

<thead>

<tr>

<th style="text-align:left;position: sticky; top:0; background-color: #FFFFFF;">

Region

</th>

<th style="text-align:left;position: sticky; top:0; background-color: #FFFFFF;">

Comuna

</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;">

Arica y Parinacota

</td>

<td style="text-align:left;">

Arica

</td>

</tr>

<tr>

<td style="text-align:left;">

Arica y Parinacota

</td>

<td style="text-align:left;">

Camarones

</td>

</tr>

<tr>

<td style="text-align:left;">

Arica y Parinacota

</td>

<td style="text-align:left;">

General Lagos

</td>

</tr>

<tr>

<td style="text-align:left;">

Arica y Parinacota

</td>

<td style="text-align:left;">

Putre

</td>

</tr>

<tr>

<td style="text-align:left;">

Arica y Parinacota

</td>

<td style="text-align:left;">

Desconocido Arica y Parinacota

</td>

</tr>

<tr>

<td style="text-align:left;">

Tarapaca

</td>

<td style="text-align:left;">

Alto Hospicio

</td>

</tr>

<tr>

<td style="text-align:left;">

Tarapaca

</td>

<td style="text-align:left;">

Camina

</td>

</tr>

<tr>

<td style="text-align:left;">

Tarapaca

</td>

<td style="text-align:left;">

Colchane

</td>

</tr>

<tr>

<td style="text-align:left;">

Tarapaca

</td>

<td style="text-align:left;">

Huara

</td>

</tr>

<tr>

<td style="text-align:left;">

Tarapaca

</td>

<td style="text-align:left;">

Iquique

</td>

</tr>

<tr>

<td style="text-align:left;">

Tarapaca

</td>

<td style="text-align:left;">

Pica

</td>

</tr>

<tr>

<td style="text-align:left;">

Tarapaca

</td>

<td style="text-align:left;">

Pozo Almonte

</td>

</tr>

<tr>

<td style="text-align:left;">

Tarapaca

</td>

<td style="text-align:left;">

Desconocido Tarapaca

</td>

</tr>

<tr>

<td style="text-align:left;">

Antofagasta

</td>

<td style="text-align:left;">

Antofagasta

</td>

</tr>

<tr>

<td style="text-align:left;">

Antofagasta

</td>

<td style="text-align:left;">

Calama

</td>

</tr>

<tr>

<td style="text-align:left;">

Antofagasta

</td>

<td style="text-align:left;">

Maria Elena

</td>

</tr>

<tr>

<td style="text-align:left;">

Antofagasta

</td>

<td style="text-align:left;">

Mejillones

</td>

</tr>

<tr>

<td style="text-align:left;">

Antofagasta

</td>

<td style="text-align:left;">

Ollague

</td>

</tr>

<tr>

<td style="text-align:left;">

Antofagasta

</td>

<td style="text-align:left;">

San Pedro de Atacama

</td>

</tr>

<tr>

<td style="text-align:left;">

Antofagasta

</td>

<td style="text-align:left;">

Sierra Gorda

</td>

</tr>

<tr>

<td style="text-align:left;">

Antofagasta

</td>

<td style="text-align:left;">

Taltal

</td>

</tr>

<tr>

<td style="text-align:left;">

Antofagasta

</td>

<td style="text-align:left;">

Tocopilla

</td>

</tr>

<tr>

<td style="text-align:left;">

Antofagasta

</td>

<td style="text-align:left;">

Desconocido Antofagasta

</td>

</tr>

<tr>

<td style="text-align:left;">

Atacama

</td>

<td style="text-align:left;">

Alto del Carmen

</td>

</tr>

<tr>

<td style="text-align:left;">

Atacama

</td>

<td style="text-align:left;">

Caldera

</td>

</tr>

<tr>

<td style="text-align:left;">

Atacama

</td>

<td style="text-align:left;">

Chanaral

</td>

</tr>

<tr>

<td style="text-align:left;">

Atacama

</td>

<td style="text-align:left;">

Copiapo

</td>

</tr>

<tr>

<td style="text-align:left;">

Atacama

</td>

<td style="text-align:left;">

Diego de Almagro

</td>

</tr>

<tr>

<td style="text-align:left;">

Atacama

</td>

<td style="text-align:left;">

Freirina

</td>

</tr>

<tr>

<td style="text-align:left;">

Atacama

</td>

<td style="text-align:left;">

Huasco

</td>

</tr>

<tr>

<td style="text-align:left;">

Atacama

</td>

<td style="text-align:left;">

Tierra Amarilla

</td>

</tr>

<tr>

<td style="text-align:left;">

Atacama

</td>

<td style="text-align:left;">

Vallenar

</td>

</tr>

<tr>

<td style="text-align:left;">

Atacama

</td>

<td style="text-align:left;">

Desconocido Atacama

</td>

</tr>

<tr>

<td style="text-align:left;">

Coquimbo

</td>

<td style="text-align:left;">

Andacollo

</td>

</tr>

<tr>

<td style="text-align:left;">

Coquimbo

</td>

<td style="text-align:left;">

Canela

</td>

</tr>

<tr>

<td style="text-align:left;">

Coquimbo

</td>

<td style="text-align:left;">

Combarbala

</td>

</tr>

<tr>

<td style="text-align:left;">

Coquimbo

</td>

<td style="text-align:left;">

Coquimbo

</td>

</tr>

<tr>

<td style="text-align:left;">

Coquimbo

</td>

<td style="text-align:left;">

Illapel

</td>

</tr>

<tr>

<td style="text-align:left;">

Coquimbo

</td>

<td style="text-align:left;">

La Higuera

</td>

</tr>

<tr>

<td style="text-align:left;">

Coquimbo

</td>

<td style="text-align:left;">

La Serena

</td>

</tr>

<tr>

<td style="text-align:left;">

Coquimbo

</td>

<td style="text-align:left;">

Los Vilos

</td>

</tr>

<tr>

<td style="text-align:left;">

Coquimbo

</td>

<td style="text-align:left;">

Monte Patria

</td>

</tr>

<tr>

<td style="text-align:left;">

Coquimbo

</td>

<td style="text-align:left;">

Ovalle

</td>

</tr>

<tr>

<td style="text-align:left;">

Coquimbo

</td>

<td style="text-align:left;">

Paiguano

</td>

</tr>

<tr>

<td style="text-align:left;">

Coquimbo

</td>

<td style="text-align:left;">

Punitaqui

</td>

</tr>

<tr>

<td style="text-align:left;">

Coquimbo

</td>

<td style="text-align:left;">

Rio Hurtado

</td>

</tr>

<tr>

<td style="text-align:left;">

Coquimbo

</td>

<td style="text-align:left;">

Salamanca

</td>

</tr>

<tr>

<td style="text-align:left;">

Coquimbo

</td>

<td style="text-align:left;">

Vicuna

</td>

</tr>

<tr>

<td style="text-align:left;">

Coquimbo

</td>

<td style="text-align:left;">

Desconocido Coquimbo

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Algarrobo

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Cabildo

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Calera

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Calle Larga

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Cartagena

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Casablanca

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Catemu

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Concon

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

El Quisco

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

El Tabo

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Hijuelas

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Isla de Pascua

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Juan Fernandez

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

La Cruz

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

La Ligua

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Limache

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Llaillay

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Los Andes

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Nogales

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Olmue

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Panquehue

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Papudo

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Petorca

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Puchuncavi

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Putaendo

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Quillota

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Quilpue

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Quintero

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Rinconada

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

San Antonio

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

San Esteban

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

San Felipe

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Santa Maria

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Santo Domingo

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Valparaiso

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Villa Alemana

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Vina del Mar

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Zapallar

</td>

</tr>

<tr>

<td style="text-align:left;">

Valparaiso

</td>

<td style="text-align:left;">

Desconocido Valparaiso

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Alhue

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Buin

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Calera de Tango

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Cerrillos

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Cerro Navia

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Colina

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Conchali

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Curacavi

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

El Bosque

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

El Monte

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Estacion Central

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Huechuraba

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Independencia

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Isla de Maipo

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

La Cisterna

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

La Florida

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

La Granja

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

La Pintana

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

La Reina

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Lampa

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Las Condes

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Lo Barnechea

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Lo Espejo

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Lo Prado

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Macul

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Maipu

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Maria Pinto

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Melipilla

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Nunoa

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Padre Hurtado

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Paine

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Pedro Aguirre Cerda

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Penaflor

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Penalolen

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Pirque

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Providencia

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Pudahuel

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Puente Alto

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Quilicura

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Quinta Normal

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Recoleta

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Renca

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

San Bernardo

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

San Joaquin

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

San Jose de Maipo

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

San Miguel

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

San Pedro

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

San Ramon

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Santiago

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Talagante

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Tiltil

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Vitacura

</td>

</tr>

<tr>

<td style="text-align:left;">

Metropolitana

</td>

<td style="text-align:left;">

Desconocido Metropolitana

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Chepica

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Chimbarongo

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Codegua

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Coinco

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Coltauco

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Donihue

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Graneros

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

La Estrella

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Las Cabras

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Litueche

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Lolol

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Machali

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Malloa

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Marchihue

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Mostazal

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Nancagua

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Navidad

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Olivar

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Palmilla

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Paredones

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Peralillo

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Peumo

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Pichidegua

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Pichilemu

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Placilla

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Pumanque

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Quinta de Tilcoco

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Rancagua

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Rengo

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Requinoa

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

San Fernando

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

San Vicente

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Santa Cruz

</td>

</tr>

<tr>

<td style="text-align:left;">

Del Libertador General Bernardo O’Higgins

</td>

<td style="text-align:left;">

Desconocido O’Higgins

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Cauquenes

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Chanco

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Colbun

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Constitucion

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Curepto

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Curico

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Empedrado

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Hualane

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Licanten

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Linares

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Longavi

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Maule

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Molina

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Parral

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Pelarco

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Pelluhue

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Pencahue

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Rauco

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Retiro

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Rio Claro

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Romeral

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Sagrada Familia

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

San Clemente

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

San Javier

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

San Rafael

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Talca

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Teno

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Vichuquen

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Villa Alegre

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Yerbas Buenas

</td>

</tr>

<tr>

<td style="text-align:left;">

Maule

</td>

<td style="text-align:left;">

Desconocido Maule

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Bulnes

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Chillan

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Chillan Viejo

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Cobquecura

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Coelemu

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Coihueco

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

El Carmen

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Ninhue

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Niquen

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Pemuco

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Pinto

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Portezuelo

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Quillon

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Quirihue

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Ranquil

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

San Carlos

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

San Fabian

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

San Ignacio

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

San Nicolas

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Treguaco

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Yungay

</td>

</tr>

<tr>

<td style="text-align:left;">

Nuble

</td>

<td style="text-align:left;">

Desconocido Nuble

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Alto Biobio

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Antuco

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Arauco

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Cabrero

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Canete

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Chiguayante

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Concepcion

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Contulmo

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Coronel

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Curanilahue

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Florida

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Hualpen

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Hualqui

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Laja

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Lebu

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Los Alamos

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Los Angeles

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Lota

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Mulchen

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Nacimiento

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Negrete

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Penco

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Quilaco

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Quilleco

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

San Pedro de la Paz

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

San Rosendo

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Santa Barbara

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Santa Juana

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Talcahuano

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Tirua

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Tome

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Tucapel

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Yumbel

</td>

</tr>

<tr>

<td style="text-align:left;">

Biobio

</td>

<td style="text-align:left;">

Desconocido Biobio

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Angol

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Carahue

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Cholchol

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Collipulli

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Cunco

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Curacautin

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Curarrehue

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Ercilla

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Freire

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Galvarino

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Gorbea

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Lautaro

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Loncoche

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Lonquimay

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Los Sauces

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Lumaco

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Melipeuco

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Nueva Imperial

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Padre Las Casas

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Perquenco

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Pitrufquen

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Pucon

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Puren

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Renaico

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Saavedra

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Temuco

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Teodoro Schmidt

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Tolten

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Traiguen

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Victoria

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Vilcun

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Villarrica

</td>

</tr>

<tr>

<td style="text-align:left;">

La Araucania

</td>

<td style="text-align:left;">

Desconocido Araucania

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Rios

</td>

<td style="text-align:left;">

Corral

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Rios

</td>

<td style="text-align:left;">

Futrono

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Rios

</td>

<td style="text-align:left;">

La Union

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Rios

</td>

<td style="text-align:left;">

Lago Ranco

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Rios

</td>

<td style="text-align:left;">

Lanco

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Rios

</td>

<td style="text-align:left;">

Los Lagos

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Rios

</td>

<td style="text-align:left;">

Mafil

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Rios

</td>

<td style="text-align:left;">

Mariquina

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Rios

</td>

<td style="text-align:left;">

Paillaco

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Rios

</td>

<td style="text-align:left;">

Panguipulli

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Rios

</td>

<td style="text-align:left;">

Rio Bueno

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Rios

</td>

<td style="text-align:left;">

Valdivia

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Rios

</td>

<td style="text-align:left;">

Desconocido Los Rios

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Ancud

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Calbuco

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Castro

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Chaiten

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Chonchi

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Cochamo

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Curaco de Velez

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Dalcahue

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Fresia

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Frutillar

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Futaleufu

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Hualaihue

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Llanquihue

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Los Muermos

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Maullin

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Osorno

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Palena

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Puerto Montt

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Puerto Octay

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Puerto Varas

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Puqueldon

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Purranque

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Puyehue

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Queilen

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Quellon

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Quemchi

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Quinchao

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Rio Negro

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

San Juan de la Costa

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

San Pablo

</td>

</tr>

<tr>

<td style="text-align:left;">

Los Lagos

</td>

<td style="text-align:left;">

Desconocido Los Lagos

</td>

</tr>

<tr>

<td style="text-align:left;">

Aysen

</td>

<td style="text-align:left;">

Aysen

</td>

</tr>

<tr>

<td style="text-align:left;">

Aysen

</td>

<td style="text-align:left;">

Chile Chico

</td>

</tr>

<tr>

<td style="text-align:left;">

Aysen

</td>

<td style="text-align:left;">

Cisnes

</td>

</tr>

<tr>

<td style="text-align:left;">

Aysen

</td>

<td style="text-align:left;">

Cochrane

</td>

</tr>

<tr>

<td style="text-align:left;">

Aysen

</td>

<td style="text-align:left;">

Coyhaique

</td>

</tr>

<tr>

<td style="text-align:left;">

Aysen

</td>

<td style="text-align:left;">

Guaitecas

</td>

</tr>

<tr>

<td style="text-align:left;">

Aysen

</td>

<td style="text-align:left;">

Lago Verde

</td>

</tr>

<tr>

<td style="text-align:left;">

Aysen

</td>

<td style="text-align:left;">

OHiggins

</td>

</tr>

<tr>

<td style="text-align:left;">

Aysen

</td>

<td style="text-align:left;">

Rio Ibanez

</td>

</tr>

<tr>

<td style="text-align:left;">

Aysen

</td>

<td style="text-align:left;">

Tortel

</td>

</tr>

<tr>

<td style="text-align:left;">

Aysen

</td>

<td style="text-align:left;">

Desconocido Aysen

</td>

</tr>

<tr>

<td style="text-align:left;">

Magallanes y la Antartica

</td>

<td style="text-align:left;">

Antartica

</td>

</tr>

<tr>

<td style="text-align:left;">

Magallanes y la Antartica

</td>

<td style="text-align:left;">

Cabo de Hornos

</td>

</tr>

<tr>

<td style="text-align:left;">

Magallanes y la Antartica

</td>

<td style="text-align:left;">

Laguna Blanca

</td>

</tr>

<tr>

<td style="text-align:left;">

Magallanes y la Antartica

</td>

<td style="text-align:left;">

Natales

</td>

</tr>

<tr>

<td style="text-align:left;">

Magallanes y la Antartica

</td>

<td style="text-align:left;">

Porvenir

</td>

</tr>

<tr>

<td style="text-align:left;">

Magallanes y la Antartica

</td>

<td style="text-align:left;">

Primavera

</td>

</tr>

<tr>

<td style="text-align:left;">

Magallanes y la Antartica

</td>

<td style="text-align:left;">

Punta Arenas

</td>

</tr>

<tr>

<td style="text-align:left;">

Magallanes y la Antartica

</td>

<td style="text-align:left;">

Rio Verde

</td>

</tr>

<tr>

<td style="text-align:left;">

Magallanes y la Antartica

</td>

<td style="text-align:left;">

San Gregorio

</td>

</tr>

<tr>

<td style="text-align:left;">

Magallanes y la Antartica

</td>

<td style="text-align:left;">

Timaukel

</td>

</tr>

<tr>

<td style="text-align:left;">

Magallanes y la Antartica

</td>

<td style="text-align:left;">

Torres del Paine

</td>

</tr>

<tr>

<td style="text-align:left;">

Magallanes y la Antartica

</td>

<td style="text-align:left;">

Desconocido Magallanes

</td>

</tr>

</tbody>

</table>

</div>
