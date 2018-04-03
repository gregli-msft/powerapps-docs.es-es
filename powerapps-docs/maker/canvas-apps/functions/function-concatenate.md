---
title: Funciones Concat y Concatenate | Microsoft Docs
description: Información de referencia sobre las funciones Concat y Concatenate de PowerApps, incluidos ejemplos y sintaxis
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/28/2017
ms.author: gregli
ms.openlocfilehash: 5f69d51fc1d018a48576cade665ebd19ec1d7c82
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="concat-and-concatenate-functions-in-powerapps"></a>Funciones Concat y Concatenate de PowerApps
Concatena cadenas de texto individuales y cadenas en [tablas](../working-with-tables.md).

## <a name="description"></a>Descripción
La función **Concat** concatena el resultado de una fórmula que se aplica en todos los [registros](../working-with-tables.md#records) de una tabla, lo que genera una sola cadena. Use esta función para resumir las cadenas de una tabla, tal como hace la función **[Sum](function-aggregates.md)** para los números.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Use la función **[Split](function-split.md)** para dividir una cadena en una tabla de subcadenas.

La función **Concatenate** concatena una combinación de cadenas individuales y una tabla de cadenas con una sola columna. Cuando se usa con cadenas individuales, esta función es equivalente a usar el [operador](operators.md) **&**. Puede usar una fórmula que incluye la función **[ShowColumns](function-table-shaping.md)** para crear una tabla de una columna a partir de una tabla con varias columnas.

## <a name="syntax"></a>Sintaxis
**Concat**( *Table*, *Formula* )

* *Table*: requerido.  La tabla sobre la cual se opera.
* *Formula*: requerido.  Fórmula para aplicar en todos los registros de la tabla.

**Concatenate**( *String1* [, *String2*, ...] )

* *String(s)*: requerido.  Combinación de cadenas individuales o una tabla de cadenas de una columna.

## <a name="examples"></a>Ejemplos
#### <a name="concat"></a>Concat
1. Agregue un control **[Botón](../controls/control-button.md)** y establezca su propiedad **[OnSelect](../controls/properties-core.md)** en esta fórmula:
   
    **Collect(Products, {String:"Violin", Wind:"Trombone", Percussion:"Bongos"}, {String:"Cello", Wind:"Trumpet", Percussion:"Tambourine"})**
2. Presione F5, haga clic en el botón y presione Esc para volver al área de trabajo de diseño.
3. Agregue un control **[Etiqueta](../controls/control-text-box.md)** y establezca su propiedad **[Texto](../controls/properties-core.md)** en esta fórmula:
   
    **Concat(Products, String & " ")**
   
    La etiqueta muestra **Violin Cello**.

#### <a name="concatenate"></a>Concatenate
1. Agregue un control **[Entrada de texto](../controls/control-text-input.md)** y denomínelo **AuthorName**.
2. Agregue un control **[Etiqueta](../controls/control-text-box.md)** y establezca su propiedad **[Texto](../controls/properties-core.md)** en esta fórmula:<br>
   **Concatenate("By ", AuthorName.Text)**
3. Escriba su nombre en **AuthorName**.
   
    La etiqueta muestra **By** antes del nombre.

Si tuviera una tabla **Employees** que incluye una columna **FirstName** y una columna **LastName**, esta fórmula concatenaría los datos de cada fila de esas columnas.
<br>**Concatenate(Employees.FirstName, " ", Employees.LastName)**
