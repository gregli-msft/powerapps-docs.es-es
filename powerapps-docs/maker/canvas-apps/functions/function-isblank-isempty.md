---
title: Funciones En blanco, Fusionar, IsBlank e IsEmpty | Microsoft Docs
description: Información de referencia de las funciones Blank, Coalesce, IsBlank e IsEmpty de PowerApps, con sintaxis y ejemplos
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.component: canvas
ms.date: 07/24/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e31d3689c7b61c408be90c31f1e212e4fdd9a91c
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2018
ms.locfileid: "42848992"
---
# <a name="blank-coalesce-isblank-and-isempty-functions-in-powerapps"></a>Funciones Blank, Coalesce, IsBlank e IsEmpty en PowerApps
Comprueba si un valor está en blanco o una [tabla](../working-with-tables.md) no contiene [registros](../working-with-tables.md#records), y proporciona una manera de crear valores *en blanco*.

## <a name="overview"></a>Información general
*Blank* es un marcador de posición para "sin valor" o "valor desconocido". Un control **[Entrada de texto](../controls/control-text-input.md)** está *en blanco* si el usuario no ha escrito en él ningún carácter. El mismo control ya no está *en blanco* tan pronto como el usuario escribe un carácter en él.  Algunos orígenes de datos pueden almacenar y devolver valores NULL, que se representan en PowerApps como *en blanco*.

> [!NOTE]
> Actualmente, solo se admite el almacenamiento de valores *en blanco* en las colecciones locales. Sabemos que muchos orígenes de datos admiten valores *en blanco* (NULL) y estamos trabajando para superar esta limitación.

Cualquier propiedad o valor calculado puede estar *en blanco*.  Por ejemplo, un valor booleano normalmente tiene uno de dos valores: **true** o **false**.  Pero además de estos dos, también puede estar *en blanco*.  Esto es similar a Microsoft Excel, donde una celda de la hoja de cálculo empieza como en blanco pero puede contener los valores **TRUE** o **FALSE**, entre otros. En cualquier momento, se puede quitar el contenido de la celda y volvería a un estado *en blanco*.

El término *vacío* es específico de tablas que no contienen registros. La estructura de tabla puede estar intacta, con nombres de [columna](../working-with-tables.md#columns), pero ningún dato en la tabla. Una tabla puede comenzar como vacía, obtener registros y ya no estar vacía y luego quitarse los registros y estar de nuevo vacía.

## <a name="description"></a>Descripción
La función **En blanco** devuelve un valor *en blanco*. Use esta función para almacenar un valor NULL en un origen de datos que admita estos valores, de forma que se quiten en la práctica todos los valores del campo.

La función **IsBlank** comprueba un valor *en blanco*. Los valores *en blanco* se encuentran en situaciones como las siguientes:

* El valor devuelto por la función **En blanco**.
* Una propiedad de control no tiene ninguna fórmula establecida para ella.
* No se escribe ningún valor en un control de entrada de texto ni se realiza ninguna selección en un cuadro de lista. Puede usar **IsBlank** para proporcionar comentarios de que un campo es obligatorio.
* Una cadena que no contiene ningún carácter tiene un valor de **[Len](function-len.md)** de 0.
* Se producido un error en una función. Con frecuencia, uno de los argumentos para la función no era válido. Muchas funciones devuelven *en blanco* si el valor de un argumento está *en blanco*.
* Los [orígenes de datos conectados](../working-with-data-sources.md), como SQL Server, pueden usar valores "null". Estos valores aparecen como *en blanco* en PowerApps.
* La parte *else* de una función **[If](function-if.md)** no se especificó y todas las condiciones fueron **false**.
* Usó la función **[Actualizar](function-update-updateif.md)** pero no especificó un valor para todas las columnas. Como resultado, no se colocó ningún valor en las columnas que no especificó.

La función **Coalesce** evalúa sus argumentos en orden y devuelve el primer valor que no sea *blank*.  Utilice esta función para reemplazar un valor *blank* por un valor diferente, sin cambiar los valores que no son *blank*.  Si todos los argumentos son *blank*, la función devuelve *blank*.  Todos los argumentos de **Coalesce** debe ser del mismo tipo; por ejemplo, no puede combinar números con cadenas de texto.  **Coalesce( value1, value2 )** es el equivalente más conciso de **If( Not( IsBlank( value1 ) ), value1, value2 )** y no requiere que **value1** se evalúe dos veces.  

La función **IsEmpty** comprueba si una tabla contiene registros. Es equivalente a usar la función **[CountRows](function-table-counts.md)** y la comprobación de cero. Puede usar **IsEmpty** para comprobar errores de origen de datos en combinación con la función **[Errores](function-errors.md)**.

El valor devuelto para **EsBlanco** e **IsEmpty** es un valor booleano **true** o **false**.

## <a name="syntax"></a>Sintaxis
**En blanco**()

**Coalesce**( *Valor1* [, *Valor2*, ... ] )

* *Valores*: requerido. Valores que se van a comprobar.  Cada valor se evalúa en orden hasta que se encuentra un valor que no es *blank*.  Los valores situados después del primer valor no *blank* no se evalúan.  

**IsBlank**( *Value* )

* *Value*: requerido. Valor que se va a probar.

**IsEmpty**( *Table* )

* *Table*: requerido. Tabla en la que se van a comprobar registros.

## <a name="examples"></a>Ejemplos
### <a name="blank"></a>En blanco
> [!NOTE]
> Actualmente, el siguiente ejemplo solo funciona en colecciones locales.  Sabemos que muchos orígenes de datos admiten valores *en blanco* (NULL) y estamos trabajando para superar esta limitación.

1. Cree una aplicación desde el principio y agregue un control **Botón**.
2. Establezca la propiedad **[OnSelect](../controls/properties-core.md)** del botón en esta fórmula:

    **ClearCollect( Cities, { Name: "Seattle", Weather: "Rainy" } )**
3. Obtenga una vista previa de la aplicación, haga clic o pulse en el botón que agregó y luego cierre la vista previa.  
4. En el menú **Archivo**, haga clic o pulse en **Colecciones**.

     Aparece la colección **Cities**, que muestra un registro con "Seattle" y "Rainy":

    ![Colección que muestra Seattle con tiempo lluvioso](./media/function-isblank-isempty/seattle-rainy.png)
5. Haga clic o pulse en la flecha Atrás para volver al área de trabajo predeterminada.
6. Agregue un control **Etiqueta** y establezca su propiedad **Texto** en esta fórmula:

    **IsBlank( First( Cities ).Weather )**

    La etiqueta muestra **false** porque el campo **Weather** contiene un valor ("Rainy").
7. Agregue un botón y establezca su propiedad **AlSeleccionar** en esta fórmula:

    **Patch( Cities, First( Cities ), { Weather: Blank() } )**
8. Obtenga una vista previa de la aplicación, haga clic o pulse en el botón que agregó y luego cierre la vista previa.  

    El campo **Weather** del primer registro de **Cities** se sustituye por un valor *en blanco*, de forma que se reemplaza el valor inicial "Rainy" que estaba ahí anteriormente.

    ![Colección que muestra Seattle con un campo Weather en blanco](./media/function-isblank-isempty/seattle-blank.png)

    La etiqueta muestra **true** porque el campo **Weather** ya no contiene ningún valor.

### <a name="coalesce"></a>Coalesce

| Fórmula | Descripción | Resultado |
| --- | --- | --- |
| **Coalesce( Blank(), 1 )** |Comprueba el valor devuelto por la función **En blanco**, que siempre devuelve un valor *en blanco*. Como el primer argumento es *blank*, la evaluación continúa con el argumento siguiente hasta que se encuentra un valor no *blank*. |**1** |
| **Coalesce( Blank(), Blank(), Blank(), Blank(), 2, 3 )** |**Coalesce** comienza al principio de la lista de argumentos y evalúa cada uno de ellos por orden hasta que encuentra un valor no *blank*.  En este caso, los cuatro primeros argumentos devuelven *blank*, por lo que la evaluación continúa con el quinto argumento. El quinto argumento no es *blank*, por lo que la evaluación se detiene ahí. Se devuelve el valor del quinto argumento y no se evalúa el sexto argumento. |**2** |

### <a name="isblank"></a>EsBlanco
1. Cree una aplicación desde el principio, agregue un control de entrada de texto y llámelo **FirstName**.
2. Agregue una etiqueta y establezca su propiedad **[Text](../controls/properties-core.md)** en esta fórmula:

    **If( IsBlank( FirstName.Text ), "First Name is a required field." )**

    De forma predeterminada, la propiedad **[Texto](../controls/properties-core.md)** de un control de entrada de texto se establece en **"Entrada de texto"**. Como la propiedad contiene un valor, no está en blanco, y la etiqueta no muestra ningún mensaje.
3. Quite todos los caracteres del control de entrada de texto, espacios incluidos.

    Como la propiedad **[Texto](../controls/properties-core.md)** ya no contiene ningún carácter, está *en blanco* y **EsBlanco( FirstName.Text )** será **true**. Se muestra el mensaje de campo requerido.

Para más información sobre cómo realizar la validación mediante otras herramientas, consulte la función **[Validar](function-validate.md)** y el [uso de orígenes de datos](../working-with-data-sources.md).  

Otros ejemplos:

| Fórmula | Descripción | Resultado |
| --- | --- | --- |
| **IsBlank( Blank() )** |Comprueba el valor devuelto por la función **En blanco**, que siempre devuelve un valor *en blanco*. |**true** |
| **IsBlank( "" )** |Una cadena que no contiene ningún carácter. |**true** |
| **IsBlank( "Hello" )** |Una cadena que contiene uno o más caracteres. |**false** |
| **IsBlank( *AnyCollection* )** |Como la [colección](../working-with-data-sources.md#collections) existe, no está en blanco, incluso si no contiene ningún registro. Para comprobar si existe una colección vacía, use **IsEmpty** en su lugar. |**false** |
| **IsBlank( Mid( "Hello", 17, 2 ) )** |El carácter inicial de **[Mid](function-left-mid-right.md)** está más allá del final de la cadena.  El resultado es una cadena vacía. |**true** |
| **IsBlank( If( false, false ) )** |Una función **[If](function-if.md)** sin *ElseResult*.  Como la condición es siempre **false**, esta función **[If](function-if.md)** siempre devuelve *en blanco*. |**true** |

### <a name="isempty"></a>IsEmpty
1. Cree una aplicación desde el principio y agregue un control **Botón**.
2. Establezca la propiedad **[OnSelect](../controls/properties-core.md)** del botón en esta fórmula:

    **Collect( IceCream, { Flavor: "Strawberry", Quantity: 300 }, { Flavor: "Chocolate", Quantity: 100 } )**
3. Obtenga una vista previa de la aplicación, haga clic o pulse en el botón que agregó y luego cierre la vista previa.  

    Se crea una colección denominada **IceCream** con estos datos:

    ![](media/function-isblank-isempty/icecream-strawberry-chocolate.png)

    Esta colección tiene dos registros y no está vacía. **IsEmpty( IceCream )** devuelve **false** y **CountRows( IceCream )** devuelve **2**.
4. Agregue un segundo botón y establezca su propiedad **[AlSeleccionar](../controls/properties-core.md)** en esta fórmula:

    **Clear( IceCream )**
5. Obtener una vista previa de la aplicación, haga clic o pulse en el segundo botón y luego cierre la vista previa.  

    Ahora, la colección está vacía:

    ![](media/function-isblank-isempty/icecream-clear.png)

    La función **[Clear](function-clear-collect-clearcollect.md)** quita todos los registros de una colección, lo que da lugar a una colección vacía. **IsEmpty( IceCream )** devuelve **true** y **CountRows( IceCream )** devuelve **0**.

También puede usar **IsEmpty** para comprobar si una tabla calculada está vacía, como muestran estos ejemplos:

| Fórmula | Descripción | Resultado |
| --- | --- | --- |
| **IsEmpty( [&nbsp;1,&nbsp;2,&nbsp;3 ] )** |La tabla de una columna contiene tres registros y, por lo tanto, no está vacía. |**false** |
| **IsEmpty( [&nbsp;] )** |La tabla de una columna no contiene registros y está vacía. |**true** |
| **IsEmpty( Filter( [&nbsp;1,&nbsp;2,&nbsp;3&nbsp;], Value > 5 ) )** |La tabla de una columna no contiene valores que sean mayores que 5.  El resultado del filtro no contiene ningún registro y está vacío. |**true** |

