# Efecto Post-Dividendo

Ajuste de Precio vs Valor del Dividendo

Este proyecto implementa una consulta SQL que analiza el comportamiento del precio en la fecha ex-dividendo, comparando la caída efectiva del precio con el valor del dividendo pagado.

La señal busca detectar ineficiencias de ajuste, donde el mercado reacciona de más (o de menos) frente a un evento teóricamente neutral.

## 🧠Idea central

En teoría financiera:
- el precio debería caer exactamente el valor del dividendo
- el día ex-dividendo no debería generar alpha

En la práctica:
- hay fricciones
- hay impuestos
- hay psicología y flujos

La diferencia entre la caída real y el dividendo revela comportamiento no eficiente.

## 🎯Valor de negocio

Identifica oportunidades de arbitraje blando

Útil para:
- estrategias de dividend capture
- análisis de microestructura
- evaluación de eficiencia de mercado

Permite separar ajuste mecánico de reacción emocional

## 🗄️Estructura de datos esperada

- eventos_corporativos
- campo	descripción
- ticker_id	Identificador del activo
- fecha	Fecha del evento
- tipo_evento	Tipo de evento (Dividendo)
- valor	Valor del dividendo
- precios_diarios
- campo	descripción
- ticker_id	Identificador
- fecha	Fecha
- open	Precio de apertura
- close	Precio de cierre

## ⚙️Lógica de la consulta

Identifica eventos de dividendo

Obtiene:
- cierre del día previo
- apertura del día ex-dividendo

Calcula:
- caída real del precio
- diferencia entre caída y dividendo
- Ordena por mayor desviación positiva

## 🔎Interpretación de resultados

Diferencia positiva alta:
- el precio cayó más que el dividendo
- posible sobre-reacción

Diferencia negativa:
- ajuste incompleto
- demanda residual o fricción fiscal

## 🚀Posibles extensiones

- Analizar reversión post-evento
- Ajustar por impuestos y moneda
- Comparar entre mercados
- Integrar volumen en el día ex-dividendo

## 📝Notas finales

- No es una señal direccional inmediata
- Es una herramienta de diagnóstico de eficiencia
- Ideal para estudios de eventos corporativos

## 👤Autora
Flavia Hepp Proyecto de SQL aplicó un análisis de riesgo basado en eventos.
