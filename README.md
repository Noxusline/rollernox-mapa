# rollernox-mapa

Mapa base vectorial de CABA para la app **RollerNox** (Noxusline).

- `caba.pmtiles`: recorte de CABA (+ ~2 km) del mapa mundial de [Protomaps](https://protomaps.com), zoom 0–15.
- `caba.json`: fecha de los datos, tamaño y zona del recorte.

Se publican en el release [`basemap`](../../releases/tag/basemap) y los genera cada lunes la acción
[`basemap.yml`](.github/workflows/basemap.yml) (también se puede correr a mano desde **Actions →
"Mapa base (CABA)" → Run workflow**).

Este repo es público solo para que la app pueda descargar el archivo sin credenciales. No contiene
código de la app.

**Datos:** © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright), disponibles bajo la
licencia ODbL. Teselas generadas por Protomaps.
