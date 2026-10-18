## Estructura
- **Componentes principales:**
  - Interfaz de consulta (paciente).
  - Coordinación de la consulta.
  - Recuperación documental (normativa de cobertura, disponibilidad de turnos).
  - Verificación de requisitos.
  - Generador de respuesta.
  - Registro y revisión administrativa.

- **Relaciones:**
  - Recuperación → Verificación: transmite regla de cobertura, fuente y vigencia.
  - Verificación → Coordinación: devuelve estado (cumple requisitos, incompleto o contradictorio).
  - Coordinación → Respuesta: decide orientar, pedir datos o derivar.

## Organización
- Consultar solo datos autorizados (cobertura, turnos disponibles).
- Detener la conclusión ante contradicciones.
- Explicar siempre las fuentes utilizadas.
- Reservar excepciones a personal administrativo humano.

## Control
- **Ciclo básico aplicado:**
  - Actividad controlada → elaborar orientación de turnos.
  - Sensor → revisión de normativa vigente y disponibilidad real.
  - Comparador → contraste con criterios de cobertura y requisitos.
  - Decisor → coordinación automática o derivación a humano.
  - Efector → respuesta al paciente o derivación administrativa.

- **Salidas posibles:**
  - Orientar con requisitos claros.
  - Pedir datos faltantes.
  - Informar indisponibilidad del sistema.
  - Derivar a personal administrativo.

## Perturbaciones
- Cobertura desactualizada.
- Datos incompletos del paciente.
- Caída del sistema hospitalario.
- Cambios normativos inesperados.

## UML · Casos de uso iniciales
- **Actores:** Paciente, Personal administrativo, Sistema hospitalario, Repositorio normativo.
- **Casos de uso:** Obtener orientación, Solicitar revisión, Registrar revisión, Mantener criterios.