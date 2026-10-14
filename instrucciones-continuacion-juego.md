# Continuación del proyecto: Juego de los aparatos del cuerpo humano

## Objetivo
Desarrollar una aplicación educativa para una niña de 10 años que estudia la organización del cuerpo y la función de nutrición. Debe ser dinámica, atractiva y adecuada para preparar un examen, especialmente la identificación de órganos sobre dibujos.

El usuario va a continuar con otra IA. Este documento recoge los requisitos, el contenido y las limitaciones conocidas. No presupongas que dispones del último HTML: solicita que el usuario lo adjunte si no está disponible. El último archivo se llamó `index.html`.

## Requisitos no negociables
- Una única interfaz de entrada y un único archivo `index.html` para TODO.
- HTML, CSS y JavaScript integrados. Las ilustraciones deben estar incorporadas, preferiblemente como SVG inline.
- Destino: GitHub Pages. Sin servidor, compilación, cuentas, APIs, bibliotecas ni recursos externos obligatorios.
- No entregar las preguntas y las láminas en archivos independientes.
- Cada modalidad de preguntas debe cubrir TODO el contenido por sí sola, no repartir el temario entre modalidades ni ofrecer solo una muestra aleatoria.
- En las láminas, preguntar TODAS las partes señaladas en las imágenes originales y NINGUNA parte adicional.
- Mantener el cuaderno de estudio con TODO el texto transcrito, conservando las negritas. No reemplazarlo por un resumen ni una lista de definiciones.
- Cada aparato debe ocupar un acordeón propio. La organización del cuerpo y la nutrición deben estar en un quinto apartado.
- Generar y entregar el archivo real: el usuario ha indicado repetidamente que no veía el HTML adjunto. No afirmar que está adjunto sin haberlo generado y verificado.
- Al modificar una funcionalidad, preservar las demás.

## Público, tono e interacción
- Niña de 10 años. Español.
- Instrucciones cortas, claras y amables.
- Sin límite de tiempo por defecto ni penalizaciones desmotivadoras.
- Diseño alegre, sin distracciones excesivas ni sonidos obligatorios.
- Corrección inmediata con explicación.
- Repaso de errores, conservando las respuestas correctas cuando proceda.
- Admitir mayúsculas/minúsculas y omisión de tildes; recortar espacios sobrantes.
- No depender del color para comunicar aciertos y errores: añadir texto e iconos.
- Usable con teclado y adaptable a móvil, tableta y ordenador.
- Respetar `prefers-reduced-motion`.

## Menú único
La versión más reciente tenía estas entradas:
1. ✏️ Palabra secreta: rellenar huecos.
2. 🔗 Conecta las pistas: emparejar.
3. 🔍 Detective del cuerpo: verdadero o falso.
4. 🚀 Gran aventura: misión combinada.
5. 🎯 Identifica las partes: láminas.
6. 📚 Mi cuaderno de estudio: consulta del texto completo.

Los nombres lúdicos pueden conservarse, pero debe quedar claro el tipo de ejercicio.

## Modalidades de preguntas
### Rellenar huecos
- Banco de palabras opcional.
- En la última versión había 56 preguntas, una por punto de estudio.
- Actualmente se pregunta el concepto a partir de una descripción: `____: descripción`.
- No excluir contenido por azar. El orden puede barajarse.
- Evitar exigir una redacción literal cuando existen respuestas equivalentes correctas.

### Emparejar
- En la última versión: 14 retos de 4 parejas, 56 relaciones en total.
- Desplegables accesibles; no exigir arrastrar.
- Todos los puntos deben aparecer una vez por recorrido completo.
- Si un reto solo cuenta como acierto cuando todas sus parejas son correctas, indicar esa regla en resultados.

### Verdadero o falso
- En la última versión: 56 preguntas, una por punto.
- Explicar la relación correcta después de responder.
- La implementación generaba falsedades cruzando conceptos y descripciones. Revisar este mecanismo: puede crear frases demasiado obvias o accidentalmente verdaderas. Preferible un banco de afirmaciones falsas revisadas.
- No considerar verdadero/falso como sustituto de las otras modalidades: cada una cubre el temario completo.

