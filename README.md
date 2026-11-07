# MPMG Gelabert 3D

Modelo 3D interactivo del **Aeropuerto Internacional Marcos A. Gelabert (MPMG, Albrook, Panamá)** para estudio aeronáutico. Funciona en el navegador, en computadora y en celular.

**Autor:** Delta Charlie (Derek Cuan) · [github.com/Bugaryy](https://github.com/Bugaryy)
**Fuente de datos:** AIP Panamá, AD 2.2-MPMG (AMDT AIRAC 11, 03 SEP 26)

> ⚠️ Herramienta de estudio. **No apta para uso operacional ni para navegación.** Consulte siempre el AIP vigente.

---

## Funciones

- **Tocar para ver información:** pista 01/19, calles de rodaje A–G, plataformas APN INTL y APN, terminal, hangares, torre de control, PAPI y obstáculos. El elemento se resalta en ámbar y se abre su ficha con datos del AIP.
- **Buscador:** lleva la cámara a cualquier calle, hangar, obstáculo o punto de interés.
- **Pista detallada:** umbrales desplazados (135 m / 165 m), flechas, designadores, punto de visada, eje, fajas laterales, chevrones y SWY de 100 m en el extremo 19.
- **Calles de rodaje:** anchos del AD 2.8, eje y bordes pintados, puntos de espera con letreros, y luces de borde solo donde el AIP las publica (A, B, C, D, E y G).
- **Edificios:** 63 trazados a mano sobre la imagen satelital. Los hangares tienen portones orientados hacia su calle de rodaje, y el terminal y las oficinas tienen ventanas.
- **Torre de control** en la coordenada del AD 2.18, con faro de aeródromo (destellos verde/blanco).
- **Relieve y obstáculos:** Cerro Ancón, Sosa, Corozal y Los Ríos, y los obstáculos del AD 2.10 con su elevación publicada.
- **Capas:** imagen satelital (si se apaga, queda césped verde y asfalto), etiquetas, edificios, letreros, luces, obstáculos, zona de tránsito (ATZ, 2100 ft) y circuito de tránsito.
- **Modo nocturno** con luces aeronáuticas visibles a distancia (una llamada de dibujo por color, sin lag).
- **Vistas rápidas:** general, final RWY 01, final RWY 19, desde la torre, Cerro Ancón y bloque de hangares.
- **Panel AIP:** frecuencias, horarios, mínimas VFR, circuito, aves y datos generales del aeródromo.

## Controles

| Acción | Mouse | Pantalla táctil |
|---|---|---|
| Desplazar | Clic izquierdo + arrastrar | Un dedo |
| Rotar / inclinar | Clic derecho + arrastrar (velocidad reducida a la mitad) | Dos dedos (girar) |
| Zoom | Rueda | Pellizcar |
| Seleccionar | Clic | Tocar |

## Precisión del modelo

| Elemento | Fuente | Precisión |
|---|---|---|
| Pista, umbrales, elevaciones | Coordenadas del AIP | Exacta (pista medida: 1799,55 m frente a 1800 m publicados) |
| Imagen satelital | Capturas georreferenciadas con los umbrales del AIP | Error del eje de pista ≈ 1 m |
| Calles de rodaje | Trazadas sobre la imagen y comparadas con el plano de aeródromo (ADC) | Pocos metros |
| Huellas de edificios | Trazadas a mano sobre la imagen | Pocos metros |
| Alturas de edificios y torre | Estimadas (el AIP no las publica) | Aproximadas |
| Relieve de cerros | Construido a partir de las cotas del AD 2.10 (no es un modelo de elevación) | Aproximado |
| Puntos de espera | 75 m del eje (referencia OACI; no publicado en el AIP) | Aproximada |
| PAPI y mangas de viento | Posición tomada del ADC | Aproximada |

## Archivos

| Archivo | Contenido |
|---|---|
| `index.html` | Visor completo (interfaz, escena 3D y lógica) |
| `data.json` | Geometría y datos: pista, calles, plataformas, edificios, obstáculos, ATZ |
| `tex_core.jpg` | Imagen satelital del área central (0,5 m/píxel) |
| `tex_field.jpg` | Imagen satelital del aeródromo (1 m/píxel) |
| `tex_wide.jpg` | Imagen satelital del entorno (2 m/píxel) |

## Ejecutar en local

El visor carga `data.json` y las texturas con `fetch`, así que necesita un servidor web: abrir el archivo directamente con doble clic no funciona.

```bash
cd carpeta-del-proyecto
python3 -m http.server 8000
# abrir http://localhost:8000
```

Necesita conexión a internet para cargar three.js y las fuentes desde CDN.

## Tecnología

- [three.js](https://threejs.org) r160 (MIT): escena 3D, controles de mapa
- Shaders propios para el terreno (satélite o césped), los techos y el brillo nocturno
- Tipografías IBM Plex Sans Condensed e IBM Plex Mono (OFL 1.1)

## Licencia

**Software propietario. Todos los derechos reservados.** © 2026 Derek Cuan ("Delta Charlie").
Para copiar, distribuir, modificar o usar el modelo con fines comerciales hace falta autorización escrita del autor. Ver [`LICENSE`](LICENSE).

Las imágenes satelitales pertenecen a Google y a sus proveedores, y los datos aeronáuticos a la Autoridad Aeronáutica Civil de Panamá. Ninguno de los dos está cubierto por esta licencia. **Antes de vender o distribuir públicamente el modelo, reemplace las imágenes por otras con licencia comercial.**
