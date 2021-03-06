---
title: Personalización de comandos con aplicaciones controladas por modelos | Microsoft Docs
description: Obtenga información sobre cómo personalizar comandos con aplicaciones controladas por modelos.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/17/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 4721ba49fe227d31f539eabd863b50842e7515b6
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2018
ms.locfileid: "42836263"
---
# <a name="customize-commands-with-model-driven-apps"></a>Personalización de comandos con aplicaciones controladas por modelos 

Los comandos que aparecen en una barra de comandos de un formulario o lista son personalizables. Los comandos se basan en los esquemas XML que se usan en las cintas de opciones de Office, por lo que todavía se usa el término *cinta*. Cuando se crea un comando, se pueden definir tres elementos:

- Las *reglas de visualización* se evalúan cuando se carga el formulario o la lista para determinar si un comando o un grupo de comandos son visibles.
- Las *reglas de habilitación* controlan si un comando está habilitado en función de varias condiciones como el elemento seleccionado actualmente en la interfaz de usuario.
- Una *acción* para cada comando que le indique lo que debe hacer cuando se seleccione. Un comando puede abrir una dirección URL o ejecutar una función definida dentro de un recurso web de JavaScript.

Los comandos personalizados se colocan en función de los comandos existentes. Se debe crear una *acción personalizada* que defina qué cambio se va a aplicar al conjunto de comandos existente. 

No se proporciona ningún diseñador para los comandos. Afortunadamente, la comunidad ha proporcionado herramientas. [Ribbon Workbench](http://www.develop1.net/public/rwb/ribbonworkbench.aspx) proporciona una interfaz gráfica y es la herramienta más usada para personalizar los comandos.

Más información: [Personalizar los comandos y la cinta de opciones (Guía para desarrolladores de Dynamics 365 Customer Engagement)](/dynamics365/customer-engagement/developer/customize-dev/customize-commands-ribbon)