### Misión combinada
- En la última versión recorre 56 puntos alternando aleatoriamente huecos y verdadero/falso.
- No incluye emparejar ni láminas en esa mezcla actualmente; no afirmar que sí.
- No usar una muestra de 12 preguntas como en la primera propuesta, porque el usuario exigió cobertura completa.

## Láminas: requisitos exactos
Actividad típica de examen: dibujo sin nombres, líneas o flechas y casillas para escribir el nombre de lo señalado.

Implementación actual: SVG con flechas numeradas; respuestas al lado en pantallas amplias y debajo en móvil. Coordenadas de dibujo y flechas en un mismo `viewBox`, en la última versión `0 0 600 600`.

Dos modos:
- Práctica: banco de palabras opcional.
- Examen: sin banco de palabras.

Corregir cada señalamiento independientemente, marcar su flecha y casilla, mostrar la respuesta correcta, permitir repetir fallos. Las repeticiones de «válvula» y «uréter» son intencionadas.

### Digestivo: 9 señalamientos
1. Boca.
2. Glándulas salivales.
3. Faringe.
4. Esófago.
5. Hígado.
6. Estómago.
7. Páncreas.
8. Intestino grueso.
9. Intestino delgado.

No añadir el ano como pregunta de la lámina: aparece en el texto, pero no está etiquetado en ese esquema.

### Respiratorio: 9 señalamientos
1. Fosas nasales.
2. Faringe.
3. Laringe.
4. Tráquea.
5. Bronquios.
6. Pulmón.
7. Diafragma.
8. Alvéolos.
9. Vasos sanguíneos.

Alvéolos y vasos sanguíneos aparecen en el detalle ampliado del esquema. Incluir ese detalle y comprobar que ambas flechas distinguen las estructuras. No añadir bronquiolos u otros nombres no pedidos.

### Corazón / circulatorio: 8 señalamientos
1. Venas.
2. Arterias.
3. Aurícula derecha.
4. Aurícula izquierda.
5. Válvula, en el lado derecho anatómico.
6. Válvula, en el lado izquierdo anatómico.
7. Ventrículo derecho.
8. Ventrículo izquierdo.

La derecha anatómica aparece a la izquierda del dibujo. Las flechas de las válvulas deben terminar en las estructuras entre aurículas y ventrículos, no en la pared o en otra región.
No exigir nombres como aorta, vena cava, válvula mitral o tricúspide: NO aparecen como etiquetas en el material.

### Excretor: 5 señalamientos
1. Riñones: el rótulo original señala ambos; puede tener dos ramas.
2. Uréter de un lado.
3. Uréter del otro lado.
4. Vejiga urinaria.
5. Uretra.

Distinguir cuidadosamente uréter y uretra. No añadir glándulas suprarrenales, vasos renales ni nefronas a esta lámina.

Total: 31 señalamientos, no 31 nombres distintos.

### Variantes aceptadas actualmente
- Pulmón / pulmones.
- Válvula / válvulas.
- Uréter / uréteres.
- Vejiga urinaria / vejiga.
- Riñones / riñón.
Todas con normalización de tildes y mayúsculas. Revisar si el singular de riñones resulta apropiado al señalar ambos.

### Ilustraciones y derechos
El usuario indicó que es para uso personal de su familia y no quiere detener el trabajo por permisos. Las entregas realizadas usaron ilustraciones SVG propias y esquemáticas, no las fotografías del libro.
No dar por demostrado que cualquier uso privado elimina todos los requisitos de derechos ni prometer que GitHub Pages será privado. No es necesario discutirlo para continuar con ilustraciones propias.
El usuario prioriza la fidelidad anatómica y que los señalamientos coincidan con lo estudiado.

## Cuaderno de estudio: texto completo que debe conservarse
Las siguientes negritas son el formato que debe trasladarse a `<strong>` en el HTML. Los títulos pueden ser encabezados/summary; cada apartado debe ser un acordeón.

