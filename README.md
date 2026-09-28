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

## Links de rutas compartidas

`r/index.html` es una página chiquita (GitHub Pages) que abre la app cuando alguien comparte una ruta por
WhatsApp: `https://noxusline.github.io/rollernox-mapa/r/?id=s-<id>` → `rollernox://ruta/s-<id>`. No
guarda ni muestra datos: la ruta la carga la app, y solo con sesión. Para que funcione hay que activar
**Settings → Pages → Deploy from a branch → `main` / `(root)`**.

**Links de salidas** (`?id=e-<id>`): en Android primero intenta abrir la app; si no está (o en iPhone y
computadora), muestra la salida con su **ruta prevista** en un mapa (Leaflet en `r/lib`, calles de
OpenStreetMap), la fecha, la hora y el punto de encuentro, un botón **Exportar recorrido** (descarga un
`.txt` con las calles por las que pasa, en orden y con sus metros: función `event_route_streets` de
Supabase) y un aviso para descargar la app. Sirve para mandarle la ruta a quien no usa RollerNox (por
ejemplo, la policía en una salida multitudinaria). Lee `events_view` con la clave *publishable* (pública, la misma de la app): son datos públicos del calendario; la ubicación en
vivo no se ve sin sesión.
