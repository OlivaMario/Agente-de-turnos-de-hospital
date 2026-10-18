### Actores externos
- **Paciente:** solicita orientación sobre turnos y cobertura.
- **Personal administrativo:** revisa derivaciones y mantiene criterios operativos.
- **Sistema hospitalario:** provee disponibilidad de turnos y estado de agenda.
- **Repositorio normativo:** ofrece reglas de cobertura y requisitos vigentes.

### Casos de uso principales
1. **CU-01 · Obtener orientación**
   - **Actor principal:** Paciente.
   - **Actores de apoyo:** Sistema hospitalario y repositorio normativo.
   - **Disparador:** El paciente consulta requisitos y disponibilidad.
   - **Precondición:** Acceso autorizado a datos de cobertura y agenda.
   - **Flujo básico:**
     1. El paciente envía consulta con especialidad y cobertura.
     2. El servicio solicita disponibilidad y normativa vigente.
     3. Verifica requisitos y genera orientación.
     4. Devuelve respuesta clara con fuentes y limitaciones.
   - **Resultado esperado:** Orientación verificable sin modificar registros institucionales.

2. **CU-02 · Solicitar revisión**
   - **Actor principal:** Paciente.
   - **Actor de apoyo:** Personal administrativo.
   - **Disparador:** El paciente detecta error o falta de información.
   - **Flujo básico:** El servicio registra la solicitud y la envía a revisión humana.

3. **CU-03 · Registrar revisión**
   - **Actor principal:** Personal administrativo.
   - **Flujo básico:** Recibe la derivación, analiza el caso y devuelve corrección o criterio aprobado.

4. **CU-04 · Mantener criterios**
   - **Actor principal:** Personal administrativo.
   - **Flujo básico:** Actualiza reglas operativas y criterios de respuesta del servicio.

### Alcance del sistema
El sistema **no autoriza inscripciones ni modifica agendas**.  
Su función es **orientar, verificar y derivar** dentro de límites explícitos.

### Relaciones
- Paciente participa en **Obtener orientación** y **Solicitar revisión**.  
- Personal administrativo participa en **Registrar revisión** y **Mantener criterios**.  
- Sistema hospitalario y repositorio normativo apoyan **Obtener orientación**.