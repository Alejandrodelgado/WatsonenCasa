# LLévate a Watson a casa
Una forma sencilla de conectar los servicios de conversación de Watson Assistant, y Google Home.

## Requisitos
Una cuenta en ibm cloud   [ibm cloud](https://console.cloud.ibm.com)

Una cuenta de Google Actions [actions](https://developers.google.com/actions/)

## Pasos

### Preparación

En la cuenta de IBM Cloud instanciamos
* Una cloud foundry App node-RED Starter  [nodered](https://console.bluemix.net/catalog/starters/node-red-starter)
* Un servicio Watson Assistant [Assistant](https://console.bluemix.net/catalog/services/conversation)

Para las acciones
* Bajarnos el CLI de [gactions](https://developers.google.com/actions/tools/gactions-cli)
     * En MacOs hacemos -> uname +x gactions
     * desde una shell  ./gactions -V y vemos que está bien instalado

### Creamos la acción

* Entramos en actions [https://console.actions.google.com/](https://console.actions.google.com/)
* Add/Import Project
     * Atento al idioma y la región
* Scroll hacia abajo y seleccionamos Actions SDK
     * Copiamos la linea que nos propone 
     * Esta linea la usaremos luego para configurar la acción, llamando con el fichero json
     * Mediante linea de comando podemos hacer gactions init que nos crea un fichero json como plantilla 
     * gactions update --action_package actionasistentedecasa.json --project asistente-de-casa-xxxx
         * en este fichero json, se especifica la url que se va a invocar
         * atentos si tenemos un error de credenciales, existe en el directorio desde el que ejecutamos un fichero oculto llamado creds.data
         * atentos a las mayúsculas y minúsculas en los nombres de la acción
               Your app for the Assistant for project asistente-de-casa-4cff4 was successfully updated with your actions. Visit the Actions on Google console to finish registering your app and submit it for review at https://console.actions.google.com/project/asistente-de-casa-4cff4/overview
* Entramos en la acción con la url de overview
     * En Quick setup especificar la frase de activación Asistente de casa
     * En invocación incluir la frase de invocación.
     * En el menu simulator especificar el idioma, y probar la frase de activación

### Creamos el asistente

* Dentro de la consola de IBM Cloud, elegir el servicio Watson Assistant, aprovechar y copiar las credenciales (API)
* En la opción de menu, elegir launch
* En la pestaña de skill , crear uno, importando el fichero de conversación json (basado en el de Ana López)
* Crear un asistente en la pestaña para copiar el workspaceID

### Creamos el interface

* Dentro del nodered, importar el flujo con el json (basado en el de Jaume Miralles)
* Copiar en el nodo de Assistant, la credencial (API) y el workspaceID


 
