---
title: Generar una aplicación de lienzo en PowerApps desde SharePoint | Microsoft Docs
description: En PowerApps, genere automáticamente una aplicación de lienzo para administrar datos de una lista de SharePoint.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/12/2018
ms.author: anneta
ms.openlocfilehash: cb68c454053a36f49b72afa1718ca0d67ad364af
ms.sourcegitcommit: e3f5a2bef64085d02aec82e62ff94ae8a4d01d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2018
ms.locfileid: "39469888"
---
# <a name="generate-a-canvas-app-in-powerapps-from-sharepoint-data"></a>Generar una aplicación de lienzo en PowerApps a partir de datos de SharePoint

En este tutorial, usará PowerApps para generar automáticamente la primera aplicación de lienzo a partir de una lista que cree en SharePoint. En esta aplicación, se pueden examinar todos los elementos de la lista, mostrar detalles de un solo elemento y crear, actualizar o eliminar un elemento.

Si tiene cualquier lista de SharePoint, puede obtener información sobre conceptos y técnicas en este tutorial rápido. Para seguir este tutorial rápido con exactitud, cree una lista, con el nombre **SimpleApp**, que contenga una columna denominada **Título**, en un sitio de SharePoint Online. En la lista, cree entradas para **Vainilla**, **Chocolate** y **Fresa**.

Puede crear una lista que sea mucho más compleja con muchas columnas de varios tipos, como texto, fechas, números y moneda. Los principios de la generación de una aplicación no cambian. También se puede generar una aplicación a partir una lista en un sitio de SharePoint local si se [conecta al sitio](connect-to-sharepoint.md) a través de una puerta de enlace de datos.

Si no tiene una licencia para PowerApps, puede [registrarse gratuitamente](../signup-for-powerapps.md).

## <a name="generate-an-app"></a>Generar una aplicación
1. Inicie sesión en [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

    ![Página principal de PowerApps](./media/app-from-sharepoint/sign-in.png)

1. En **Make apps like these** (Crear aplicaciones como estas), mantenga el puntero sobre **Start from data** (Iniciar desde datos) y, después, haga clic en **Crear esta aplicación**.

    ![Opción para crear una aplicación](./media/app-from-sharepoint/make-this-app.png)

1. En el icono de SharePoint, seleccione **Diseño de teléfono**.

    ![Opción para crear una aplicación](./media/app-from-sharepoint/sharepoint-tile.png)

1. Con la opción **Conectar directamente** seleccionada, haga clic en **Crear**.

    ![Crear conexión](./media/app-from-sharepoint/create-connection.png)

1. En **Conectar a un sitio de SharePoint**, escriba o pegue la dirección URL para el sitio de SharePoint Online y, después, haga clic en **Ir**.

    Incluya solo la dirección URL del sitio (no el nombre de la lista), como en este ejemplo:<br>`https://microsoft.sharepoint.com/teams/Contoso`

1. En **Elegir una lista**, seleccione **SimpleApp** y, después, haga clic en **Conectar**.

Después de unos minutos, la aplicación se abre en la pantalla de exploración, en la que se muestran los elementos creados en la lista. Si la lista tiene datos en más columnas además de **Título**, la aplicación mostrará esos datos. Cerca de la parte superior de la pantalla, en una barra de título se muestran iconos para actualizar la lista, ordenarla y crear un elemento en la lista. Bajo la barra de título, un cuadro de búsqueda proporciona la opción de filtrar la lista según el texto que se escriba o pegue. 

![Pantalla de exploración](./media/app-from-sharepoint/browse-screen.png)

Probablemente le interesará realizar más cambios antes de usar esta aplicación o compartirla con otros usuarios. Como procedimiento recomendado, guarde el trabajo realizado hasta el momento antes de continuar presionando Ctrl-S. Asigne un nombre a la aplicación y, después, haga clic en **Guardar**.

## <a name="next-steps"></a>Pasos siguientes
En este tutorial, ha creado una aplicación para administrar datos en una lista de SharePoint. El siguiente paso es generar una aplicación a partir de una lista más compleja y, después, personalizar la aplicación (empezando por la pantalla de exploración) para que se ajuste mejor a las necesidades.

> [!div class="nextstepaction"]
> [Personalizar una pantalla de exploración predeterminada](customize-layout-sharepoint.md)