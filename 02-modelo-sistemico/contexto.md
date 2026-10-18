## Diagrama de contexto · Agente de turnos hospitalarios

### Actores externos
- **Paciente:** consulta requisitos y disponibilidad de turnos.
- **Sistema hospitalario oficial:** provee disponibilidad de turnos y estado de agenda.
- **Repositorio normativo:** contiene reglas de cobertura y requisitos vigentes.
- **Personal administrativo:** recibe derivaciones y revisiones de casos.

### Sistema delimitado
**Servicio de orientación de turnos hospitalarios**  
Responsabilidad: interpretar la consulta del paciente, verificar requisitos y cobertura, y devolver orientación o derivar.

### Flujos de información
- **F1 · Consulta**  
  Paciente → Servicio  
  Datos mínimos: especialidad, fecha solicitada, cobertura.

- **F2 · Orientación**  
  Servicio → Paciente  
  Requisitos, horarios disponibles, fuentes utilizadas, límites de la respuesta.

- **F3 · Solicitud de turnos**  
  Servicio → Sistema hospitalario  
  Consulta de disponibilidad (solo lectura, sin modificar agenda).

- **F4 · Disponibilidad**  
  Sistema hospitalario → Servicio  
  Turnos disponibles, estado de agenda, señal de indisponibilidad.

- **F5 · Búsqueda normativa**  
  Servicio → Repositorio normativo  
  Consulta de reglas de cobertura y requisitos vigentes.

- **F6 · Documentos normativos**  
  Repositorio normativo → Servicio  
  Normas aplicables con metadatos de vigencia.

- **F7 · Derivación / revisión**  
  Servicio → Personal administrativo  
  Motivo, síntesis del caso, evidencia y datos mínimos.

- **F8 · Corrección / criterio**  
  Personal administrativo → Servicio  
  Devolución fundada, criterios aprobados, estado de revisión.

### Supuestos
- El servicio solo accede a datos autorizados en modo lectura.  
- No modifica agendas ni autoriza inscripciones.  
- Las derivaciones siempre requieren confirmación humana.  