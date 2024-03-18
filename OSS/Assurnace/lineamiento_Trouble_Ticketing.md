<!--<style>
img{
    border: 1px solid #ddd;
    border-radius: 4px;
    padding: 15px;
    width: 200px;
  }
</style>-->

# Lineamientos de Trouble Ticketing

## Control de versiones

| Versión | Fecha      | Responsable | Comentarios                                                                             |
| ------- | ---------- | ----------- | --------------------------------------------------------------------------------------- |
| v0.1     | 02/11/2022 | Arquitectura de Soluciones & Empresarial      | Versión Inicial                      |

## Índice


- [Lineamientos de Trouble Ticketing](#lineamientos-de-trouble-ticketing)
  - [Control de versiones](#control-de-versiones)
  - [Índice](#índice)
  - [Introducción](#introducción)
  - [Alcance](#alcance)
  - [Audiencia](#audiencia)
  - [Ubicación en los Frameworks de Referencia del TM Forum](#ubicación-en-los-frameworks-de-referencia-del-tm-forum)
    - [Framework de Aplicaciones TAM](#framework-de-aplicaciones-tam)
  - [Macroprocesos TM Forum](#macroprocesos-tm-forum)
    - [Centrados en el Cliente](#centrados-en-el-cliente)
  - [Arquitectura de Referencia](#arquitectura-de-referencia)
    - [Diferencia entre Gestión de Incidentes y Gestión de problemas](#diferencia-entre-gestión-de-incidentes-y-gestión-de-problemas)
  - [Principios y Lineamientos](#principios-y-lineamientos)
    - [Lineamientos](#lineamientos)
      - [Título del lineamiento a definir](#título-del-lineamiento-a-definir)
  - [Lineameintos](#lineameintos)
  
  
## Introducción

Documento elaborado por la Gerencia de Arquitectura y Evolución Tecnológica Hispam, con el propósito de establecer los principios y lineamientos de arquitectura, los cuales deben ser contemplados por las operadoras del grupo de Hispam para la implementación y/o evolución de sus sistemas con  la aplicación de Trouble Ticketing.


## Alcance

El alcance de este documento es definir una arquitectura de referencia, y establecer los principios, lineamientos y funcionalidades básicas que deben ser cubiertas por la solución de Trouble Ticketing en todo su ámbito de aplicación, considerando los macroprocesos asociados, basados en eTOM y las funcionalidades según TAM.
No es parte del alcance, definir qué herramienta particular debe seleccionarse para cubrir el dominio funcional de Activación.  

## Audiencia

Las áreas o grupos a los que está dirigido este documento, son aquellos que tienen relación con los proyectos de evolución y/o selección y posterior implementación de una herramienta de Trouble Ticketing convergente en las distintas operaciones de la región. Entre ellos consideramos a las áreas regionales Hispam de Planificación, Sistemas Back End y Gestión de Proyectos, otras áreas usuarias de cada OB, y a todos aquellos grupos afines que de alguna u otra manera tengan relación con dichos proyectos.  


## Ubicación en los Frameworks de Referencia del TM Forum

### Framework de Aplicaciones TAM

A nivel del framework de aplicaciones TAM, las funcionalidades de “Trouble Ticketing” están situadas dentro de las intersecciones entre la vertical de “Assurance” y los dominios del “Service Domain”.  

![Diagrama de dominios resaltando la aplicación](./image/Application_Framework_Level_1_Overview.png)

![Diagrama de los subniveles de la aplicación](./image/Service_Management_Domain.png)
![Diagrama de los subniveles de la aplicación](./image/Service_Problem_Management.png)

Las aplicaciones de gestión de problemas de servicio son responsables de recibir el servicio que afecta los problemas de los clientes, así como los problemas/fallas de la red, relacionar los diversos problemas y resolverlos de manera eficiente.

Las aplicaciones de **recepción de problemas de servicio** proporcionan la funcionalidad adecuada para recibir problemas que se perciben como que afectan al servicio.

![Diagrama de los subniveles de la aplicación](./image/Service_Problem_Reception.png)

Las aplicaciones de **Supervisión de problemas de servicio** proporcionan la funcionalidad necesaria para supervisar continuamente el estado operativo actual de los servicios del proveedor. El estado operativo actual está disponible como notificaciones para acción inmediata en caso de desviación operativa significativa.

![Diagrama de los subniveles de la aplicación](./image/Service_Problem_Monitoring.png)

Las aplicaciones de **análisis de problemas de servicio** proporcionan la funcionalidad necesaria para diagnosticar el problema del servicio. La aplicación también correlacionará los problemas de los clientes con los problemas de los recursos y priorizará el problema de manera adecuada. Los problemas de servicio que afecten la disponibilidad de los servicios al cliente notificarán a las aplicaciones de operaciones para su mitigación o corrección manual o automática inmediata.

![Diagrama de los subniveles de la aplicación](./image/Service_Problem_Analysis.png)

Las aplicaciones de **corrección y resolución de problemas de servicio** brindan la funcionalidad necesaria para resolver el problema de servicio y devolverlo a un estado operativo normal de la manera más eficiente posible.
![Diagrama de los subniveles de la aplicación](./image/Service_Problem_Correction.png)

Las aplicaciones de **seguimiento y gestión de problemas de servicio** brindan la funcionalidad necesaria para garantizar que los problemas de servicio se resuelvan de la manera más eficiente posible.

![Diagrama de los subniveles de la aplicación](./image/Service_Problem_Trakin.png)

Las aplicaciones de **informes de problemas de servicio** proporcionan la funcionalidad necesaria para informar sobre el estado de los problemas de servicio abiertos.

![Diagrama de los subniveles de la aplicación](./image/Service_Problem_Reporting.png)

Las aplicaciones de **Establecimiento del modelo de monitoreo de problemas de servicio** brindan la funcionalidad necesaria para establecer qué se monitoreará y cómo se monitoreará en términos de problemas de servicio.
![Diagrama de los subniveles de la aplicación](./image/Service_Problem_Model.png)

## Macroprocesos TM Forum

Los procesos en los que interviene Trouble Ticketing de acuerdo con las visiones centradas en el Cliente, la Red y el Producto son:

### Centrados en el Cliente

![Diagrama de los procesos TM Forum](./image/MacroProceso_TAM.png)


## Arquitectura de Referencia

![Diagrama de arquitectura de referencia del Activador](./images/Activador_new.drawio.png)

### Diferencia entre Gestión de Incidentes y Gestión de problemas

Es importante entender que es un incidente y un problema para poder gestionarlo de manera correcta.

Un incidente es un solo evento no planificado que causa una interrupción o reducción en la calidad del servicio. Un problema es una causa o posible causa de uno o varios incidentes. <br/>
Con esta aclaración podemos indicar que, la gestión de incidentes no se preocupa de encontrar y analizar las causas subyacentes a un determinado incidente sino exclusivamente a restaurar el servicio. El objetivo de la gestión de incidentes es restablecer un servicio lo más pronto posible. <br/>
En cambio, la gestión de problemas se preocupa de investigar y solucionar la causa raíz y encontrar soluciones permanentes. El objetivo de la gestión de problemas es prevenir futuros incidentes.


## Principios y Lineamientos

### Lineamientos

#### Título del lineamiento a definir

| Código  | Se definen 3 letras mayúsculas que indican el tipo de lineamiento y un número secuencial. Ej. CAT_01 | 
|:---:|:--- |
|Lineamiento| Título del lineamiento a definir. Proporciona un resumen corto y claro del lineamiento. Evitar palabras ambiguas y suavizantes como "apoyar" y "considerar".|
|Declaración  | Se debe definir y describir el lineamiento usando modo imperativo. Redacción sin ambigüedades. La declaración amplía el nombre usado en Lineamiento y proporciona una explicación más profunda. Evitar explicar cómo aplicar el lineamiento.|
|Justificación| Se debe indicar los motivos y razones por los que se debe aplicar dicho lineamiento. Es la explicación de porque existe el lineamiento.  |
|Implicaciones| Se debe indicar que será necesario implementar para aplicar dicho lineamiento. Resaltar los requisitos para llevar a cabo el lineamiento. Indicar claramente el impacto y las consecuencias de seguir el lineamiento.|
|Contexto| Se debe indicar el macroproceso en el que aplica el lineamiento.|
|Escenario| Se debe indicar los casos de uso en los cuales aplica.|  
 

 ## Lineameintos

 [SP_0001 ITSM](TT%20001%20ITSM.md)
 [SP_0002 GUI](TT%20002%20GUI.md)