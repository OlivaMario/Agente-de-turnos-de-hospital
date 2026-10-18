## 🎯 Objetivo
Representar el agente de turnos hospitalarios mediante diagramas de contexto y casos de uso UML, y especificar un caso con alternativas.

---

## 📌 Diagrama de contexto
**Sistema central:** Agente de turnos hospitalarios.  
**Entidades externas:**  
- Paciente → envía solicitud de turno, datos de cobertura.  
- Administrativo → recibe alertas, confirma excepciones.  
- Sistema de cobertura → devuelve estado de afiliación.  
- Hospital (agenda oficial) → recibe derivación, confirma turno.  

**Intercambios principales:**  
- Paciente ↔ Agente: solicitud de turno / orientación.  
- Agente ↔ Sistema de cobertura: consulta / estado de cobertura.  
- Agente ↔ Administrativo: alerta / revisión.  
- Agente ↔ Hospital: derivación / confirmación de turno.

![Diagrama de contexto](06-diagramas-uml/contexto.png)

---

## 📌 Diagrama de casos de uso UML
**Actores:** Paciente, Administrativo, Sistema de cobertura, Hospital.  
**Casos de uso:**  
- CU-01 · Solicitar turno.  
- CU-02 · Verificar cobertura.  
- CU-03 · Orientar sobre requisitos.  
- CU-04 · Registrar alerta / excepción.  

![Diagrama UML](06-diagramas-uml/uml.png)

---

## 📌 Especificación de caso de uso
**CU-01 · Solicitar turno**

- **Objetivo:** que el paciente reciba orientación sobre si puede acceder a un turno de cardiología.  
- **Alcance:** Agente de turnos hospitalarios.  
- **Actor principal:** Paciente.  
- **Apoyos:** Sistema de cobertura, Administrativo.  
- **Disparador:** paciente solicita turno.  
- **Precondición:** paciente declara plan y cobertura.  
- **Garantía mínima:** el sistema informa si falta información o si la cobertura no está activa.  
- **Resultado de éxito:** orientación presentada y derivación al hospital si corresponde.  

**Flujo principal:**  
1. Paciente solicita turno de cardiología.  
2. Agente pide datos de plan y cobertura.  
3. Agente consulta estado de cobertura.  
4. Si está activa, informa que cumple requisito y deriva al hospital.  
5. Hospital confirma turno.  

**Alternativas y excepciones:**  
- 2a: datos incompletos → pide aclaración.  
- 3a: cobertura no activa → informa que no cumple requisito.  
- 3b: excepción declarada → recomienda consulta con administrativo.  
- 4a: sistema de cobertura no responde → informa indisponibilidad.  

---

## 📌 Decisiones y dudas
- **Decisión 1:** incluir al hospital como entidad externa, porque la autorización formal está fuera del agente.  
- **Decisión 2:** separar “Verificar cobertura” como caso de uso independiente, para que pueda repetirse en otros escenarios.  
- **Decisión 3:** representar al administrativo como actor de apoyo, no como parte del sistema.  
- **Duda pendiente:** ¿el agente debería registrar automáticamente cada interacción en una base externa o alcanza con conservar datos declarados en memoria temporal?

---

## 📌 Comparación con el prototipo
El prototipo de la clase 14 solo orienta sobre cobertura declarada y no consulta sistemas externos.  
El diagrama de contexto y casos de uso muestran funciones más amplias (consulta al sistema de cobertura, derivación al hospital, alertas al administrativo).  
Esto evidencia la diferencia entre el modelo completo y el alcance reducido del prototipo.