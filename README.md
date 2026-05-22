# Actividad Prompt Testing con Promptfoo y Gemini

Proyecto académico enfocado en la evaluación y validación de prompts utilizando Promptfoo y modelos de inteligencia artificial de Google Gemini.

## Objetivo

Diseñar y probar distintos prompts orientados a tutoría en programación y bases de datos, evaluando el comportamiento de la IA mediante assertions automáticas.

---

# Herramientas utilizadas

- Node.js
- npm
- Promptfoo
- Google Gemini API
- YAML
- Git y GitHub

---

# Configuración del entorno

## Verificación de versiones

Se verificaron las instalaciones con los siguientes comandos:

bash
node -v
npm -v
promptfoo --version

# Estructura del proyecto
Actividad_prompt_testing/
│

├── evidencias/

│   ├── foto 1 de prueba

│   ├── foto 2 de prueba

│   ├── foto 3 de prueba

│   └── foto de configuración

│

├── .env

├── .gitignore

├── promptfooconfig.yaml

└── README.md

# Configuración de seguridad

Se utilizó un archivo .gitignore para evitar subir información sensible al repositorio.

#### Contenido del .gitignore:
.env

node_modules

La API Key de Gemini se almacenó en el archivo .env.

Ejemplo:
GOOGLE_API_KEY=tu_api_key

### Modelo utilizado
google:gemini-2.5-flash-lite

Se utilizó la versión Lite debido a problemas de saturación y tiempos de espera en otros modelos durante las pruebas.

## Descripción de los prompts

Se diseñaron dos prompts con enfoques diferentes:

prompt 1:
Eres un tutor de programación y bases de datos estricto, formal y altamente técnico.
Cuando el estudiante te haga una pregunta, debes responder con la definición formal,
la sintaxis exacta, un bloque de código limpio y una breve explicación de los componentes clave.
Evita rodeos, saludos informales o metáforas.
Pregunta del estudiante: {{user_input}}

prompt 2:
Eres un tutor de desarrollo de software amigable, paciente y didáctico.
Tu misión es explicar conceptos complejos usando analogías de la vida real (como comida, deportes, o videojuegos) antes de mostrar el código.
Mantén un tono motivador y cierra tu respuesta explicando el código paso a paso de forma muy sencilla.
Mantén las respuestas concisas y evita explicaciones excesivamente largas.
Pregunta del estudiante: {{user_input}}

Se implementaron distintos tipos de assertions para validar las respuestas del modelo.

### icontains
Verifica que una palabra o concepto esté presente en la respuesta.

##### Ejemplo:
- type: icontains

  value: "FOR"


### javascript
Permite validar condiciones personalizadas utilizando JavaScript.

##### Ejemplo:
- type: javascript

  value: output.length < 5000

## Ejecución de pruebas

Las pruebas se ejecutaron mediante:

promptfoo eval --max-concurrency 1 --no-cache
Evidencias

En la carpeta evidencias/ se incluyen capturas de:

Configuración del entorno
Resultados PASS y FAIL
Ejecución de Promptfoo
Validación de prompts
Uso de assertions
Problemas encontrados

#### Durante el desarrollo se presentaron algunos inconvenientes:

-Saturación de la API de Gemini
-Errores 503 y timeouts
-Problemas de rate limit
-Bloqueo de una API Key por exposición accidental en GitHub
-Soluciones aplicadas
-Cambio de modelo a gemini-2.5-flash-lite
-Uso de .gitignore
-Regeneración de API Keys
-Reducción de concurrencia
-Simplificación de tests y assertions
-Aprendizajes obtenidos
-Configuración de APIs para IA
-Uso de Promptfoo para testing de prompts
-Estructura básica de YAML
-Uso de assertions automáticas
-Manejo de seguridad con .env y .gitignore
-Evaluación y validación de respuestas generadas por IA

#### Autores

Manuel Isaac Camaño Díaz
Maria Fernanda Quiñonez Moreno

Proyecto realizado para Campuslands.
