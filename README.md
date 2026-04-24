# AGENTE PRONOSTICADOR: FORECAST-BET
## INTEGRANTES: 
-Juan Echavez
-Nestor Rico
-Carlos Pulgar

## PERFIL DEL AGENTE: 
<img width="1471" height="798" alt="image" src="https://github.com/user-attachments/assets/a400d2b9-ae49-4362-bf85-6d5c4f0e2138" 
  
## JUSTIFICACIÓN PROCESOS COGNITIVOS 
Nuestro bot necesita mucha memoria (10/10) ya que tiene que memorizar todas las preguntas anteriores y así poder dar los mejores pronosticos.
De atención necesitará (10/10) porque cualquier error en la comprensión de un texto puede dar resultados erroneos y hará que el cliente pierde dinero.
Lenguaje (5/10) no es esencial que nuestra IA tenga el mejor habla del mundo, solo un lenguaje básico.
Emoción (3/10) la emoción es lo de menos, debe tener una emoción neutral para no incitar a las apuestas deportivas. 
<img width="1092" height="778" alt="image" src="https://github.com/user-attachments/assets/6afd71eb-50c0-4c44-abe7-2f213767b1b9" />

## 2.Procesamiento Perceptual del Sistema

El sistema transforma datos de entrada (sensación) en información significativa (percepción) para la toma de decisiones en apuestas deportivas.

---

### Sensación (Datos Crudos)

Corresponde a la información que entra al sistema sin interpretación.

Ejemplos:
- Texto del usuario: "Voy con todo al Madrid 🔥"
- Emojis: 🔥 💀
- Números: cuotas, dinero
- Equipos: Real Madrid, Barcelona
- Fecha y hora del partido

---

### Percepción (Interpretación)

El sistema interpreta los datos y les da significado.

Ejemplos:
- "Voy con todo" → intención de apuesta
- 🔥 → emoción alta
- Madrid → equipo seleccionado
- Cuota baja → baja ganancia, menor riesgo

---

### Transformación Sensación → Percepción

El sistema aplica reglas para interpretar la entrada:

- Detecta palabras clave → intención
- Identifica equipos → contexto deportivo
- Analiza emojis → estado emocional
- Reconoce números → cuotas o dinero

## 2. Arquitectura de Atención con las reglas lógicas definidas
## Reglas de Atención
1. Filtrado de Ruido
- Si el mensaje no contiene términos deportivos → IGNORAR
2. Prioridad de Entidades Clave
- Detectar y priorizar:
  - Equipos
  - Ligas
  - Cuotas
  - Tipos de apuesta
3. Regla de Longitud (Carga Cognitiva)
- Si el mensaje tiene más de 500 palabras:
  → Extraer únicamente:
     - Sustantivos clave
     - Última frase del mensaje
4. Detección de Intención
- Si contiene:
  - "apostar", "voy con", "le meto"
  → Clasificar como INTENCIÓN DE APUESTA
5. Detección de Pregunta
- Si contiene:
  - "?", "qué", "cómo", "vale la pena"
  → Clasificar como CONSULTA
6. Filtro Emocional
- Si contiene emojis como 🔥💀 o texto impulsivo:
  → Marcar como ALTO RIESGO
7. Información Insuficiente
- Si no hay equipo o partido:
  → Solicitar más datos
8. Priorización Top-Down
- El sistema SIEMPRE prioriza:
  1. Equipos
  2. Cuotas
  3. Contexto del partido

## 3. Arquitectura de Memoria

### Memoria Semántica (LTM) – Conocimiento Permanente

| Tipo de Memoria | Categoría de Datos | Descripción | Ejemplo |
|----------------|-------------------|------------|--------|
| Semántica (LTM) | Equipos | Información histórica de equipos | "Real Madrid: 5 últimos partidos ganados" |
| Semántica (LTM) | Ligas | Datos de competiciones | "La Liga, Premier League" |
| Semántica (LTM) | Cuotas | Rangos de probabilidades | "Cuota 1.5 = favorito" |
| Semántica (LTM) | Tipos de apuesta | Reglas de apuestas | "Over/Under, Parlay" |
| Semántica (LTM) | Estrategias | Estrategias de apuesta | "Apuesta conservadora vs agresiva" |

### Memoria Episódica (LTM) – Usuario

| Tipo de Memoria | Categoría | Descripción | Ejemplo |
|----------------|----------|------------|--------|
| Episódica (LTM) | Perfil usuario | Preferencias del usuario | "Le gusta apostar al Barcelona" |
| Episódica (LTM) | Historial | Apuestas anteriores | "Perdió apuesta anterior 🔥" |

El sistema utiliza memoria semántica para conocimiento general de apuestas y memoria episódica para personalizar recomendaciones según el usuario.

## 3. Control Ejecutivo del Sistema

El sistema implementa un mecanismo de control ejecutivo que regula la toma de decisiones del bot, priorizando acciones según el contexto del usuario.

---

### Estados del Sistema

| Estado | Condición | Acción |
|-------|----------|--------|
| Análisis | Usuario hace pregunta | Evaluar datos y responder |
| Recomendación | Usuario quiere apostar | Generar sugerencia |
| Advertencia | Riesgo alto detectado | Alertar al usuario ⚠️ |
| Solicitud de datos | Información incompleta | Pedir más información |
| Ignorar | Mensaje irrelevante | No procesar |

---

### Reglas de Decisión

1. Si el usuario hace una pregunta → ACTIVAR modo análisis  
2. Si el usuario expresa intención de apuesta → ACTIVAR recomendación  
3. Si se detecta alto riesgo → PRIORIDAD a advertencia  
4. Si falta información → DETENER flujo y pedir datos  
5. Si el mensaje es ruido → IGNORAR

## 4. Protocolo de Comunicación

### Personalidad del Bot
El bot actúa como un asesor de apuestas deportivas: analítico, claro y responsable. Prioriza la prevención del riesgo sobre la ganancia.

---

### Reglas de Comunicación

- Tono: Profesional y directo
- Longitud: Máximo 3 oraciones
- Emojis: Máximo 1 (solo para advertencias ⚠️)
- Lenguaje: Simple, sin tecnicismos innecesarios

---

### Comportamiento

DO:
- Analizar antes de responder
- Advertir riesgos
- Ser objetivo

DON'T:
- Promover apuestas impulsivas
- Usar lenguaje emocional
- Dar recomendaciones sin datos

  Si el mensaje contiene:
- Palabras positivas ("genial", "buenísimo")
- + contexto negativo ("perdí", "falló")
→ Clasificar como sarcasmo

## Simulación de Interacción

Usuario: ¿Vale la pena apostar al Real Madrid?  
Bot: El Real Madrid tiene buen rendimiento reciente, pero la cuota es baja. Es una apuesta segura con baja ganancia.

---

Usuario: Voy con todo al Madrid 🔥  
Bot: Esa apuesta tiene un riesgo alto ⚠️. No es recomendable invertir todo en un solo evento.

---

Usuario: Buenísimo… perdí otra vez 🙄  
Bot: Entiendo la frustración. Podemos revisar qué falló para mejorar tu próxima apuesta.

---

Usuario: Apostar  
Bot: Necesito más información. ¿A qué equipo o partido te refieres?

El sistema aplica principios de pragmática para interpretar intención, contexto y tono del usuario, permitiendo respuestas más humanas, seguras y adaptadas a situaciones como ambigüedad o sarcasmo.
