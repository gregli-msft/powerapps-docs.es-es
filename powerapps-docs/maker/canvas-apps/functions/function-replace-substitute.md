---
title: Funciones Reemplazar y Substitute | Microsoft Docs
description: Información de referencia para las funciones Replace y Substitute en PowerApps, incluida la sintaxis
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
ms.openlocfilehash: d403fc5d756934900664affc04619c5cc72af6ee
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2018
ms.locfileid: "42834368"
---
# <a name="replace-and-substitute-functions-in-powerapps"></a>Funciones Replace y Substitute en PowerApps
Reemplace una parte de una cadena de texto por otra cadena.

## <a name="description"></a>Descripción
La función **Replace** identifica el texto que se debe reemplazar según la posición inicial y la longitud.  

La función **Substitute** identifica el texto que se debe reemplazar buscando una cadena coincidente.  Si se encuentra más de una coincidencia, puede controlar cuál se reemplaza.

Si pasa una única cadena, el valor devuelto es la cadena modificada.  Si pasa una [tabla](../working-with-tables.md) de una sola columna que contiene cadenas, el valor devuelto es la tabla de una sola columna con cadenas modificadas. Si tiene una tabla con varias columnas, puede convertirla en una tabla de una sola columna, como se describe en cómo [trabajar con tablas](../working-with-tables.md).

## <a name="syntax"></a>Sintaxis
**Replace**( *String*, *StartingPosition*, *NumberOfCharacters*, *NewString* )

* *Cadena*: requerido. La cadena en la que se va a actuar.
* *StartingPosition*: requerido.  La posición del carácter en la que se va a iniciar el reemplazo. El primer carácter de *String* está en la posición 1.
* *NumberOfCharacters*: requerido.  El número de caracteres que se van a reemplazar en *String*.
* *NewString*: requerido.  La cadena de reemplazo. El número de caracteres de este argumento puede diferir del argumento *NumberOfCharacters*.

**Substitute**( *String*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *Cadena*: requerido. La cadena en la que se va a actuar.
* *OldString*: requerido.  La cadena que se va a reemplazar.
* *NewString*: requerido.  La cadena de reemplazo. *OldString* y *NewString* pueden tener longitudes distintas.
* *InstanceNumber*: opcional. De forma predeterminada, se reemplaza la primera instancia de *OldString*. Si *String* contiene más de una instancia, puede especificar qué instancia desea reemplazar.

**Replace**( *SingleColumnTable*, *StartingPosition*, *NumberOfCharacters*, *NewString* )

* *SingleColumnTable*: requerido. Una tabla de números de una sola columna sobre la que se va a actuar.
* *StartingPosition*: requerido.  La posición del carácter en la que se va a iniciar el reemplazo.  El primer carácter de cada cadena de la tabla se encuentra en la posición 1.
* *NumberOfCharacters*: requerido.  El número de caracteres que se van a reemplazar en cada cadena.
* *NewString*: requerido.  La cadena de reemplazo. El número de caracteres de este argumento puede diferir del argumento *NumberOfCharacters*.

**Substitute**( *SingleColumnTable*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *SingleColumnTable*: requerido. Una tabla de números de una sola columna sobre la que se va a actuar.
* *OldString*: requerido.  La cadena que se va a reemplazar.
* *NewString*: requerido.  La cadena de reemplazo. *OldString* y *NewString* pueden tener longitudes distintas.
* *InstanceNumber*: opcional. De forma predeterminada, se reemplaza la primera instancia de *OldString*. Si la tabla contiene más de una instancia, puede especificar cuál desea reemplazar.

