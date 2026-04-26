# 📡 Mapa de cobertura de telecomunicaciones – Valle de Aburrá (Antioquia)

Este documento presenta un **modelo de polígonos de cobertura** para operadores de internet, TV y telefonía en la región metropolitana del Valle de Aburrá. Es útil para planificar despliegues de fibra, HFC, wireless o evaluar expansión de servicios.

---

## 1. Contexto geográfico

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

## 2. Representación de polígonos de cobertura

Un polígono de cobertura se define mediante un conjunto de coordenadas `[longitud, latitud]` en formato **GeoJSON**. Cada polígono puede representar:

- **Cobertura total** (zona urbana o rural con servicio)
- **Capacidad tecnológica** (fibra, 4G, 5G, HFC)
- **Velocidades ofrecidas** (ej. > 300 Mbps)

### Ejemplo 1: Polígono de cobertura para el municipio de **Sabaneta**

```geojson
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "municipio": "Sabaneta",
        "operador": "EjemploNet",
        "tecnologia": "FTTH",
        "velocidad_max_mbps": 1000,
        "cobertura": "Urbana"
      },
      "geometry": {
        "type": "Polygon",
        "coordinates": [[
          [-75.619, 6.149],
          [-75.607, 6.149],
          [-75.607, 6.156],
          [-75.619, 6.156],
          [-75.619, 6.149]
        ]]
      }
    }
  ]
}