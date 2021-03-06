---
title: 'Control Columna: referencia | Microsoft Docs'
description: En este tema se proporciona información sobre el control Columna en Microsoft PowerApps.
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/05/2017
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e1c8ba704a01c989da990fd1b2b17f7b5def5541
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2018
ms.locfileid: "42850864"
---
# <a name="column-control-in-powerapps"></a>Control Columna en PowerApps
Proporciona la representación de un solo campo en un control [**Tabla de datos**](control-data-table.md).

## <a name="description"></a>Descripción
El control [**Tabla de datos**](control-data-table.md) muestra un conjunto de datos en formato tabular, y cada columna en ese formato tabular se representa mediante un control **Columna**. El control **Columna** proporciona propiedades que el creador de la aplicación puede usar para personalizar la apariencia y el comportamiento de la columna.

## <a name="capabilities"></a>Funcionalidades
### <a name="now-available"></a>Ahora disponible
* Cambie el ancho de un control **Columna**.
* Cambie el texto de un control **Columna**.
* Navegue pulsando o haciendo clic en el valor de un control **Columna**.

### <a name="not-yet-available"></a>Aún no está disponible
* Personalice el estilo de un control **Columna**.

### <a name="known-issues"></a>Problemas conocidos
* La propiedad **Visible** todavía no funciona.

## <a name="properties"></a>Propiedades
* **DisplayName** (NombreParaMostrar): el texto que aparece en el encabezado de la columna.
  
  > [!NOTE]
  > El nombre de esta propiedad se cambiará pronto a **HeaderText** (TextoDeEncabezado).
  > 
  > 
* **IsHyperlink** (EsHipervínculo): un valor que indica si los datos de la columna deben subrayarse para indicar que se trata de un hipervínculo.
* [**Ancho**](properties-size-location.md): la distancia entre los bordes derecho e izquierdo del control **Columna**.

## <a name="examples"></a>Ejemplos
### <a name="resize-a-column"></a>Cambio del tamaño de una columna
1. Cree una aplicación de tableta vacía.
2. En la pestaña **Insertar**, pulse o haga clic en **Tabla de datos** y cambie el tamaño del control **Tabla de datos** de modo que cubra toda la pantalla.
3. En el panel derecho, pulse o haga clic en la flecha abajo a la derecha de **No se ha seleccionado un origen de datos** y en **Agregar un origen de datos**.
4. En la lista de conexiones, pulse o haga clic en la conexión para la base de datos de Common Data Service.
5. En la lista de entidades, pulse o haga clic en **Cuenta** y en **Conectar**.
   
    El control **Tabla de datos** se inicializa y muestra un conjunto de campos predeterminados.
6. Pulse o haga clic en la columna **Nombre completo**.
   
    ![Control Columna seleccionado](./media/control-column/pre-resize-column.png)
7. Arrastre el adorno del lado derecho para cambiar el tamaño del campo.
   
    ![Control Columna con tamaño cambiado](./media/control-column/post-resize-column.png)


## <a name="accessibility-guidelines"></a>Directrices de accesibilidad
### <a name="screen-reader-support"></a>Soporte técnico para el lector de pantalla
* La propiedad **DisplayName** debe existir.
