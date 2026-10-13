# Prompt 2 · Convertir un control que hacés "de memoria" en una regla escrita

**Para qué sirve:** sirve para cualquier rubro, no solo comercio exterior. Le contás a la IA un control que hoy hace una persona "porque ya sabe" (revisar un saldo, una fecha, un precio, un stock) y te devuelve la regla escrita: qué datos usa, cuándo bloquea, qué mensaje mostrar, quién lo resuelve y con qué casos probarla.

Con eso podés:
- Enseñarle el control a otra persona.
- Ponerlo en una planilla con fórmulas.
- Pedirle a alguien que lo programe sin que tenga que adivinar.

**Antes de automatizar, escribí la regla.**

---

```
Actuá como analista de procesos. Te voy a describir un control que hoy se hace manualmente en mi empresa. Ayudame a convertirlo en reglas escritas y verificables.

MI CONTROL (completá):
- Qué se revisa: [ej: que la autorización tenga saldo antes de cargar una operación]
- Quién lo hace hoy y cuándo: [ej: el analista, antes de oficializar]
- Qué datos mira y de dónde salen: [ej: planilla de saldos + factura del proveedor]
- Qué pasa cuando está mal: [ej: hay que frenar y pedir ampliación]
- Errores que ya pasaron: [ej: se cargó en kg una autorización en unidades]

QUÉ NECESITO:
1. Antes de responder, si falta un dato imprescindible, hacé como máximo 3 preguntas. Si no falta, seguí.
2. Una tabla de reglas con estas columnas:
   ID | Descripción | Datos y fuente | Condición (en forma de cuenta o comparación) | Tolerancia | Severidad | Mensaje para el usuario | Quién lo resuelve
   Severidad solo puede ser: Bloqueante, Advertencia, Información o Excepción con autorización.
   El mensaje tiene que decir qué pasó y cómo resolverlo, en una sola frase.
3. Casos de prueba: para cada regla, un caso que pase y uno que falle, con números concretos.
4. Excepciones: quién puede autorizar saltear cada regla bloqueante y qué tiene que quedar registrado (motivo, responsable, fecha, evidencia).
5. Separá claramente:
   - Lo que es una cuenta o comparación fija (no necesita IA).
   - Lo que requiere interpretar documentos variables (ahí puede ayudar la IA, siempre con revisión humana).
6. Si alguna regla depende de una norma, no la inventes: marcala como "PENDIENTE: verificar en fuente oficial" y decime qué buscar.

No prometas ahorro de tiempo ni cero errores. Sé concreto y usá mis palabras.
```
