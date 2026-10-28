# SimLabIA

Laboratorio de simulación clínica con IA. Aplicación web de un solo fichero (`index.html`), sin servidor ni cuentas.

**Usar la app:** https://fborrasumh.github.io/simlabia/

**Idiomas:** español (por defecto), inglés y portugués; selector en la barra superior (o `?lang=en` / `?lang=pt` en la URL).

## Qué hace

SimLabIA no es un chatbot de paciente: es un laboratorio para diseñar, probar, observar y ajustar simulaciones clínicas. Recorre el ciclo idea → escenario → paciente → revisión → entrevista → análisis → debriefing → reflexión, e incluye los 13 experimentos guiados del libro «Laboratorio de simulación clínica con IA».

- **Escenario por fases.** De una idea de dos líneas a un escenario con contexto, nivel, dificultad y 1–5 objetivos observables. Toda propuesta de la IA se acepta, se acepta y edita, se regenera o se rechaza; nada entra en el escenario sin decisión, y la decisión queda registrada.
- **Paciente con reglas de información.** Cada dato tiene su política: espontánea, si se pregunta, solo con pregunta específica, oculta o desconocida para el paciente. Historia clínica → paciente (identidad, personalidad, comunicación) y ocho personalidades sobre el mismo caso clínico.
- **Revisión del diseño.** Rúbrica de conductas observables (con «Este criterio no puede observarse»), comprobaciones deterministas y test de estrés («Romper escenario»). El escenario no se puede marcar como revisado sin test de estrés, sin decisión sobre cada problema y sin bloqueos del código; editarlo después lo devuelve a borrador.
- **Simulación.** Modos libre, condicionado, con personalidad y de demostración (sin IA). Texto o voz (dictado y lectura en voz alta, grabación opcional), y modalidad visual (imagen fija, vídeo, avatar sencillo) registrada para comparar.
- **Análisis sin notas.** Resumen, preguntas realizadas, áreas, información obtenida y la que no aparece en el registro, preguntas poco claras, tecnicismos, reformulaciones, momentos relevantes y aspectos para revisión docente. El docente marca cada observación (correcta, parcial, incorrecta, no verificable) y puede comparar su valoración con la de la IA, sin calcular ninguna «precisión».
- **Debriefing.** Estructura (reconstrucción, reflexión, análisis, alternativas, mejora) y 5–8 preguntas abiertas editables; después, una pregunta cada vez, con resumen final.
- **Experimentos, comparaciones y exportación.** Experimentos guiados (objetivo → preparación → ejecución → observación → análisis → reflexión), comparación de entrevistas del mismo escenario, ZIP por simulación (`scenario.json`, `patient.json`, `transcript.json`, `analysis.json`, `debriefing.json`), informe Word, CSV, escenario y experimento en JSON. Importación de escenarios JSON para compartirlos sin servidor.
- **Modo docente y modo estudiante.**

## Qué comprueba el código (y no la IA)

- **Revelación de información:** en modo condicionado el código decide, por palabras clave (y opcionalmente con una IA clasificadora que solo recibe los temas, nunca los valores), qué datos recibe el paciente en cada turno. Lo oculto y lo aún no desbloqueado no se envía.
- **Filtros del paciente:** se eliminan frases con palabras del diagnóstico que el estudiante no ha dicho, consejos de tutor y salidas del personaje; se señalan cifras que no están en el caso.
- **Citas:** cada observación del análisis, cada evidencia del debriefing y cada cita de las comparaciones se busca literalmente en la transcripción. Sin cita verificada, una «conducta observable» pasa a «aspecto a comprobar». Se señalan atribuciones de intención y cualquier nota o calificación.
- **Diseño:** número de objetivos, palabras del diagnóstico en datos visibles, palabras clave genéricas, edades incoherentes, temas duplicados, verbos no observables en la rúbrica.

## Cómo se usa la IA

Con la propia clave de OpenAI, Google Gemini o Anthropic Claude. Se puede usar un modelo para el paciente y otro para el análisis, ajustar la temperatura del paciente y el límite de tokens, y elegir no guardar la clave (se borra al cerrar la pestaña). El ejemplo y el paciente de demostración funcionan sin clave.

## Privacidad

Escenarios, simulaciones, análisis y reflexiones se guardan solo en el navegador (IndexedDB). Antes del primer envío de cada sesión se muestra lo que sale hacia el proveedor de IA; los correos, DNI y teléfonos de una historia pegada se enmascaran. Usa solo casos ficticios. Con dictado por voz, algunos navegadores procesan el audio en servidores del fabricante. La grabación de audio y el vídeo se quedan en memoria y no se guardan.

## Límites

- Es una herramienta de diseño y reflexión, no un evaluador clínico: no pone notas y lo que propone la IA debe revisarlo el docente.
- Las palabras clave pueden desbloquear datos de más o de menos; el test de estrés y la prueba ayudan a ajustarlas.
- Que algo no aparezca en la transcripción no significa que no se hiciera.
- El modo estudiante oculta el diseño, pero no es una barrera de seguridad.
- El dictado depende del navegador (Chrome o Edge); el avatar es deliberadamente sencillo.
- Probado con IA simulada en los tres proveedores; antes de usarlo en clase, prueba tu escenario con tu clave y tu modelo.

## Autoría

Fernando Borrás Rocher (Universidad Miguel Hernández de Elche), Antonio F. Compañ Rosique (Universidad Miguel Hernández de Elche) y Juan Carlos Rodríguez Vidal (Centro Experimental CYBORG, Universidad Miguel Hernández de Elche).

A partir de la especificación SIMLAB IA, que lleva a la práctica los experimentos del libro «Laboratorio de simulación clínica con IA».

ORCID: Fernando Borrás Rocher [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573) · Antonio F. Compañ Rosique [0000-0002-8166-396X](https://orcid.org/0000-0002-8166-396X)

## Cómo citar

Borrás Rocher, F., Compañ Rosique, A. F. y Rodríguez Vidal, J. C. (2026). *SimLabIA* (v1.0.0) [Software]. (DOI en trámite)

## Licencia

Los tres autores han aceptado publicar el código con licencia MIT.


MIT. Véase [LICENSE](LICENSE).
