# Ficha de analisis

## 1. Nombre del space

**Nombre:** WAMU V2 - Wan 2.2 I2V (14B)

**Enlace:** https://huggingface.co/spaces/r3gm/wan2-2-fp8da-aoti-preview

## 2. ¿Qué hace el agente?

Genera un video a partir de una imagen cargada dado un prompt que describa que se quiere ver en el video

## 3. Análisis PEAS

**Performance** tiempo, fluidez, calidad del video, realismo del video, fidelidad al prompt, coherencia

**Environment** El usuario

**Actuators** Generacion de fotogramas de video

**Sensors** Texto del prompt del usuario, imagenes de entrada, parámetros de configuración 

## 4. Clasificación del entorno

**Observable parcial**

Justificacion: El agente percibe el prompt y la imagen de entrada, no tiene acceso completo a lo que el usuario realmente quiere

**No determinista** 

Justificacion: Con el mismo prompt se pueden obtener videos distintos ya que cada video se genera en una semilla aleatorias

**Episódico** 

Justificacion: Cada generacion de video es un episodio independiente, no tiene memoria de otras generaciones de video

**Estático**

Justificacion: El prompt y la imagen no cambia mientras el agente genera el video

**No Discreto / Continuo**

Justificacion: El espacio de los posibles prompts es continuo

**Conocido**

Justificacion: Las reglas del proceso son conocidas y definidas por el diseño del modelo

## 5. ¿Qué tipo de programa de agente creen que es?

Agente basado en objetivos: El agente tiene un objetivo explícito en cada generación el cual es producir un video que coincida con el prompt y coherente con la imagen de entrada. Evalúa en en cada paso que tan cerca está el resultado parcial de ese objetivo y ajusta su salida.

# Reto adicional

1.  **Totalmente observable, determinista y episódico.**

   NLLB Translator: Puede clasificarse como totalmente observable, determinista y episódico porque cada traduccion depende unicamente del texto de entrada visible, sin necesidad de inferir informacion, dado el mismo texto produce la misma salida y cada solicitud es un evento aislado

2.  **Parcialmente observable, estocástico y secuencial.**

   Chatbot conversacional: puede clasificarse como Parcialmente observable, estocástico y secuencial porque el modelo solo accede al texto escrito por el usuario sin conocer su intencion real ni el contexto externo, la misma pregunta puede generar respuestas distintas en cada ejecucion, y cada respuesta depende del historial de la conversacion
