---
title: Señales Aceleración, Aplicación, Brújula, Conexión y Ubicación | Microsoft Docs
description: Información de referencia, incluida la sintaxis y los ejemplos, para los sensores Acceleration, App, Compass, Connection y Location en PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0038a3a5a7f5e23e9777dafeb181dc2cb867c7a2
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2018
ms.locfileid: "42832154"
---
# <a name="acceleration-app-compass-connection-and-location-signals-in-powerapps"></a>Señales Aceleración, Aplicación, Brújula, Conexión y Ubicación en PowerApps
Devuelve información sobre el entorno de la aplicación, como dónde se encuentra el usuario en el mundo y la pantalla que se muestra.  

## <a name="description-and-syntax"></a>Descripción y sintaxis
Todas las señales devuelven un [registro](../working-with-tables.md#records) de información. Puede usar y almacenar esta información como un registro, o puede extraer propiedades individuales mediante el **operador** [.](operators.md)

### <a name="acceleration"></a>Acceleration
La señal **Acceleration** devuelve la aceleración del dispositivo en tres dimensiones en relación con la pantalla del dispositivo. La aceleración se mide en unidades *g* de 9,81 m/s<sup>2</sup> o 32,2 ft/s<sup>2</sup> (la aceleración que imparte la Tierra en los objetos en su superficie debida a la gravedad).

| Propiedad de la señal | Descripción |
| --- | --- |
| **Acceleration.X** |Derecha e izquierda.  El valor de la derecha es un número positivo. |
| **Acceleration.Y** |Hacia delante y atrás.  El valor hacia delante es un número positivo. |
| **Acceleration.Z** |Arriba y abajo.  El valor de arriba es un número positivo. |

### <a name="app"></a>App
La señal**App** devuelve información acerca de la aplicación en ejecución.

| Propiedad de la señal | Descripción |
| --- | --- |
| **App.ActiveScreen** |Pantalla que se muestra. Devuelve un objeto de la pantalla, que puede usar para hacer referencia a propiedades de la pantalla o comparar con otra pantalla para determinar qué pantalla se muestra.  Mediante el uso de la función **[Back](function-navigate.md)** o **[Navigate](function-navigate.md)**, puede cambiar la pantalla mostrada. |

### <a name="compass"></a>Compass
La señal **Compass** devuelve el encabezado de brújula de la parte superior de la pantalla. El encabezado se basa en el norte magnético.

| Propiedad de la señal | Descripción |
| --- | --- |
| **Compass.Heading** |Encabezado en grados.  Devuelve que un número de 0 a 360, y 0 es el norte. |

### <a name="connection"></a>Conexión
La señal **Connection** devuelve información acerca de la conexión de red. Cuando está en una conexión medida, puede que desee limitar la cantidad de datos que envíe o reciba a través de la red.

| Propiedad de la señal | Descripción |
| --- | --- |
| **Connection.Connected** |Devuelve un valor booleano **true** o **false** que indica si el dispositivo está conectado a una red. |
| **Connection.Metered** |Devuelve un valor booleano **true** o **false** que indica si la se mide la conexión. |

### <a name="location"></a>Ubicación
La señal **Location** devuelve la ubicación del dispositivo según el sistema GPS (Global Positioning System) y otra información de dispositivo, como las comunicaciones de la torre de telefonía móvil y la dirección IP.

Cuando un usuario tiene acceso a la información de ubicación por primera vez, el dispositivo puede solicitar que el usuario permita el acceso a esta información.

A medida que cambia la ubicación, las dependencias de la ubicación se recalcularán continuamente, lo que consumirá corriente de la batería del dispositivo. Para conservar la vida útil de la batería, puede usar las funciones **[Enable](function-enable-disable.md)** y **[Disable](function-enable-disable.md)** para activar y desactivar las actualizaciones de la ubicación. La ubicación se desactiva automáticamente si la pantalla mostrada no depende de la información de la ubicación.

| Propiedad de la señal | Descripción |
| --- | --- |
| **Location.Altitude** |Devuelve un número que indica la altitud, medida en metros, por encima del nivel del mar. |
| **Location.Latitude** |Devuelve un número, de -90 y 90, que indica la latitud, que se mide en grados desde el Ecuador. Un número positivo indica una ubicación que sea al norte del ecuador. |
| **Location.Longitude** |Devuelve un número, de 0 y 180, que indica la longitud, que se mide en grados oeste desde Greenwich, Inglaterra. |

## <a name="examples"></a>Ejemplos
Desde el montículo del lanzador en Safeco Field en Seattle, Washington, un lanzador de baseball tira un teléfono a un lanzador situado en la base. El teléfono se encuentra situado horizontalmente con respecto a la tierra, la parte superior de la pantalla está orientada al lanzador, y el lanzador no hace ningún giro. En esta ubicación, el teléfono tiene una cobertura medida, pero no tiene Wi-Fi. Se muestra la pantalla **PlayBall**.   

| Fórmula | Descripción | Resultado |
| --- | --- | --- |
| **Location.Latitude** |Devuelve la latitud de la ubicación actual.  Safeco Field se encuentra en las coordenadas de mapa 47.591 N, 122.333 W. |47.591<br><br>La latitud cambiará continuamente a medida que la pelota se mueva entre el lanzador y el receptor. |
| **Location.Longitude** |Devuelve la longitud de la ubicación actual. |122.333<br><br>La longitud cambiará continuamente a medida que la pelota se mueva entre el lanzador y el receptor. |
| **Location** |Devuelve la latitud y longitud de la ubicación actual, como un registro. |{&nbsp;Latitud:&nbsp;47.591, Longitud:&nbsp;122.333&nbsp;} |
| **Compass.Heading** |Devuelve el encabezado de brújula de la parte superior de la pantalla. En Safeco Field, la base del bateador está aproximadamente al suroeste del montículo del lanzador. |230.25 |
| **Acceleration.X** |Devuelve la aceleración del dispositivo de lado a lado. El lanzador está lanzando el teléfono en línea recta con respecto a la parte superior de la pantalla, por lo que el dispositivo no cuenta con una aceleración de lado a lado. |0 |
| **Acceleration.Y** |Devuelve la aceleración del dispositivo de la parte delantera a la trasera. El lanzador inicialmente ofrece al dispositivo una gran aceleración al lanzar el dispositivo, que pasa de 0 a 144 km por hora (40 metros por segundo) en medio segundo. Después de que el dispositivo esté en el aire, sin tener en cuenta la fricción del aire, no se acelera más. El dispositivo deja de acelerarse cuando el receptor lo atrapa, hasta que para. |8,2, cuando el lanzador lanza el dispositivo.<br><br>0, cuando el dispositivo está en el aire.<br><br>-8,2, cuando el receptor atrapa el dispositivo. |
| **Acceleration.Z** |Devuelve la aceleración del dispositivo de la parte delantera a la trasera. Mientras está en el aire, el dispositivo experimenta los efectos de la gravedad. |0, antes de que el lanzador lace el dispositivo.<br><br>1, cuando el dispositivo está en el aire.<br><br>0, cuando el receptor atrapa el dispositivo. |
| **Acceleration** |Devuelve la aceleración como registro. |{ X: 0, Y: 264, Z: 0 } cuando el lanzador lanza el dispositivo. |
| **Connection.Connected** |Devuelve un valor booleano que indica si el dispositivo está conectado a una red. |**true** |
| **Connection.Metered** |Devuelve un valor booleano que indica si la se mide la conexión. |**true** |
| **App.ActiveScreen = PlayBall** |Devuelve un valor booleano que indica si se muestra **PlayBall**. |**true** |
| **App.ActiveScreen.Fill** |Devuelve el color de fondo de la pantalla mostrada. |**Color.Green** |

