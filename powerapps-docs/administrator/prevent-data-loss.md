---
title: Administración de directivas de prevención de pérdida de datos (DLP) | Microsoft Docs
description: Tutorial sobre cómo administrar directivas de prevención de pérdida de datos para PowerApps.
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 4faa8a4cc58b138eec4e7dfe8d35b927faf905b7
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2018
ms.locfileid: "42837171"
---
# <a name="manage-data-loss-prevention-dlp-policies"></a>Administración de directivas de prevención de pérdida de datos (DLP)
Los datos de una organización son fundamentales para su éxito. Los datos tienen que estar disponibles de inmediato para la toma de decisiones, pero tienen que protegerse de manera que no se compartan con personas que no deben tener acceso a ellos. Para proteger estos datos, PowerApps permite crear y aplicar directivas de prevención de pérdida de datos (DLP) que definen con qué conectores de consumidor se pueden compartir datos empresariales específicos. Por ejemplo, es posible que una organización que utiliza PowerApps no desee que los datos empresariales que se almacenan en SharePoint se publiquen automáticamente en su publicación de Twitter.

Para crear, editar o eliminar directivas DLP, debe tener los permisos Administrador de entorno o Administrador de inquilino de Azure Active Directory. Para obtener más información, vea [Administración de entornos en PowerApps](environments-administration.md).

Para obtener instrucciones sobre cómo crear una directiva DLP, vea [Crear una directiva de prevención de pérdida de datos (DLP)](create-dlp-policy.md).

## <a name="find-a-dlp-policy"></a>Buscar una directiva DLP
1. Inicie sesión en el Centro de administración en [https://admin.powerapps.com]([https://admin.powerapps.com).
2. En el panel de navegación, pulse o haga clic en **Directivas de datos**. Si tiene una lista larga de directivas, use el cuadro **Buscar** cuadro para buscar directivas DLP específicas.

    ![](./media/prevent-data-loss/data-policies.png)

## <a name="edit-a-dlp-policy"></a>Editar una directiva DLP
1. En la lista de directivas de prevención de pérdida de datos, pulse o haga clic en el icono de lápiz situado junto a la directiva que quiere modificar.

    ![Iniciar sesión](./media/prevent-data-loss/3.png)
2. Realice los cambios y, después, pulse o haga clic en **Guardar directiva**.

    > [!NOTE]
    > Las directivas DLP de los entornos no pueden reemplazar las directivas DLP de los inquilinos.
    >
    >

    Para revisar los cambios, busque la directiva DLP en la lista de directivas de prevención de pérdida de datos y pulse o haga clic en ella para revisar sus propiedades.

## <a name="delete-a-dlp-policy"></a>Eliminar una directiva DLP
1. En la lista de directivas de prevención de pérdida de datos, pulse o haga clic en el icono de la papelera situado junto a la directiva que quiere eliminar.

    ![Iniciar sesión](./media/prevent-data-loss/3-delete.png)
4. En el cuadro de diálogo de confirmación, pulse o haga clic en **Eliminar**.

    La directiva se elimina y ya no aparece en la lista de directivas de prevención de pérdida de datos.

## <a name="next-steps"></a>Pasos siguientes
* [Aprender más acerca de los entornos](environments-administration.md)
* [Aprender más acerca de Microsoft PowerApps](../maker/canvas-apps/getting-started.md)
