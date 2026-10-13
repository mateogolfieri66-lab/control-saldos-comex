# Control de saldos de autorizaciones

Herramienta gratuita para controlar **vigencia y saldo** de autorizaciones de importación por cantidad, antes de oficializar una operación.

> Vigente no significa disponible: una autorización puede estar en regla y aun así no alcanzar para tu próxima operación.

**Abrir la herramienta:** `index.html` (o el link de GitHub Pages de este repositorio).

## Qué hace

1. Cargás autorizaciones: código, ítem, unidad, cantidad autorizada y vencimiento.
2. Registrás las operaciones que ya usaron cantidad.
3. Simulás la próxima operación y la herramienta aplica estas reglas:

| ID | Regla | Severidad | Mensaje |
|---|---|---|---|
| R01 | La cantidad es un número mayor a cero | Bloqueante | Escribí la cantidad |
| R02 | La fecha prevista es anterior o igual al vencimiento | Bloqueante | Adelantá la operación o gestioná una nueva autorización |
| R03 | La unidad de la operación es igual a la autorizada | Bloqueante | Convertí antes de controlar, no se mezclan unidades |
| R04 | Autorizado − utilizado ≥ cantidad nueva | Bloqueante | Faltan N: reducí o pedí ampliación |
| R05 | Después de la operación queda menos del 10 % | Advertencia | Avisá antes de comprometer otra operación |
| R06 | Vence dentro de 30 días después de la operación | Información | Planificá renovación |
| R07 | La referencia ya existe en esa autorización | Advertencia | Posible duplicado |

Con una regla bloqueante no te deja registrar. Si hay advertencias, tenés que marcar que las revisaste.

## Importar desde documentos con IA

En `prompts/1-extraer-cantidades.md` hay un prompt que convierte tus PDF o Excel en un CSV con este formato:

```
tipo,codigo,item,unidad,cantidad,fecha,referencia,fuente
```

Acepta números con coma o con punto decimal y fechas en formato `AAAA-MM-DD` o `DD/MM/AAAA`. Las filas con problemas (unidad distinta, autorización inexistente, cantidad vacía) no se importan y te avisa cuáles son.

En `prompts/2-convertir-control-en-regla.md` hay un prompt para escribir cualquier control manual de tu empresa como reglas verificables, sea o no de comercio exterior.

## Límites (leelos)

- **No consulta ARCA ni ningún sistema oficial.** Trabaja solo con los datos que cargás vos.
- Los datos quedan guardados **solo en tu navegador**. Si borrás los datos del sitio, se pierden: exportá el CSV como respaldo.
- Es una herramienta educativa. Verificá siempre con tu despachante y con la normativa vigente.
- Ejemplo de contexto normativo: la RG ARCA 5909/2026 (Boletín Oficial, 05/10/2026) incorpora a la VUCEA la declaración jurada de destino minero del régimen de la Ley 24.196. Consultá el texto oficial.

## Cómo publicarla en GitHub Pages

Settings → Pages → Source: *Deploy from a branch* → Branch: `main` / `(root)` → Save. En uno o dos minutos te da el link.

---

Hecho por **Mateo Golfieri**, Lic. en Economía Empresarial · Instagram [@lic.mateogolfieri](https://instagram.com/lic.mateogolfieri)