### Acordeón 1: Organización del cuerpo y función de nutrición
#### ¿Cómo es nuestro cuerpo?
Nuestro cuerpo está formado por **células**, que se agrupan formando **tejidos**. Los tejidos se agrupan formando **órganos** y estos se agrupan formando **aparatos y sistemas**.

#### ¿Qué es la función de nutrición?
La **nutrición** consiste en tomar alimentos y agua, respirar oxígeno y utilizar esas sustancias para obtener energía, vivir, crecer y expulsar los desechos.

### Acordeón 2: El aparato digestivo
Se encarga de romper los alimentos en nutrientes, que atraviesan sus paredes y pasan a la sangre. Está formado por:
- El **tubo digestivo** (boca, faringe, esófago, estómago, intestino y ano).
- Las **glándulas digestivas** (glándulas salivales, hígado y páncreas).

La **digestión** es el proceso por el cual se transforman los alimentos y se extraen los nutrientes que se absorben y pasan a la sangre. Los restos no aprovechables se expulsan al exterior.

Textos del esquema: Boca; Glándulas salivales; Faringe; Esófago; Hígado; Estómago; Páncreas; Intestino grueso; Intestino delgado.

### Acordeón 3: El aparato respiratorio
Se encarga de extraer del aire el oxígeno y de eliminar el dióxido de carbono, que producen las células como desecho. Está formado por:
- Las **vías respiratorias** (fosas nasales, faringe, laringe, tráquea, bronquios).
- Los **pulmones**, que están separados del abdomen por un músculo llamado **diafragma**, están formados por las ramificaciones de los bronquios y por los alvéolos.

La **respiración** consiste en tomar el oxígeno del aire y expulsar el dióxido de carbono que se genera como producto de desecho. Consta de tres etapas: la inspiración, el intercambio de gases y la espiración.

Textos del esquema: Fosas nasales; Faringe; Laringe; Tráquea; Bronquios; Pulmón; Diafragma; Vasos sanguíneos.

Los **alvéolos** son pequeños saquitos rodeados de finísimos vasos sanguíneos.

### Acordeón 4: El aparato circulatorio
Se encarga de **distribuir los nutrientes** y el oxígeno hasta las células y de **retirar los desechos**. Está formado por los **vasos sanguíneos** y el **corazón**. Por su interior circula la **sangre**.

El **corazón** está dividido en dos partes incomunicadas (derecha e izquierda). Y cada parte se divide en dos: **aurícula y ventrículo**.

Textos del esquema: Venas; Arterias; Aurícula derecha; Aurícula izquierda; Válvula (dos señalamientos); Ventrículo derecho; Ventrículo izquierdo.

El latido cardiaco es el movimiento continuo de contracción y dilatación del corazón.
- Cuando el corazón **se contrae**, las cavidades se comprimen y la sangre sale por las arterias hacia los órganos.
- Cuando el corazón **se dilata**, las cavidades se ensanchan y la sangre entra al corazón por las venas desde los órganos.

### Acordeón 5: El aparato excretor
Está formado por los **riñones** y **las vías urinarias** (uréteres, vejiga urinaria y uretra).

Textos del esquema: Riñones; Uréter (dos señalamientos); Vejiga urinaria; Uretra.

Los riñones están formados por finísimos tubos envueltos de capilares sanguíneos llamados **nefronas**.

Las nefronas reciben sangre del cuerpo, la filtran para limpiarla y producen la **orina**.

