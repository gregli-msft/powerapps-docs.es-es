---
title: Funciones AddColumns, DropColumns, CambiarNombreColumnas y MostrarColumnas | Microsoft Docs
description: Información de referencia para las funciones AddColumns, DropColumns, CambiarNombreColumnas y MostrarColumnas en PowerApps, incluidos la sintaxis y ejemplos
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
ms.openlocfilehash: 6a7d511143a0b16e04ae31263dec9f6a4e04689e
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2018
ms.locfileid: "42864365"
---
# <a name="addcolumns-dropcolumns-renamecolumns-and-showcolumns-functions-in-powerapps"></a>Funciones AddColumns, DropColumns, CambiarNombreColumnas y MostrarColumnas en PowerApps
Forma una [tabla](../working-with-tables.md) agregando, quitando, cambiando el nombre y seleccionando sus [columnas](../working-with-tables.md#columns).

## <a name="overview"></a>Información general
Estas funciones dan forma a una tabla mediante el ajuste de sus columnas:

* Reducción de una tabla que contiene varias columnas a una sola columna para su uso con las funciones de columna única, como **[Minusc](function-lower-upper-proper.md)** o  **[Abs](function-numericals.md)**.  
* Incorporación de una columna calculada a una tabla (por ejemplo, una columna **Total Price** que muestre el resultado de multiplicar **Quantity** por **Unit Price**).
* Cambio del nombre de una columna a algo más significativo, para mostrarla a los usuarios o para su uso en las fórmulas.

Una tabla es un valor en PowerApps, como una cadena o un número.  Puede especificar una tabla como un argumento en una fórmula, y las funciones pueden devolver una tabla como resultado. Las funciones que se describen en este tema no modifican una tabla. En su lugar, usan una tabla como un argumento y devuelven una nueva tabla con una transformación aplicada.  Consulte cómo [trabajar con tablas](../working-with-tables.md) para más detalles.  

No se pueden modificar las columnas de un [origen de datos](../working-with-data-sources.md) mediante el uso de estas funciones. Tiene que modificar los datos en su origen. Puede agregar columnas a una [colección](../working-with-data-sources.md#collections) con la función **[Recopilar](function-clear-collect-clearcollect.md)**.  Consulte cómo [trabajar con fuentes de datos](../working-with-data-sources.md) para más detalles.  

## <a name="description"></a>Descripción
La función **AddColumns** agrega una columna a una tabla y una fórmula define los valores de esa columna. Las columnas existentes permanecen sin modificar.

La fórmula se evalúa para cada registro de la tabla.
[!INCLUDE [record-scope](../../../includes/record-scope.md)]

La función **DropColumns** excluye las columnas de una tabla.  El resto de las columnas permanece sin modificar. **DropColumns** excluye las columnas, y **MostrarColumnas** las incluye.

La función **CambiarNombreColumnas** cambia el nombre de las columnas de una tabla. Todas las demás columnas mantienen sus nombres originales.

La función **MostrarColumnas** incluye columnas de una tabla y quita todas las demás columnas. Puede usar **MostrarColumnas** para crear una tabla de una sola columna a partir de una tabla de varias columnas.  **MostrarColumnas** incluye columnas, y **DropColumns** las excluye.  

Para todas estas funciones, el resultado es una nueva tabla con la transformación aplicada.  La tabla original no se modifica.

[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Sintaxis
**AddColumns**( *Table*, *ColumnName1*, *Formula1* [, *ColumnName2*, *Formula2*, ... ] )

* *Table*: requerido.  La tabla sobre la cual se opera.
* *ColumnName(s)*: requerido. Nombres de las columnas para agregar.  Tiene que especificar una cadena (por ejemplo, **"Name"** entre comillas dobles incluidas) para este argumento.
* *Formula(s)*: requerido.  La fórmula o fórmulas para evaluar para cada registro. Se agregará el resultado como el valor de la nueva columna correspondiente. Puede hacer referencia a otras columnas de la tabla en esta fórmula.

**DropColumns**( *Table*, *ColumnName1* [, *ColumnName2*, ... ] )

* *Table*: requerido.  La tabla sobre la cual se opera.
* *ColumnName(s)*: requerido. Nombres de las columnas para excluir. Tiene que especificar una cadena (por ejemplo, **"Name"** entre comillas dobles incluidas) para este argumento.

**CambiarNombreColumnas**( *Table*, *OldColumneName*, *NewColumnName* )

* *Table*: requerido.  La tabla sobre la cual se opera.
* *OldColumnName*: requerido. Nombre de la columna a la que se va a cambiar el nombre. Este nombre tiene que ser una cadena (por ejemplo, **"Name"** entre comillas dobles incluidas).
* *NewColumnName*: requerido. Nombre de reemplazo. Tiene que especificar una cadena (por ejemplo, **"Customer Name"** entre comillas dobles incluidas) para este argumento.

**MostrarColumnas**( *Table*, *ColumnName1* [, *ColumnName2*, ... ] )

* *Table*: requerido.  La tabla sobre la cual se opera.
* *ColumnName(s)*: requerido. Nombres de las columnas para incluir. Tiene que especificar una cadena (por ejemplo, **"Name"** entre comillas dobles incluidas) para este argumento.

## <a name="examples"></a>Ejemplos
En los ejemplos en esta sección, use el origen de datos **IceCreamSales**, que contiene los datos de esta tabla:

![](media/function-table-shaping/icecream.png)

Ninguno de estos ejemplos modificar el origen de datos **IceCreamSales**. Cada función transforma el valor del origen de datos como una tabla y devuelve ese valor como resultado.

| Fórmula | Descripción | Resultado |
| --- | --- | --- |
| **AddColumns (IceCreamSales, "Revenue", UnitPrice * QuantitySold)** |Agrega una columna **Revenue** al resultado.  Para cada registro, se evalúa **UnitPrice * QuantitySold**, y el resultado se coloca en la nueva columna. |<style> img { max-width: none; } </style> ![](media/function-table-shaping/icecream-add-revenue.png) |
| **DropColumns (IceCreamSales, "UnitPrice")** |Excluye la columna **UnitPrice** del resultado. Use esta función para excluir columnas y usar **MostrarColumnas** para incluirlas. |![](media/function-table-shaping/icecream-drop-price.png) |
| **MostrarColumnas (IceCreamSales, "Flavor")** |Incluye solamente la columna **Flavor** en el resultado. Use esta función para incluir columnas y **DropColumns** para excluirlas. |![](media/function-table-shaping/icecream-select-flavor.png) |
| **CambiarNombreColumnas (IceCreamSales, "UnitPrice", "Price")** |Cambia el nombre de la columna **UnitPrice** en el resultado. |![](media/function-table-shaping/icecream-rename-price.png) |
| **DropColumns(<br>CambiarNombreColumnas(<br>AddColumns( IceCreamSales, "Revenue",<br>UnitPrice * QuantitySold ),<br>"UnitPrice", "Price" ),<br>"Quantity" )** |Realiza las siguientes transformaciones de tabla en orden, comenzando desde el interior de la fórmula: <ol><li>Agrega una columna **Revenue** basada en el cálculo por registro de **UnitPrice * Quantity**.<li>Cambia el nombre de **UnitPrice** a **Price**.<li>Excluye la columna **Quantity**.</ol>  Tenga en cuenta que el orden es importante. Por ejemplo, no se puede calcular con **UnitPrice** después de que se le haya cambiado el nombre. |![](media/function-table-shaping/icecream-all-transforms.png) |

### <a name="step-by-step"></a>Paso a paso
1. Importe o cree una colección denominada **Inventory**, como se describe en el primer subprocedimiento del artículo sobre [visualización de imágenes y texto en una galería](../show-images-text-gallery-sort-filter.md).
2. Agregue un botón y establezca su propiedad **[OnSelect](../controls/properties-core.md)** en esta fórmula:
   
    **ClearCollect(Inventory2, CambiarNombreColumnas(Inventory, "ProductName", "JacketID"))**
3. Presione F5, seleccione el botón que acaba de crear y presione Esc para volver al área de trabajo de diseño.
4. En el menú **Archivo**, seleccione **Colecciones**.
5. Confirme que ha creado una colección, denominada **Inventory2**. La nueva colección contiene la misma información que **Inventory** salvo que la columna denominada **ProductName** en **Inventory** se denomina **JacketID** en **Inventory2**.

