# Calculadora estructural — Brazo extensible para TV

Web app de un solo archivo (`index.html`, sin dependencias ni build) para dimensionar el perfil metálico de un brazo extensible de TV anclado a la pared.

**Uso:** abre `index.html` directamente en el navegador (o publícalo con GitHub Pages).

## Qué calcula

Modela el caso más desfavorable: el brazo totalmente extendido como **voladizo multi-tramo** (1–3 tramos, cada uno con su longitud y perfil), con la TV como carga puntual en el extremo más el peso propio de cada tramo. La flecha se integra numéricamente sobre la sección escalonada (κ = M/EI) y la tensión se comprueba al inicio de cada tramo.

**Conexiones entre tramos**: empotramiento rígido, pivote de eje vertical (codo típico de brazo de TV, rígido frente a cargas verticales), bisagra de eje horizontal y rótula esférica — estas dos últimas convierten el voladizo en un mecanismo y la app lo señala como inestable. Cada tramo muestra una **vista previa SVG de la sección** del perfil con sus dimensiones.

- **Flecha máxima en punta**: δ = P·L³/(3EI) + q·L⁴/(8EI), comparada con un límite seleccionable (L/150…L/300 o mm absolutos).
- **Tensión máxima** en el empotramiento: σ = M/W frente a f_y/FS, con veredicto **APTO / NO APTO**.
- **Reacciones en la pared** (momento y cortante) y **fuerzas por perno** (tracción de arranque y cortante) según la geometría de la placa de anclaje, para ayudar a elegir tacos.
- **Sugerencia de perfil óptimo**: el más ligero del catálogo que cumple ambas comprobaciones.
- **Esquema SVG** en vivo: pared, placa con pernos, brazo, TV y deformada exagerada.

## Catálogo

Perfiles: tubo rectangular, cuadrado y redondo, pletina y angular en L, con medidas comerciales o dimensiones personalizadas.
Materiales: acero S235/S275, aluminio 6061-T6/6063-T5 e inox 304.

## Caso de verificación

Tubo rectangular 40×20×2 en S235, TV de 15 kg + soporte de 2 kg, L = 60 cm, FS = 2, límite L/200:
A = 224 mm², I = 44 459 mm⁴, M ≈ 103,2 N·m, δ ≈ 1,32 mm (límite 3 mm), σ ≈ 46,4 MPa (admisible 117,5 MPa) → APTO.

## Aviso

Herramienta orientativa y educativa; **no sustituye el cálculo de un técnico competente** ni la normativa aplicable (CTE / Eurocódigo). No considera cargas dinámicas, fatiga, pandeo lateral-torsional ni soldaduras. La capacidad real de los anclajes depende del material del muro: consulta las fichas del fabricante del taco.

## Licencia

MIT — ver [LICENSE](LICENSE).