## Banco de 56 puntos de estudio de la última versión
Cada punto aparece en huecos, verdadero/falso y emparejar. Conservar la cobertura, pero mejorar formulaciones o aceptar sinónimos si hace falta. No confundir este banco resumido con el cuaderno íntegro anterior.
1. Células — Unidades que forman el cuerpo
2. Tejidos — Agrupaciones de células
3. Órganos — Agrupaciones de tejidos
4. Aparatos y sistemas — Agrupaciones de órganos
5. Nutrición — Tomar alimentos y agua, respirar oxígeno y utilizar esas sustancias
6. Finalidad de la nutrición — Obtener energía, vivir, crecer y expulsar desechos
7. Aparato digestivo — Transforma los alimentos y extrae nutrientes
8. Nutrientes absorbidos — Atraviesan las paredes del aparato digestivo y pasan a la sangre
9. Componentes del aparato digestivo — Tubo digestivo y glándulas digestivas
10. Boca — Inicio del tubo digestivo
11. Faringe digestiva — Parte del tubo digestivo entre boca y esófago
12. Esófago — Parte del tubo digestivo entre faringe y estómago
13. Estómago — Parte del tubo digestivo entre esófago e intestino
14. Intestinos del esquema — Intestino grueso e intestino delgado
15. Ano — Final del tubo digestivo
16. Glándulas salivales — Glándulas digestivas representadas junto a la boca
17. Hígado — Glándula digestiva nombrada junto a las salivales y el páncreas
18. Páncreas — Glándula digestiva nombrada junto a las salivales y el hígado
19. Digestión — Transformación de alimentos y extracción de nutrientes que se absorben y pasan a la sangre
20. Restos no aprovechables — Se expulsan al exterior
21. Aparato respiratorio — Extrae oxígeno del aire y elimina dióxido de carbono
22. Oxígeno — Gas que el aparato respiratorio extrae del aire
23. Dióxido de carbono — Gas que producen las células como desecho
24. Componentes del aparato respiratorio — Vías respiratorias y pulmones
25. Fosas nasales — Primeras vías respiratorias del listado del texto
26. Faringe respiratoria — Vía respiratoria entre fosas nasales y laringe
27. Laringe — Vía respiratoria entre faringe y tráquea
28. Tráquea — Vía respiratoria entre laringe y bronquios
29. Bronquios — Sus ramificaciones forman parte de los pulmones
30. Pulmones — Están formados por ramificaciones de los bronquios y alvéolos
31. Diafragma — Músculo que separa los pulmones del abdomen
32. Alvéolos — Pequeños saquitos rodeados de finísimos vasos sanguíneos
33. Respiración — Tomar oxígeno del aire y expulsar dióxido de carbono
34. Inspiración — Primera de las tres etapas de la respiración
35. Intercambio de gases — Etapa entre inspiración y espiración
36. Espiración — Última de las tres etapas de la respiración
37. Aparato circulatorio — Distribuye nutrientes y oxígeno hasta las células y recoge desechos
38. Componentes del aparato circulatorio — Vasos sanguíneos y corazón
39. Sangre — Circula por el interior del aparato circulatorio
40. Partes del corazón — Derecha e izquierda, incomunicadas entre sí
41. Aurículas — Hay una derecha y una izquierda, una en cada parte del corazón
42. Ventrículos — Hay uno derecho y uno izquierdo, uno en cada parte del corazón
43. Válvulas — Estructuras señaladas con ese nombre en ambos lados del esquema del corazón
44. Latido cardiaco — Movimiento continuo de contracción y dilatación del corazón
45. Contracción del corazón — Las cavidades se comprimen y la sangre sale hacia los órganos
46. Arterias — La sangre sale del corazón por ellas hacia los órganos
47. Dilatación del corazón — Las cavidades se ensanchan y la sangre entra desde los órganos
48. Venas — La sangre entra al corazón por ellas desde los órganos
49. Componentes del aparato excretor — Riñones y vías urinarias
50. Uréteres — Vías urinarias señaladas a ambos lados en el esquema
51. Vejiga urinaria — Parte de las vías urinarias señalada por encima de la uretra
52. Uretra — Parte de las vías urinarias señalada por debajo de la vejiga
53. Nefronas — Finísimos tubos de los riñones rodeados de capilares sanguíneos
54. Capilares sanguíneos del riñón — Rodean los finísimos tubos llamados nefronas
55. Filtración en las nefronas — Limpia la sangre que reciben del cuerpo
56. Orina — Producto que elaboran las nefronas al filtrar la sangre

