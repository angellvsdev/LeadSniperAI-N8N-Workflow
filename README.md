# 🎯 Lead Sniper AI: Autonomous Prospecting Engine
Lead Sniper AI es un motor de prospección autónomo diseñado para identificar oportunidades de negocio en tiempo real dentro de comunidades tecnológicas. Utiliza un enfoque de análisis semántico impulsado por IA para detectar "puntos de dolor" técnicos y generar propuestas de valor inmediatas.

# 🚀 Descripción General
A diferencia de los scrapers tradicionales basados en palabras clave, este flujo de trabajo orquestado en n8n utiliza modelos de lenguaje de gran escala (LLM) para entender la intención y la urgencia detrás de cada publicación en foros como Hacker News o Reddit.

El sistema monitoriza fuentes RSS, procesa la información a través de Groq (Llama 3) para una inferencia de baja latencia y entrega leads calificados directamente a un bot de Telegram con un pitch personalizado listo para ser enviado.

# ✨ Características Principales
- Monitoreo Multicanal: Integración con feeds RSS de comunidades de alta señal (Hacker News, Reddit, etc.).
- Cerebro de IA (Groq + Llama 3): Análisis profundo de texto para filtrar ruido y detectar necesidades reales de infraestructura, automatización o desarrollo.
- Lead Scoring Dinámico: Clasificación automática por nivel de urgencia (1-10) y resumen del problema principal.
- Generación de Pitch Contextual: Redacción automática de mensajes de contacto adaptados al tono y estilo de la empresa.
- Arquitectura de Microservicios: Desplegado mediante Docker para garantizar portabilidad y escalabilidad.

🛠️ Stack Técnico
- Orquestador: n8n.
- Motor de IA: Groq API (Llama 3-70b).
- Notificaciones: Telegram Bot API.
- Infraestructura: Docker & Docker Compose.
- Hardware de Desarrollo: Dell Latitude 7400.

📦 Instalación y Despliegue
- Requisitos previos
- Docker y Docker Compose instalados.
- API Keys de Groq y Telegram Bot Token.

Ejecución con Docker Bash

```
  docker run -d \
  --name n8n_sniper \
  -p 5678:5678 \
  -v n8n_data:/home/node/.n8n \
  docker.n8n.io/n8nio/n8n
```

# 🧠 Lógica del Workflow
- Trigger: Nodo RSS consulta nuevas entradas cada 15 minutos.
- Brain: El nodo de IA evalúa el contenido. Si el parámetro is_lead es true, el flujo continúa.
- Filter: Un nodo condicional valida la respuesta del LLM.
- Action: Envío de notificación enriquecida a Telegram.

--- 
Desarrollado con mentalidad de solucionador de problemas por Angel Leonardo Vera Soto.
Ingeniero de Sistemas y Software
