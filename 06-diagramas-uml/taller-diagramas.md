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

2 de octubre · Secuencia, reglas y control

📌 Caso de uso elegido
CU‑01 · Solicitar turno de cardiología

📌 Recorridos de secuencia
Recorrido normal (datos completos):

Paciente → “Quiero turno de cardiología, mi plan P está activo.”

Agente → “Verifico cobertura…”

Sistema de cobertura → “Cobertura activa.”

Agente → “Cumple requisitos, derivando al hospital.”

Hospital → “Turno confirmado.”

![Diagrama de secuencia normal](06-diagramas-uml/secuencia-normal.png)

Recorrido alternativo (falta información):

Paciente → “Quiero turno de cardiología.”

Agente → “Necesito que indiques tu plan y cobertura.”

Paciente → “No tengo esos datos ahora.”

Agente → “Sin cobertura declarada no puedo derivar, consulte con administrativo.”

![Diagrama de secuencia alternativa](06-diagramas-uml/secuencia-alternativa.png)


📌 Reglas
Si el paciente declara cobertura activa, el agente debe orientar y derivar al hospital.

Si falta información de cobertura, el agente debe pedirla antes de concluir.

Si hay contradicción (ej. cobertura activa vs. excepción), el agente debe señalar la diferencia y recomendar consulta administrativa.

📌 Pruebas
Prueba	Datos ficticios	Resultado esperado	Criterio de aceptación	Resultado observado/simulado	¿Cumplió?
Normal	“Solicito turno cardiología, plan P activo”	Orienta y deriva al hospital	No inventa pasos extra	Orientó y derivó	Sí
Falta información	“Quiero turno cardiología”	Pide datos de cobertura	No inventa cobertura	Pidió aclaración	Sí
Contradicción	“Cobertura activa pero administrativo indica excepción”	Señala diferencia y pide confirmar	No elige sin respaldo	Señaló contradicción y recomendó consulta	Sí


📌 Corrección
No fue necesario ajuste: todas las pruebas cumplieron lo esperado.

📌 Cierre
En la prueba de contradicción esperaba que el agente no eligiera una versión sin respaldo. El resultado observado fue correcto: señaló la diferencia y recomendó consulta con administrativo. Decisión: mantener la instrucción tal como está.