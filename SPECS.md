1. Introducción y Propósito Estratégico

AgentHub constituye el núcleo operativo para el despliegue de "Agent-Native Services", permitiendo la orquestación de sistemas agenticos en entornos de producción real y no simplemente en fases piloto. En el paradigma actual, la interfaz centralizada es crítica para gobernar la automatización de procesos core en funciones de Marketing, Operaciones, Customer Support, Legal, Sales, HR y Finanzas. Esta herramienta trasciende la gestión técnica para convertirse en un centro de control estratégico donde el Usuario Administrador actúa como un "Arquitecto de Automatización".

El sistema está diseñado para operar en sectores de alta exigencia como Retail (ej. Celio, Alinea), Industria (ej. Eramet) y Contabilidad, transformando métricas técnicas granulares —como Trace IDs, latencias de inferencia y Inference Costs— en decisiones de negocio accionables que validan el cumplimiento del ROI y la gobernanza empresarial. AgentHub es el motor de ejecución que sostiene los pilares de escalabilidad y cumplimiento normativo exigidos por las organizaciones modernas.

2. Stack Tecnológico y Restricciones de Arquitectura

Para cumplir con la promesa de Paatch de una implementación en 48 horas (desde el diagnóstico hasta el agente en producción), la arquitectura SHALL prescindir de procesos de compilación pesados y dependencias de frameworks complejos.

Componentes del Stack:

* HTML5 Semántico: Estructura base para accesibilidad nativa.
* Tailwind CSS (CDN): Estilización mediante clases de utilidad para permitir transiciones inmediatas de "diagnóstico a producción".
* JavaScript Vanilla (ES6+): Lógica de interacción pura para maximizar la compatibilidad con las más de 20 herramientas integradas (Claude, Gemini, Make, n8n, MuleRun).

Restricciones Estrictas:

* Prohibición de Frameworks: El uso de React, Vue o similares está estrictamente PROHIBIDO para evitar la sobrecarga de mantenimiento.
* Ausencia de Backend: El sistema operará exclusivamente en el lado del cliente. Los datos DEBEN estar hardcodeados en objetos JSON dentro de los scripts del cliente.
* Renderizado Local: Toda la lógica de manipulación del DOM se ejecutará mediante JavaScript nativo, garantizando una portabilidad absoluta.

3. Especificaciones Detalladas de la Interfaz

3.1. Dashboard de Control Principal (Métricas)

El sistema MUST presentar una visión consolidada de la salud del ecosistema para mitigar la fatiga cognitiva del operador.

* Métricas Core: Cuadrícula responsive 2×2 con tarjetas de: ROI (Acento verde), Actividad Semanal (Acento azul), Agentes Activos y Coste de Inferencia. Se utilizarán iconos de heroicons.
* Diseño: Tarjetas con elevación shadow-sm y bordes de acento semánticos.
* Visualización: Un contenedor de ancho completo con border-dashed SHALL representar el gráfico de actividad, centralizando la observabilidad del flujo de trabajo.

3.2. Hub de Gestión de Agentes (Listado)

Basado en los principios de UX de Stéphanie Walter para datos complejos, la tabla SHALL facilitar cuatro tareas mayores: Encontrar registros, Comparar datos, Ver/Editar y Tomar acción.

* Tabla de Datos: Listado de agentes (Sales, HR, Finance, Legal) con badges de status (Verde/Rojo).
* Acciones Rápidas: Las filas contarán con un efecto hover que revele un "Action Dropdown" para pausar o eliminar agentes.
* LLM Identification: Se utilizarán avatares circulares para indicar el motor de razonamiento (Claude, Gemini).

3.3. Monitorización y Logs (Observabilidad)

La trazabilidad es el pilar de la confianza en sistemas autónomos. El sistema MUST implementar los 8 niveles de severidad del estándar de industria:

1. Emergency/Fatal: Rojo Intenso.
2. Alert: Rojo.
3. Critical: Rojo suave.
4. Error: Naranja/Rojo.
5. Warning: Amarillo (Comportamiento inesperado pero recuperable).
6. Notice: Azul claro (Eventos significativos fuera de rutina).
7. Informational: Gris oscuro (Actividad normal del sistema).
8. Debug: Gris claro (Detalles de ejecución).

* Detalle Técnico: Cada log SHALL permitir la apertura de un panel lateral que exponga el JSON con el Trace ID y la Correlation ID.

3.4. Orquestación y Workflows (Pipeline)

Visualización del "Agentic Pipeline" donde la salida de un paso alimenta al siguiente.

* Flujo: Lista vertical conectada por bordes CSS (border-l-2).
* Tool Calling: Badges específicos para invocaciones externas a MuleRun, Slack, Make o n8n.
* Human-in-the-loop: Un interruptor (Toggle) MUST permitir activar la validación humana en pasos críticos de decisión, asegurando la gobernanza en procesos de alta sensibilidad.

3.5. Directorio de Builders y Expertos

Acceso a la red de 2000+ expertos verificados.

* Grid de Perfiles: Tarjetas con especialidades (Automation, Architecture).
* Pureza Funcional: La lista de skills SHALL implementarse mediante el elemento <details> nativo. Esto garantiza interactividad con zero-JS overhead, manteniendo la ligereza del DOM.

3.6. Configuración y Gobernanza

* Controles: Toggles para cumplimiento de GDPR y trazabilidad de auditoría.
* Modo Oscuro: Selector que aplique la clase .dark al elemento raíz (<html>) según las directrices de Tailwind CSS.
* Límites de Gasto: Formulario de validación nativa para establecer topes de Inference Cost.

4. Inventario de Componentes UI Reutilizables

La consistencia visual SHALL ser garantizada mediante el uso estricto de los siguientes componentes base:

* Sidebar de Navegación: w-64 fixed h-full bg-slate-50 border-r border-slate-200 dark:bg-slate-900.
* Tarjeta de Métrica: bg-white dark:bg-slate-800 p-4 rounded-lg shadow-sm border-l-4.
* Modal Nativo: Implementado vía <dialog> con backdrop:bg-gray-900/50 backdrop-blur-sm p-6 rounded-xl.
* Action Dropdown: absolute right-0 mt-2 w-48 rounded-md shadow-lg bg-white ring-1 ring-black ring-opacity-5 focus:outline-none.
* Badge de Estado: px-2 py-1 rounded-full text-xs font-medium uppercase tracking-wider.
* Toggle Switch: relative inline-flex h-6 w-11 items-center rounded-full transition-colors focus:outline-none.

5. Criterios de Aceptación y Validación

Para que el prototipo se considere "Production-Grade", SHALL cumplir los siguientes criterios:

1. Gobernanza de Interacción: El Dropdown de acciones MUST conmutar su visibilidad mediante lógica de JS Vanilla (element.classList.toggle('hidden')).
2. Accesibilidad Nativa (Modal): El componente <dialog> MUST gestionar automáticamente el focus trapping y soportar el cierre nativo mediante la tecla ESC.
3. Eficiencia de Interfaz: El elemento colapsable de skills MUST ser funcional sin necesidad de scripts (uso de <details>/<summary>).
4. Lógica de Modo Oscuro: La conmutación de tema MUST inyectar/remover la clase .dark en el nodo raíz del documento para una propagación instantánea de estilos.
5. Validación de Datos: Los inputs de límites de gasto MUST incluir validaciones de tipo y rango mediante los atributos nativos de HTML5 y validación secundaria en JavaScript.

Este documento técnico define el estándar de excelencia para la ejecución de AgentHub, asegurando que la simplicidad del stack no comprometa la robustez de un sistema de grado empresarial.
