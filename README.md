# LLévate a Watson a casa
Una forma sencilla de conectar los servicios de conversación de Watson Assistant, y Google Home.

## Requisitos
Una cuenta en ibm cloud  [bluemix](https://console.bluemix.net) , o en breve [ibm cloud](https://console.cloud.ibm.com)

Una cuenta de Google Actions [actions](https://developers.google.com/actions/)

## Pasos

### Preparación

En la cuenta de IBM Cloud instanciamos
* Una cloud foundry App node-RED Starter  [nodered](https://console.bluemix.net/catalog/starters/node-red-starter)
* Un servicio Watson Assistant [Assistant](https://console.bluemix.net/catalog/services/conversation)

Para las acciones
* Bajarnos el CLI de [gactions](https://developers.google.com/actions/tools/gactions-cli)
     * desde una shell  ./gactions -V y vemos que está bien instalado

### Creamos la acción

* Entramos en actions [https://console.actions.google.com/](https://console.actions.google.com/)
* Add/Import Project
     * Atento al idioma y la región
* Scroll hacia abajo y seleccionamos Actions SDK
     * Copiamos lo que nos propone gactions update --action_package PACKAGE_NAME --project asistente-de-casa
     * Esta linea la usaremos luego para configurar la acción, llamando con el fichero json
     * gactions update --action_package actionasistentedecasa.json --project asistente-de-casa
      * en este fichero


