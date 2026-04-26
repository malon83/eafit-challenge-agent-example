# 📡 Mapa de cobertura de telecomunicaciones – Valle de Aburrá (Antioquia)

Este documento presenta un **modelo de polígonos de cobertura** para operadores de internet, TV y telefonía en la región metropolitana del Valle de Aburrá. Es útil para planificar despliegues de fibra, HFC, wireless o evaluar expansión de servicios.

---

## Contexto geográfico

El Valle de Aburrá está compuesto por 10 municipios (de norte a sur):

| Municipio      | Cabecera | Población (miles) | Zona industrial |
|----------------|----------|------------------|----------------|
| Caldas         | Sur      | 80               | Baja            |
| La Estrella    | Sur      | 70               | Media           |
| Sabaneta       | Sur      | 85               | Media           |
| Itagüí         | Centro-Sur | 280            | Alta            |
| Envigado       | Centro-Sur | 240            | Media-Alta      |
| Medellín       | Centro   | 2600             | Muy alta        |
| Bello          | Norte    | 600              | Alta            |
| Copacabana     | Norte    | 80               | Baja            |
| Girardota      | Norte    | 60               | Baja            |
| Barbosa        | Norte    | 60               | Media-Baja      |

---

## Representación de polígonos de cobertura

Un polígono de cobertura se define mediante un conjunto de coordenadas `[longitud, latitud]` en formato **GeoJSON**. Cada polígono puede representar:

- **Cobertura total** (zona urbana o rural con servicio)
- **Capacidad tecnológica** (fibra, 4G, 5G, HFC)
- **Velocidades ofrecidas** (ej. > 300 Mbps)

## Mapa de calor de cobertura por tecnología en el Valle de Aburrá
[Barbosa]        ░░░░░░ (solo cobertura inalámbrica)
[Girardota]      ▓▓▓▓░░ (fibra parcial)
[Copacabana]     ▓▓▓▓░░ (fibra parcial)
[Bello]          ▓▓▓▓▓▓ (fibra masiva + HFC)
[Medellín]       ██████ (fibra + 5G + HFC)
[Envigado]       ██████ (fibra + 5G)
[Itagüí]         █████▓ (fibra industrial)
[Sabaneta]       ▓▓▓▓▓▓ (FTTH total)
[La Estrella]    ▓▓▓▓░░ (FTTH parcial)
[Caldas]         ░░░░░░ (proyecto futuro)
Leyenda:

█ = cobertura total (más del 90% del área urbana)

▓ = cobertura parcial (50% - 90%)

░ = cobertura baja o nula (< 50%)


### Polígono de **Medellín centro** (alta densidad + 5G)

```json

{
  "type": "Feature",
  "properties": {
    "municipio": "Medellín",
    "operador": "MetaRed",
    "tecnologia": "5G + FTTH",
    "velocidad_max_mbps": 2000,
    "cobertura": "Centro expandido"
  },
  "geometry": {
    "type": "Polygon",
    "coordinates": [[
      [-75.575, 6.240],
      [-75.560, 6.240],
      [-75.560, 6.255],
      [-75.575, 6.255],
      [-75.575, 6.240]
    ]]
  }
}