---
title: Operadores | Microsoft Docs
description: "Información de referencia de los operadores de PowerApps, incluidos la sintaxis y ejemplos"
services: 
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/24/2017
ms.author: gregli
ms.openlocfilehash: 3250251e02170d2dd7bab441bc3c94705216ec00
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="operators-and-data-types-in-powerapps"></a>Operadores y tipos de datos de PowerApps
Algunos de estos operadores dependen del idioma del autor.  Para más información, consulte [Aplicaciones globales](../global-apps.md).

| Símbolo | Tipo | Sintaxis | Descripción |
| --- | --- | --- | --- |
| **.** |Selector de propiedad |**Slider1.Value<br>Color.Red<br>Acceleration.X** |Extrae una propiedad de una [tabla](../working-with-tables.md), control, [señal](signals.md) o enumeración.  Para lograr compatibilidad con versiones anteriores, también se puede usar **!** . |
| **.**<br>(o **,** [en función del idioma](../global-apps.md)) |Separador decimal |**1.23**<br>[o **1,23** en función del idioma] |Separador entre las partes entera y fraccionaria de un número.  El carácter depende del idioma. |
| **( )** |Paréntesis |**Filtrar(T, A &lt; 10)**<br><br>**(1 + 2) * 3** |Aplica el orden de prioridad y agrupa las subexpresiones en una expresión mayor |
| **+** |Operadores aritméticos |**1 + 2** |Suma |
| **-** |&nbsp; |**2 - 1** |Resta y signo |
| **\*** |&nbsp; |**2 * 3** |Multiplicación |
| **/** |&nbsp; |**2 / 3** |División (consulte también la función **[Resto](function-mod.md)**) |
| **^** |&nbsp; |**2 ^ 3** |Exponenciación, equivalente a la función **[Potencia](function-numericals.md)** |
| **%** |&nbsp; |**20 %** |Porcentaje (equivalente a &quot;* 1/100&quot;) |
| **=** |Operadores de comparación |**Precio = 100** |Igual a |
| **&gt;** |&nbsp; |**Precio &gt; 100** |Más de |
| **&gt;=** |&nbsp; |**Precio &gt;= 100** |Mayor o igual que |
| **&lt;** |&nbsp; |**Precio &lt; 100** |Menos de |
| **&lt;=** |&nbsp; |**Precio &lt;= 100** |Menor o igual que |
| **&lt;&gt;** |&nbsp; |**Precio &lt;&gt; 100** |No igual a |
| **&amp;** |Operador de concatenación de cadenas |**&quot;hello&quot; &amp; &quot; &quot; &amp; &quot;world&quot;** |Hace que varias cadenas aparezcan continuas |
| **&amp;&amp;** o **And** |Operadores lógicos |**Precio &lt; 100 &amp;&amp; Slider1.Value = 20**<br>o **Price &lt; 100 And Slider1.Value = 20** |Conjunción lógica, equivalente a la función **[Y](function-logicals.md)** |
| **&#124;&#124;** u **Or** |&nbsp; |**Price &lt; 100 &#124;&#124; Slider1.Value = 20** o **Price &lt; 100 Or Slider1.Value = 20** |Disyunción lógica, equivalente a la función **[Or](function-logicals.md)** |
| **!** o **Not** |&nbsp; |**!(Price &lt; 100)** o **Not (Price &lt; 100)** |Negación lógica, equivalente a la función **[No](function-logicals.md)** |
| **exactin** |[Operadores de pertenencia](#in-and-exactin-operators) |**Gallery1.Selected exactin SavedItems** |Perteneciente a una [colección](../working-with-data-sources.md#collections) o una tabla |
| **exactin** |&nbsp; |**&quot;Windows&quot; exactin "Para mostrar ventanas en el sistema de operativo Windows..."** |Prueba de subcadena (distingue mayúsculas de minúsculas) |
| **in** |&nbsp; |**Gallery1.Selected in SavedItems** |Perteneciente a una colección o una tabla |
| **in** |&nbsp; |**&quot;El&quot; en &quot;El teclado y el monitor...&quot;** |Prueba de subcadena (no distingue mayúsculas de minúsculas) |
| **@** |[Operador de desambiguación](#disambiguation-operator) |**MyTable[@fieldname]** |Desambiguación de campo |
| **@** |&nbsp; |**[@MyVariable]** |Desambiguación global |
| **,**<br>(o **;** [en función del idioma](../global-apps.md)) |Separador de lista |**If( X < 10, "Bajo", "Bien" )**<br>**{ X: 12, Y: 32 }**<br>**[ 1, 2, 3 ]**<br>[o **If( X < 10; "Bajo"; "Bien" )<br>{ FirstName: "Juana"; LastName: "Directora" }<br>[ 1; 2; 3 ]** ] |Separa: <ul><li>argumentos en llamadas a funciones</li><li>campos en un [registro](../working-with-tables.md#elements-of-a-table)</li><li>registros en una [tabla de valores](../working-with-tables.md#inline-syntax)</li></ul>.  Este carácter depende del idioma. |
| **;**<br>(o **;;** [en función del idioma](../global-apps.md)) |Encadenamiento de fórmulas |**Recopilar(T, A); Navegar(S1, &quot;&quot;)**<br>[o **Recopilar(T; A);; Navegar(S1; &quot;&quot;)**] |Separar invocaciones de funciones en las propiedades del comportamiento.  El operador de encadenamiento depende del idioma. |
| **Parent** |[Operador Parent](#parent-operator) |**Parent.Fill** |Acceso a las propiedades de un contenedor de control |
| **ThisItem** |[Operador ThisItem](#thisitem-operator) |**ThisItem.FirstName** |Acceder a los campos de una galería o un control de formulario |

## <a name="in-and-exactin-operators"></a>operadores in y exactin
Los operadores **[in](operators.md#in-and-exactin-operators)** y **[exactin](operators.md#in-and-exactin-operators)** se pueden usar para buscar una cadena en un [origen de datos](../working-with-data-sources.md), como una colección o una tabla importada. El operador **[in](operators.md#in-and-exactin-operators)** identifica coincidencias, independientemente del caso, mientras que  **[exactin](operators.md#in-and-exactin-operators)** identifica coincidencias solo si coinciden las mayúsculas. Este es un ejemplo:

1. Cree o importe una colección denominada **Inventario** y muéstrela en una galería, como describe el primer procedimiento de [Show images and text in a gallery, including gallery selection, sort, and filter](../show-images-text-gallery-sort-filter.md) (Mostrar texto e imágenes de una galería, incluidos la selección, ordenación y filtro de la galería).
2. Establezca la propiedad **[Elementos](../controls/properties-core.md)** de la galería en esta fórmula:
   <br>**Filtrar(Inventory, "E" in ProductName)**
   
    La galería muestra todos los productos, excepto Callisto, porque el nombre de ese producto es el único que no contiene la letra que ha especificado.
3. Cambie la propiedad **[Elementos](../controls/properties-core.md)** de la galería a esta fórmula:
   <br>**Filtrar(Inventory, "E" exactin ProductName)**
   
    La galería muestra solo Europa, porque es la única palabra que contiene la letra que ha especificado con el uso de mayúsculas y minúsculas que ha especificado.

## <a name="thisitem-operator"></a>Operador ThisItem
Puede mostrar datos en los controles **[Galería](../controls/control-gallery.md)**, **[Formulario de edición](../controls/control-form-detail.md)** o **[Formulario de presentación](../controls/control-form-detail.md)**  enlazándolos a una tabla o una colección.  Estos controles son un contenedor para otros controles y tarjetas.  Todas las tarjetas o controles del contenedor pueden acceder a los datos enlazados a través del operador **[ThisItem](operators.md#thisitem-operator)**.   

El operador **[ThisItem](operators.md#thisitem-operator)** se usa para especificar la [columna](../working-with-tables.md#columns) de datos de cada tarjeta o control en el control externo. Por ejemplo, el operador de la galería de productos de [Show images and text in a gallery, including gallery selection, sort, and filter](../show-images-text-gallery-sort-filter.md) (Mostrar texto e imágenes de una galería, incluidos la selección, ordenación y filtro de la galería) especificaba que el control de imagen mostraba el diseño del producto, la etiqueta superior mostraba el nombre del producto y la etiqueta inferior mostraba el número de unidades en existencias.

En el caso de las galerías anidadas, **[ThisItem](operators.md#thisitem-operator)** hace referencia a los elementos de la galería más interna. Suponiendo que los campos de fila de las galerías interna y externa no están en conflicto, también puede utilizar los nombres de campo (columna) no completos directamente. Este enfoque permite que las reglas de una galería interna hagan referencia a elementos de una galería externa.

## <a name="parent-operator"></a>Operador Parent
Algunos controles hospedan otros controles. Por ejemplo, los controles **[Pantalla](../controls/control-screen.md)**, **[Galería](../controls/control-gallery.md)**, **[Tarjeta](../controls/control-card.md)**, **[Formulario de edición](../controls/control-form-detail.md)** y **[Formulario de presentación](../controls/control-form-detail.md)** son contenedores de controles. Al control que hospeda se le denomina el "control primario" de los controles que contiene.

En PowerApps se puede hacer referencia a todos los controles por su nombre desde cualquier lugar de la aplicación. **Screen1** puede ser el nombre de una pantalla de una aplicación. Para recuperar el color de fondo de esta pantalla, puede usar **Screen1.Fill**.

Los controles de esta pantalla tienen otra opción. Pueden utilizar una referencia relativa: **Parent.Fill**. El operador **[Parent](operators.md#parent-operator)** hace referencia al control que hospeda este control, y que hace que todas sus propiedades estén disponibles. **[Parent](operators.md#parent-operator)** resulta muy útil, ya que no depende del nombre del control. Puede copiar y pegar un control contenedor sin necesidad de ajustar ninguna de las referencia del contenedor. Este operador también hace que la relación entre los controles primarios y secundarios sea más clara al leer fórmulas.

## <a name="disambiguation-operator"></a>Operador de desambiguación
Algunas funciones crean [ámbitos de registro](../working-with-tables.md#record-scope) para acceder a los campos de la tabla mientras se procesa cada registro, como **Filtrar**, **AddColumns** y **Suma**.  Los nombres de campo agregados con el ámbito de registro invalidan los mismos nombres de los restantes lugares de la aplicación.  Cuando esto sucede, para acceder a los valores desde fuera del ámbito de registro hay que utilizar el operador de desambiguación **@**:

* Para acceder a los valores desde ámbitos de registro anidados, utilice el operador **@** con el nombre de la tabla en la que opera y use el patrón ***Tabla*[@*FieldName*]**.  
* Para acceder a los valores globales, como orígenes de datos, colecciones y variables de contexto, use el patrón **[@*ObjectName*] ** (sin designar ninguna tabla).

Para más información y ejemplos, vea la explicación acerca de los [ámbitos de registro](../working-with-tables.md#record-scope).
