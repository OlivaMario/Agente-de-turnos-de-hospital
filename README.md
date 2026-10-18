# Agente de orientación de turnos hospitalarios

## 📑 Índice
- [Descripción](#-descripción)
- [Objetivo](#-objetivo)
- [Modelo sistémico preliminar](#-modelo-sistémico-preliminar)
- [Diagrama de contexto](#-diagrama-de-contexto)
- [Diagrama UML de casos de uso](#-diagrama-uml-de-casos-de-uso)
- [Flujos y control](#-flujos-sistema-abierto)
- [Preguntas de investigación](#-preguntas-de-investigación)
- [Integración](07-integracion/integracion.md)

## 📌 Descripción
Los pacientes necesitan reservar turnos médicos, pero la información sobre requisitos, horarios y coberturas está dispersa en distintos sistemas y documentos. Esto genera demoras, errores y consultas repetidas.

## 🎯 Objetivo
Orientar a los pacientes sobre turnos y requisitos, sin autorizar ni modificar agendas oficiales.  
El agente debe derivar a personal humano cuando la consulta exceda su alcance.

## 🧩 Modelo sistémico preliminar
- **Frontera:**  
  - Dentro: interfaz de consulta, corpus documental autorizado, reglas de cobertura, buscador de turnos, generador de respuesta.  
  - Fuera: sistema oficial de turnos, decisiones administrativas, validación médica.  
  - Área gris: acceso automático a la historia clínica vs. información aportada por el paciente (impacta en privacidad y permisos).  

- **Contexto:** pacientes, sistema de gestión hospitalaria, normativa de cobertura, personal administrativo.  

- **Sinergia:** el agente solo funciona si coordina reglas de cobertura, disponibilidad de turnos y validación humana.  

- **Recursividad:** el agente contiene subsistemas de consulta documental y validación de cobertura, pero también integra el sistema institucional de orientación y gestión de turnos. 

- **Perturbaciones:**  
  - Cobertura desactualizada  
  - Datos incompletos del paciente  
  - Caída del sistema hospitalario  
  - Cambios normativos inesperados 

## 🌐 Diagrama de contexto
![Diagrama de contexto](02-modelo-sistemico/contexto.png)

---

## 🎯 Diagrama UML de casos de uso
Muestra las finalidades del sistema y los roles que interactúan con él.

![Diagrama UML](02-modelo-sistemico/uml.png)

---
 
- **Flujos (sistema abierto):**  
  - Entrada: consulta del paciente, normativa vigente, disponibilidad de turnos.  
  - Conversión: interpretar la consulta, verificar requisitos, contrastar con normativa, generar orientación.  
  - Salida: respuesta fundamentada con requisitos, disponibilidad y fuentes.  
  - Feedback: validación administrativa, corrección de errores, registro de consultas.  

## 📊 Flujos y control
 ![Diagrama de flujos](03-flujos-y-control/diagrama.png)

## ❓ Preguntas de investigación
1. ¿Qué información puede usar el agente sin comprometer la privacidad del paciente?  
2. ¿Cómo se valida la salida para evitar errores críticos?  
3. ¿Qué ocurre cuando el agente no sabe o detecta contradicciones?  
4. ¿Qué perturbaciones externas afectan más el funcionamiento?  
5. ¿Qué decisiones requieren intervención humana obligatoria?  

---

## 📖 Justificación teórica (Lorenzón, caps. 7–9)
- **Cap. 7 – Frontera y contexto:** delimitar qué está dentro y fuera del sistema.  
- **Cap. 8 – Sinergia y recursividad:** el agente depende de coordinar normativa, turnos y validación humana.  
- **Cap. 9 – Apertura y control:** entradas, transformación, salidas y feedback con revisión administrativa.  

📂 Para más detalles, ver las carpetas:  
- `01-problema/` → descripción del problema, actores y evidencia.  
- `02-modelo-sistemico/` → frontera, contexto, sinergia y recursividad.  
- `03-flujos-y-control/` → entradas, conversión, salidas, feedback y perturbaciones.  
- `04-investigacion/` → fichas y preguntas abiertas. 