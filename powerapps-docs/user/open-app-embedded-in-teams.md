---
title: Adición de una aplicación a Microsoft Teams | Microsoft Docs
description: Agregue una aplicación a un canal de Microsoft Teams para que los usuarios con los que se ha compartido la puedan abrir desde dentro de ese canal.
services: ''
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: quickstart
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/18/2018
ms.author: mblythe
ms.openlocfilehash: 02248cc3e98f256df36bb6a57fac6e66c684a8bf
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="quickstart-add-an-app-to-microsoft-teams"></a>Inicio rápido: Adición de una aplicación a Microsoft Teams

Microsoft Teams es una plataforma de colaboración basada en chat creada sobre tecnologías de Office 365. Se puede personalizar la experiencia de Teams mediante la adición de aplicaciones de lienzo de PowerApps a los canales de Teams. En este tutorial, obtendrá información sobre cómo agregar la aplicación de ejemplo Presentación de productos a un canal de Teams y, después, abrirla desde ese canal. 

![Aplicación insertada en Microsoft Teams](./media/open-app-embedded-in-teams/embedded-app.png)

Si no está registrado para PowerApps, [regístrese gratuitamente](https://web.powerapps.com/signup?redirect=marketing&email=) antes de empezar.

## <a name="prerequisites"></a>Requisitos previos

Para seguir este tutorial rápido, necesita una [suscripción a Office 365](https://signup.microsoft.com/Signup?OfferId=467eab54-127b-42d3-b046-3844b860bebf&dl=O365_BUSINESS_PREMIUM&ali=1) y un [canal en Teams](https://www.youtube.com/watch?v=he2f1quaR7M).

## <a name="sign-in-to-powerapps"></a>Inicio de sesión en PowerApps

Inicie sesión en PowerApps en [https://web.powerapps.com]([https://web.powerapps.com).

## <a name="add-an-app"></a>Incorporación de una aplicación

1. En Microsoft Teams, seleccione un equipo y un canal bajo ese equipo. En este ejemplo, es el canal **General** del equipo **Desarrollo empresarial**.

    ![](./media/open-app-embedded-in-teams/teams-select-channel.png)

2. Haga clic en **+** para agregar una pestaña.

    ![](./media/open-app-embedded-in-teams/teams-add-tab.png)

3. En el cuadro de diálogo **Add a tab** (Agregar una pestaña), haga clic en **PowerApps**.

    ![](./media/open-app-embedded-in-teams/add-a-tab.png)

4. Seleccione **Aplicaciones de ejemplo** > **Presentación de productos** > **Guardar**.

    ![](./media/open-app-embedded-in-teams/select-an-app.png)

    La aplicación ya está disponible para su uso en el canal.

    ![](./media/open-app-embedded-in-teams/app-in-channel.png)

> [!NOTE]
> Debe [compartir](../maker/canvas-apps/share-app.md) sus propias aplicaciones antes de agregarlas a Teams (las aplicaciones de ejemplo se comparten de forma predeterminada).

## <a name="open-an-app"></a>Abrir una aplicación

1. En Microsoft Teams, seleccione el equipo y el canal que contiene la aplicación.

    ![](./media/open-app-embedded-in-teams/teams-select-channel.png)

2. Haga clic en la pestaña **Presentación de productos**.

    ![](./media/open-app-embedded-in-teams/open-tab.png)

    La aplicación se abre en el canal.

    ![](./media/open-app-embedded-in-teams/app-in-channel.png)

## <a name="known-issues"></a>Problemas conocidos

En la aplicación de escritorio de Microsoft Teams:

* Las aplicaciones tienen que cargar contenido, como imágenes y archivos .pdf a través de una conexión segura (https).
* No todos los sensores, como **Aceleración**, **Brújula**, y **Ubicación**, son compatibles.
* Se admiten únicamente estos formatos de audio: AAC, H264, OGG Vorbis y WAV.

## <a name="clean-up-resources"></a>Limpiar los recursos

Para quitar la aplicación del canal, haga clic en la pestaña **Presentación de productos** > **Quitar**.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha agregado la aplicación de ejemplo Presentación de productos a un canal de Teams y, después, la ha abierto desde ese canal. Para obtener más información sobre PowerApps, continúe con los tutoriales de PowerApps.

> [!div class="nextstepaction"]
> [Tutoriales de PowerApps](../maker/canvas-apps/get-started-create-from-blank.md)