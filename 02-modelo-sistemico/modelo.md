# Modelo Sistémico

## Frontera
- Dentro: interfaz de consulta, corpus documental autorizado, reglas de cobertura, buscador de turnos, generador de respuesta.
- Fuera: sistema oficial de turnos, decisiones administrativas, validación médica.
- Área gris: acceso automático a la historia clínica vs. información aportada por el paciente (impacta en privacidad y permisos).

## Contexto
Pacientes, sistema de gestión hospitalaria, normativa de cobertura, personal administrativo.

## Sinergia
El agente solo funciona si coordina reglas de cobertura, disponibilidad de turnos y validación humana. Ningún componente aislado puede dar la respuesta completa.

## Recursividad
El agente contiene subsistemas de consulta documental y validación de cobertura, pero también integra el sistema institucional de orientación y gestión de turnos.

## Justificación teórica (Lorenzón, caps. 7–9)

- **Capítulo 7 – Frontera y contexto**  
  La definición de frontera del agente (qué está dentro y qué queda fuera) se apoya en la idea de que todo sistema necesita delimitar su alcance para evitar confusiones. El área gris (historia clínica vs. datos aportados) ejemplifica cómo la frontera puede ser difusa y requiere decisiones explícitas.

- **Capítulo 8 – Sinergia y recursividad**  
  El agente no puede funcionar de manera aislada: necesita coordinar normativa, disponibilidad de turnos y validación humana. Esto refleja la sinergia entre subsistemas. Además, el modelo muestra recursividad porque el agente es parte de un sistema mayor (institución hospitalaria) y a su vez contiene subsistemas internos (consulta documental, validación de cobertura).

- **Capítulo 9 – Apertura, control y perturbaciones**  
  El agente se concibe como sistema abierto: recibe entradas (consultas, normativa, disponibilidad), las transforma y genera salidas (respuestas). El control se ejerce mediante feedback administrativo y corrección de errores. Las perturbaciones (cobertura desactualizada, fallas del sistema, cambios normativos) ilustran cómo factores externos pueden alterar el funcionamiento y deben ser previstos.