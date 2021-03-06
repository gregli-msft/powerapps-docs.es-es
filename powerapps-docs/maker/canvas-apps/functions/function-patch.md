---
title: Función Revisión | Microsoft Docs
description: Información de referencia de la función Revisión en PowerApps, con sintaxis y ejemplos
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/21/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 64641b0cc0822a955de2b1c9e53692dac9dfcf31
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2018
ms.locfileid: "42865495"
---
# <a name="patch-function-in-powerapps"></a>Función Revisión en PowerApps
Modifica o crea uno o varios [registros](../working-with-tables.md#records) de un [origen de datos](../working-with-data-sources.md) o combina registros fuera de un origen de datos.

Use la función **Patch** para modificar registros en situaciones complejas, como cuando se realizan actualizaciones que no requieren interacción del usuario o se usan formularios que abarcan varias pantallas.

En situaciones menos complejas, puede utilizar el control **Formulario de edición** para actualizar registros en un origen de datos con mayor facilidad. Cuando agrega un control **Formulario de edición**, proporciona a los usuarios un formulario para rellenar y después guarda los cambios en un origen de datos. Para más información, consulte [Descripción de los formularios de datos](../working-with-forms.md).

## <a name="overview"></a>Información general
Use la función **Revisión** para modificar uno o varios registros de un origen de datos.  Los valores de [campos](../working-with-tables.md#elements-of-a-table) específicos se modifican sin que otras propiedades se vean afectadas. Por ejemplo, esta fórmula cambia el número de teléfono de un cliente llamado Contoso:

**Patch( Customers, First( Filter( Customers, Name = "Contoso" ) ), { Phone: “1-212-555-1234” } )**

Use **Revisión** con la función **[Defaults](function-defaults.md)** para crear registros. Use este comportamiento para crear una [sola pantalla](../working-with-data-sources.md) tanto para crear como para editar registros. Por ejemplo, la siguiente fórmula crea un registro para un cliente llamado Contoso:

**Patch( Customers, Defaults( Customer ), { Name: “Contoso” } )**

Incluso si no está trabajando con un origen de datos, puede usar **Revisión** para combinar dos o más registros. Por ejemplo, esta fórmula combina dos registros en uno que identifica tanto el número de teléfono como la ubicación de Contoso:

**Patch( { Name: "Contoso", Phone: “1-212-555-1234” }, { Name: "Contoso", Location: “Midtown”  } )**

## <a name="description"></a>Descripción
### <a name="modify-or-create-a-record-in-a-data-source"></a>Modificar o crear un registro en un origen de datos
Para usar esta función con un origen de datos, especifique el origen de datos y, a continuación, especifique un registro base:

* Para modificar un registro, el registro base debe proceder de un origen de datos.  El registro base puede proceder de una propiedad **[Items](../controls/properties-core.md)** de la galería, haberse colocado en una [variable de contexto](../working-with-variables.md#create-a-context-variable) o proceder de algún otro sitio. Sin embargo, debe poder realizar un seguimiento del registro base hasta el origen de datos.  Esto es importante, ya que el registro incluirá información adicional para ayudar a encontrar el registro para la modificación.  
* Para crear un registro, use la función **[Defaults](function-defaults.md)** para crear un registro base con valores predeterminados.  

A continuación, especifique uno o más registros de cambio, cada uno de los cuales contenga nuevos valores de propiedad que reemplacen los valores de propiedad en el registro base. Los registros de cambio se procesan en orden, desde el principio de la lista de argumentos hasta el final, donde los valores de propiedad últimos reemplazan a los primeros.

El valor devuelto de **Revisión** es el registro modificado o creado.  Si ha creado un registro, el valor devuelto puede incluir propiedades que el origen de datos generó automáticamente.

Al actualizar un origen de datos, pueden surgir uno o varios problemas. Use la función **[Errors](function-errors.md)** para identificar y examinar los problemas, como se describe en [Working with Data Sources](../working-with-data-sources.md) (Uso de orígenes de datos).

Las funciones relacionadas incluyen **[Actualizar](function-update-updateif.md)**, que puede usar para reemplazar un registro entero, o **[Recopilar](function-clear-collect-clearcollect.md)**, que puede usar para crear un registro.  Puede usar la función **[UpdateIf](function-update-updateif.md)** para modificar propiedades específicas de varios registros según una condición.

### <a name="modify-or-create-a-set-of-records-in-a-data-source"></a>Modificar o crear un conjunto de registros en un origen de datos
**Revisión** también puede utilizarse para crear o modificar varios registros con una sola llamada.

En lugar de pasar un único registro base, se puede proporcionar una tabla de registros base en el segundo argumento.  También se proporcionan registros de cambio en una tabla, que se corresponden uno a uno con los registros base.  El número de registros en cada tabla de cambios debe ser el mismo que el número de registros en la tabla base.

Cuando se usa **Revisión** de esta manera, el valor devuelto también es una tabla donde cada registro se corresponde uno a uno con los registros base y de cambio.

### <a name="merge-records-outside-of-a-data-source"></a>Combinar registros fuera de un origen de datos
Especifique dos o más registros que desee combinar. Los registros se procesan en orden desde el principio de la lista de argumentos hasta el final, donde los valores de propiedad últimos reemplazan a los primeros.

**Revisión** devuelve el registro combinado y no modifica sus argumentos ni los registros de ningún origen de datos.

## <a name="syntax"></a>Sintaxis
#### <a name="modify-or-create-a-record-in-a-data-source"></a>Modificar o crear un registro en un origen de datos
**Revisión**( *DataSource*, *BaseRecord*, *ChangeRecord1* [, *ChangeRecord2*, … ])

* *DataSource*: requerido. El origen de datos que contiene el registro que desea modificar o que contendrá el registro que desea crear.
* *BaseRecord*: valor necesario. El registro para modificar o crear.  Si el registro proviene de un origen de datos, el registro se encuentra y se modifica. Si se usa el resultado de **[Defaults](function-defaults.md)**, se crea un registro.
* *ChangeRecord(s)*: requerido.  Uno o más registros que contienen propiedades para modificar en *BaseRecord*.  Los registros de cambio se procesan en orden, desde el principio de la lista de argumentos hasta el final, donde los valores de propiedad últimos reemplazan a los primeros.

#### <a name="modify-or-create-a-set-of-records-in-a-data-source"></a>Modificar o crear un conjunto de registros en un origen de datos
**Revisión**( *DataSource*, *BaseRecordsTable*, *ChageRecordTable1*, [, *ChangeRecordTable2*,... ] )

* *DataSource*: requerido. El origen de datos que contiene los registros que desea modificar o que contendrá los registros que desea crear.
* *BaseRecordTable*: requerido. Una tabla de registros para modificar o crear.  Si el registro proviene de un origen de datos, el registro se encuentra y se modifica. Si se usa el resultado de **[Defaults](function-defaults.md)**, se crea un registro.
* *ChangeRecordTable(s)*: requerido.  Una o varias tablas de registros que contienen propiedades para modificar de cada registro de *BaseRecordTable*.  Los registros de cambio se procesan en orden, desde el principio de la lista de argumentos hasta el final, donde los valores de propiedad últimos reemplazan a los primeros.

#### <a name="merge-records"></a>Combinar registros
**Revisión**( *Record1*, *Record2* [, …] )

* *Registro(s)*: requerido.  Al menos dos de los registros que desea combinar. Los registros se procesan en orden desde el principio de la lista de argumentos hasta el final, donde los valores de propiedad últimos reemplazan a los primeros.

## <a name="examples"></a>Ejemplos
#### <a name="modify-or-create-a-record-in-a-data-source"></a>Modificar o crear un registro (en un origen de datos)
En estos ejemplos, modificará o creará un registro en un origen de datos denominado **IceCream**, que contiene los datos de esta [tabla](../working-with-tables.md) y generará automáticamente los valores de la [columna](../working-with-tables.md#columns) **ID**:

![](media/function-patch/icecream.png)

| Fórmula | Descripción | Resultado |
| --- | --- | --- |
| **Patch(&nbsp;IceCream,<br>First( Filter( IceCream, Flavor = "Chocolate" ) ), {&nbsp;Quantity:&nbsp;400&nbsp;} )** |Modifica un registro del origen de datos **IceCream**:<ul><li> La columna **ID** del registro para modificar contiene el valor de **1**. (El registro **Chocolate** tiene ese ID).</li><li>El valor de la columna **Quantity** cambia a **400**. |{&nbsp;ID:&nbsp;1, Flavor:&nbsp;"Chocolate", Quantity:&nbsp;400 }<br><br>La entrada **Chocolate** del origen de datos **IceCream** se ha modificado. |
| **Patch( IceCream, Defaults(&nbsp;IceCream ), {&nbsp;Flavor:&nbsp;“Strawberry”&nbsp;}&nbsp;)** |Crea un registro en el origen de datos **IceCream**:<ul><li>La columna **ID** contiene el valor **3**, que el origen de datos genera automáticamente.</li><li>La columna **Quantity** contiene **0**, que es el valor predeterminado de esa columna en el origen de datos **IceCream**, como especifica la función **[Defaults](function-defaults.md)**.<li>La columna **Flavor** contiene el valor de **Strawberry**.</li> |{ ID:&nbsp;3, Flavor:&nbsp;“Strawberry”, Quantity:&nbsp;0&nbsp;}<br><br>Se ha creado la entrada **Strawberry** en el origen de datos **IceCream**. |

Después de que se han evaluado las fórmulas anteriores, el origen de datos termina con estos valores:

![](media/function-patch/icecream-after.png)

#### <a name="merge-records-outside-of-a-data-source"></a>Combinar registros (fuera de un origen de datos)

| Fórmula | Descripción | Resultado |
| --- | --- | --- |
| **Patch(&nbsp;{&nbsp;Name:&nbsp;"James",&nbsp;Score:&nbsp;90&nbsp;}, {&nbsp;Name:&nbsp;"Jim",&nbsp;Passed:&nbsp;true&nbsp;} )** |Combina dos registros fuera de un origen de datos:<br><ul><li>Los valores de la columna **Name** de cada registro no coinciden. El resultado contiene el valor (**Jim**) en el registro que se aproxima más al final de la lista de argumentos en lugar del valor (**James**) en el registro que está más cerca del principio.</li><li>El primer registro contiene una columna (**Score**) que no existe en el segundo registro. El resultado contiene esa columna con su valor (**90**).</li><li>El segundo registro contiene una columna (**Passed**) que no existe en el primer registro. El resultado contiene esa columna con su valor (**true**). |{&nbsp;Name:&nbsp;"Jim", Score:&nbsp;90, Passed:&nbsp;true&nbsp;} |

