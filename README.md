# PersonalAgent Project

## 📜 Descripción del Proyecto

PersonalAgent es un Agente Personal desarrollado en *N8N* que utiliza automatizaciones y Agentes de IA. La arquitectura del sistema se basa en un enfoque de múltiples Agentes, donde un agente principal actúa como orquestador, delegando tareas a agentes más especializados, hasta llegar a los agentes o WorkFlows que interactúan directamente con las herramientas necesarias.

El sistema está compuesto por tres niveles de agentes:

1. *Agente Principal y Orquestador*: Este agente recibe directamente las peticiones del usuario, interpreta sus necesidades y delega las tareas necesarias para su ejecución.
2. *Agentes Divididos por Áreas*: Se encargan de tareas específicas en áreas como Comunicación, Calendario/Eventos, Investigación y RAG, y Asistencia (to-do lists, notas rápidas y recordatorios).
3. *Agentes Interactivos*: Estos agentes interactúan directamente con herramientas como Gmail, Google Calendar, bases de datos y motores de búsqueda en Internet.

### 🌳 Árbol de Agentes


└── PersonalAgent
    ├── ComunicationalAgent
    │   └── GmailAgent
    ├── CalendarEvents_Agent
    │   └── GoogleCalendarAgent
    ├── Research_RAG
    │   ├── ResearchAgent
    │   └── RAGAgent
    └── AsistanceAgent (todo-lists, notes, reminders)
        ├── TodoListsAndNoteTakingAgent
        └── RemindersAgent


Esta arquitectura permite la escalabilidad y el crecimiento del sistema, mitigando la posibilidad de errores. Los agentes son muy efectivos realizando una tarea, pero son poco efectivos realizando múltiples a la vez. Al ir filtrando y especificando la tarea, se reduce el riesgo de error. También se da la posibilidad de agregar agentes de manera sencilla. Por ejemplo, el agente comunicacional solo delega tareas a GmailAgent por el momento, pero en el futuro se podrán añadir herramientas de mensajería como WhatsApp o Slack, entre muchas más. Lo mismo se aplica a los demás agentes.

Además, el sistema cuenta con herramientas sencillas pero cruciales, como una lista de contactos del usuario (almacenada en Google Sheets) y memoria de chat, que personaliza la experiencia del usuario y mejora con el tiempo.

## 📱 Interacción del Usuario

La comunicación entre el usuario y el agente se realiza a través de *WhatsApp, utilizando la **Evolution API* y un enrutador que determina qué WorkFlow (WF) llamar según el número de teléfono entrante. De esta manera, un único número de teléfono del agente permite la comunicación con múltiples usuarios. Este enrutador también permite la personalización de los WorkFlows, lo que puede dirigir la ejecución a los WFs específicos en los que el usuario tiene credenciales para los servicios utilizados y su propia memoria de chat.

El agente es capaz de procesar texto, audio, imágenes y documentos, proporcionando una experiencia más completa que aumenta el dinamismo y la productividad del usuario.

Además, el proyecto incluye un WorkFlow para la creación automatizada de Agentes a partir de credenciales. Este proceso (aún en desarrollo) busca facilitar la automatización de agentes utilizando las credenciales del usuario. En el flujo de uso, el usuario adquiere el producto en una página web o aplicación, acepta el acceso a los servicios de Google utilizados e ingresa su información, lo que permite la creación de todos los WFs necesarios mediante OAuth2.

Se eligio N8N como herramienta principal por su rapido desarrollo y facilidad de crear sistemas, pudiendo validar la idea en menos tiempo. Teniendo la posibilidad de escar utilizando frameworks mas especializados, robustos y escalables como LangChain por ejemplo.

## 🚀 Tecnologías Utilizadas

- *N8N*
- *Supabase*
- *Google APIs* (Gmail, Calendar, Sheets, Drive)
- *OAuth2*
- *Redis*
- *LLMs*
- *APIs / WebHooks*
- *JavaScript*

