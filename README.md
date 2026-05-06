# dpp-textil

Hoja de ruta + demos navegables del Digital Product Passport para productos textiles UE, mantenidos por Code Contract S.L.

URL publica: https://codecontract-dpp.github.io/dpp-textil/

## Contenido

```
dpp-textil/
├── index.html          ← landing (marco regulatorio + listado de demos)
├── xenon/              ← Demo XENON Ternua (Adrenalite Series SS26)
│   ├── index.html
│   ├── assets/
│   └── data/
└── (futuro: demina/, etc.)
```

## Estado regulatorio

**El acto delegado textil del ESPR (Reg. UE 2024/1781) NO esta adoptado a fecha de publicacion de este repositorio.** Toda referencia a obligaciones especificas del DPP textil es indicativa, no vinculante. Las fechas que aparecen como "estimadas" son lecturas sectoriales, no fechas oficiales publicadas en el OJ.

Posicionamiento del proyecto: **preparacion temprana** + validez legal de los datos certificados via eIDAS QES (Code Contract Trackline).

## Demos disponibles

| Demo | Marca | Producto | Patron que materializa |
|---|---|---|---|
| `xenon/` | Ternua | XENON Jacket M + Hood Jacket M | Herencia de masters comunes entre prendas hermanas, 6 fases del DPP textil |
| `demina/` (pendiente) | Ternua | DEMINA Hard Hood W | 3 capas (modelo+lote+item), serializacion GS1 AI 21, eventos post-venta firmados eIDAS QES |

## Origen de los datos

- **Datos publicos verificables**: extraidos de `ternua.com` (SKU, color, peso, precio, talla, imagen, coleccion, claims, cuidado).
- **Composicion de fibra y % reciclado**: estimacion coherente con tecnologia Dryshell, marcada como `partial` en el JSON con explicacion.
- **Masters mock** (operador economico, planta Tier 1, lab, certificados, EPR, NIF/LEI/EORI): **ficticios**, generados por Code Contract para ilustrar la estructura del DPP. No representan la realidad operativa de Ternua Group S.L. ni de los proveedores citados.
- **Trackline evidence**: hashes y processIds simulados.

## Disclaimer

Datos ficticios para fines demostrativos. No constituyen asesoramiento juridico ni compromiso comercial. La planta Tier 1 "Confecciones Atlantico S.A.", el GLN, el LEI, el EORI y los numeros de certificado son ficticios. Los GTINs simulados (8412345678035 y derivados) tienen check digit GS1 valido pero no estan registrados en AECOC.

## Stack tecnico

Sitio estatico - HTML + CSS + JavaScript vanilla. No hay build step. Sin frameworks, sin dependencias externas. Los JSON se cargan via `fetch()` en runtime, por eso no funciona con doble-click local: hay que servir desde un servidor estatico.

Para desarrollo local:

```bash
cd xenon/
python3 -m http.server 8000
# abrir http://localhost:8000
```

## Stack regulatorio referenciado

- **ESPR** Reg. UE 2024/1781 (marco horizontal)
- **Working Plan ESPR 2025-2030** COM(2025) 772
- **CIRPASS-2** deliverables (preparacion DPP)
- **JTC 24** serie EN 18xxx (DPP horizontal)
- **GS1 Digital Link** AI 01/10/21 (identificacion modelo+lote+item)
- **W3C Verifiable Credentials** + **DataIntegrityProof** ecdsa-rdfc-2019
- **eIDAS QES** (firma cualificada con validez legal)
- **Reg. 1007/2011** etiquetado textil
- **REACH SVHC** + **SCIP**
- **CSDDD** Dir. UE 2024/1760
- **Reg. UE 2024/3015** trabajo forzoso
- **PEFCR** Apparel & Footwear v3.1
- **WFD** EPR textil

## Mantenimiento

Para actualizar un demo: editar archivos en `xenon/data/*.json` (o equivalente), commit + push a `main`. GitHub Pages republica en menos de 1 minuto. El HTML del demo lee los JSON via `fetch()` por lo que no necesita re-build.

## Repos hermanos

- [dpp-construccion](https://codecontract-dpp.github.io/dpp-construccion/) - Hoja de ruta DPP para productos de construccion (CPR + ESPR)
- [dpp-validator](https://codecontract-dpp.github.io/dpp-validator/) - Validador estructural CIRPASS

## Contacto

- Web corporativa: https://codecontract.io
- Plataforma Trackline: https://web.codecontractplattform.com/
- Email: adkady@gmail.com

---

Code Contract S.L. - 2026
