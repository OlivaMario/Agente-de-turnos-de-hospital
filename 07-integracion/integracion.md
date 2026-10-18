9 de octubre · Integración
Mi agente ayuda a:  
Orientar a pacientes que solicitan turnos hospitalarios, verificando cobertura y derivando al hospital o al administrativo según corresponda.

El caso de uso que revisé es:  
CU‑01 · Solicitar turno de cardiología.

La prueba mostró que:

En el recorrido normal, el agente verificó cobertura activa y derivó correctamente al hospital.

En el recorrido alternativo, pidió datos de cobertura y, al faltar, recomendó consulta con administrativo.

En la prueba de contradicción, señaló la diferencia y no eligió sin respaldo, cumpliendo la regla.

La mejora que hice fue:  
Completar la coherencia entre reglas, recorridos y pruebas, asegurando que cada paso esté representado en los diagramas y validado en las simulaciones.

Para el final me falta:  
Definir si el agente debe registrar automáticamente cada interacción en una base externa o si alcanza con conservar datos en memoria temporal. También completar la implementación de un prototipo funcional.

Cierre:  
Decisión: mantener al hospital como entidad externa, porque la autorización formal está fuera del agente. Esta decisión se sostiene en la prueba normal, donde el hospital confirma el turno después de la derivación.