## Estilo visual que debe conservarse
- Fondo claro con degradados suaves y tarjetas blancas redondeadas.
- Cabecera violeta de exploradores, iconos/emoji y aspecto lúdico.
- Tarjetas de misión con colores distintos.
- Tipografía legible, botones grandes y foco de teclado visible.
- Barra de progreso y contador de aciertos.
- Aciertos en verde; errores en ámbar, siempre con mensajes.
- Pantalla de resultados con medalla y estadísticas.
- Cuaderno con botones «Abrir todos» y «Cerrar todos».
- El cuaderno debe poder consultarse mientras se realiza cualquier actividad sin reiniciar la sesión.

## Estado de la última entrega y pruebas pendientes
La última entrega generó un `index.html` de aproximadamente 39 KB con:
- 56 puntos de preguntas.
- 4 SVG y 31 señalamientos.
- 5 acordeones de estudio con texto completo.
- 26 fragmentos `<strong>` en el cuaderno.
- Una pantalla de entrada con seis tarjetas.

Se verificó por programación la existencia del archivo, los recuentos y que no hubiera identificadores HTML estáticos repetidos. NO se ejecutó una prueba completa en navegador ni se hizo una validación visual anatómica independiente. No afirmar que está completamente probado.

Pendientes importantes:
1. Abrir el archivo en un navegador y revisar errores de consola.
2. Probar todas las modalidades, resultados, repetición y navegación.
3. Confirmar que cada señalamiento termina exactamente en la estructura prevista, sobre todo intestino delgado, válvulas, vasos de los alvéolos y uréteres.
4. Revisar la fidelidad de las ilustraciones: son esquemáticas y pueden necesitar mejoras.
5. Verificar la correspondencia de negritas con las fotos originales si están disponibles. Los encabezados y los textos entre paréntesis añadidos para explicar repeticiones no deben confundirse con transcripción literal.
6. Revisar aceptaciones de respuestas equivalentes, particularmente conceptos largos como «Faringe digestiva» o «Finalidad de la nutrición»: no deberían penalizar conocimiento correcto por una etiqueta artificial.
7. Revisar las afirmaciones falsas generadas automáticamente y el equilibrio de dificultad.
8. Probar escritorio y móvil; evitar flechas cruzadas ambiguas y textos diminutos.
9. La última versión no persiste progreso: al recargar o cerrar se pierde. No prometer guardado.
10. Las ilustraciones no son las fotografías originales: explicar esto si se pregunta por similitud con el examen.

## Lista de aceptación antes de entregar
- [ ] Un solo `index.html` con HTML, CSS, JS y SVG integrados.
- [ ] Todas las actividades desde el mismo menú.
- [ ] Cobertura íntegra por modalidad, no selección parcial.
- [ ] Exactamente 9 + 9 + 8 + 5 señalamientos en las láminas.
- [ ] No añadir nombres anatómicos fuera del material.
- [ ] Texto completo del cuaderno, no resumen.
- [ ] Negritas preservadas.
- [ ] Cinco acordeones, uno por aparato y uno introductorio.
- [ ] Acceso al cuaderno sin perder las respuestas.
- [ ] Corrección, explicaciones y repaso de errores operativos.
- [ ] Respuestas tolerantes a tildes y mayúsculas.
- [ ] Funcionamiento sin conexión y sin dependencias externas.
- [ ] Sin errores JavaScript y sin IDs duplicados.
- [ ] Revisión visual y anatómica real; distinguir comprobaciones automáticas de revisión humana.
- [ ] Archivo creado, no vacío y entregado realmente al usuario.

## Instrucción de continuación sugerida
«Continúa este proyecto desde el HTML que te adjunto y este documento. Mantén todas las funcionalidades y el contenido, no lo reconstruyas reduciéndolo. Revisa primero la cobertura, el cuaderno íntegro y la precisión de las flechas. Devuelve un único index.html completo y funcional, con una interfaz de entrada común y sin archivos auxiliares obligatorios. Indica las pruebas realizadas y las limitaciones pendientes.»
