# DiagnOIA  
Sistema Clínico Inteligente basado en Reglas, Grafos y Modelos de Lenguaje

DiagnOIA es un asistente clínico académico desarrollado como parte del Proyecto Integrador.  
Combina un grafo semántico en **Neo4j**, un motor de reglas difusas, una interfaz en **Streamlit** y un LLM local (**Ollama**) para responder consultas clínicas, listar pacientes y priorizar casos según riesgo y urgencia.

---

## Características principales

### Base de conocimiento en Neo4j
- Representación con **FrameClass**, **FrameInstance**, **Slots**, **Measurement** y **SLOT_VALUE**.
- Enfermedades, síntomas, factores personales y antecedentes clínicos.
- Activación automática de reglas diagnósticas:
  - **Gripe**
  - **COVID-19**
  - **Neumonía**
- Cálculo de:
  - Enfermedad sugerida  
  - Nivel de riesgo  
  - Prioridad de atención  
  - Acción recomendada  

### Motor de Reglas  
Incluye reglas con múltiples condiciones (temperatura, tos, tabaquismo, edad, vacunación) usando pesos y score acumulado para activar diagnósticos.

### Interfaz Streamlit  
Permite:
- Consultar el grafo clínico mediante lenguaje natural.
- Preguntar por síntomas, patologías, riesgo y prioridad.
- Ver **todos los pacientes ordenados por prioridad clínica** (Urgente → Moderada → Baja).
- Crear pacientes (opcional, si se activa el módulo).
- Chat integrado con memoria por sesión.

### LLM local (Ollama)
Usa **llama3.2:3b** (modelo liviano que no rompe RAM) para resumir, interpretar y devolver texto clínico.

---

## Tecnologías utilizadas

- **Python 3.8+**
- **Streamlit**
- **Neo4j AuraDB**
- **Cypher**
- **Ollama (llama3.2:3b)**
- **LangChain Community**

---

## Instalación

### 1. Clonar el repositorio
```bash
git clone https://github.com/valentina-lencioni/diagnoia.git
cd diagnoia
