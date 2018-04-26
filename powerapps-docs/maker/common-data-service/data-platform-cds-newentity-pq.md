---
title: Inicio rápido para agregar datos a una entidad en Common Data Service mediante Power Query | Microsoft Docs
description: Inicio rápido con instrucciones paso a paso para usar Power Query para agregar datos a una entidad nueva o existente en Common Data Service for Apps desde otro origen de datos.
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: cds
ms.date: 03/21/2018
ms.author: anneta
ms.openlocfilehash: e54553467714bad1f4bc17963f1011c0decc1963
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="quickstart-add-data-to-an-entity-in-the-common-data-service-by-using-power-query"></a>Inicio rápido: Adición de datos a una entidad en Common Data Service mediante Power Query
En este procedimiento, creará una entidad en [Common Data Service for Apps](data-platform-intro.md) y la rellenará con datos de una fuente OData mediante Power Query. Puede usar las mismas técnicas para integrar datos de estos orígenes en línea y locales, entre otros:

* SQL Server
* Salesforce
* IBM DB2
* Access
* Excel
* API web
* Fuente OData
* Archivos de texto

También puede filtrar, transformar y combinar los datos antes de cargarlos en una entidad nueva o existente.

Si no tiene una licencia para PowerApps, puede [registrarse gratuitamente](../signup-for-powerapps.md).

## <a name="prerequisites"></a>Requisitos previos
Para seguir este tema, debe cambiar a un [entorno](../canvas-apps/working-with-environments.md) en el que se puedan crear entidades.

## <a name="specify-the-source-data"></a>Especificar los datos de origen

1. Inicie sesión en [PowerApps](https://web.powerapps.com) y pulse o haga clic en la flecha hacia abajo para **Datos** cerca del borde izquierdo.

    ![Página principal de PowerApps](./media/data-platform-cds-newentity-pq/sign-in.png)

1. En la lista que aparece, pulse o haga clic en **Integración de datos** y, después, en **Nuevo proyecto** cerca de la esquina superior derecha de la ventana.

1. En la lista de orígenes de datos, pulse o haga clic en **OData**.

    ![Elegir el conector de OAuth](./media/data-platform-cds-newentity-pq/choose-odata.png)

1. En **Configuración de conexión**, escriba o pegue esta dirección URL y, después, haga clic en **Siguiente**:<br>
`http://services.odata.org/V4/Northwind/Northwind.svc/`

1. En la lista de tablas, active la casilla **Clientes** y, después, pulse o haga clic en **Siguiente**.

    ![Seleccionar la tabla Clientes](./media/data-platform-cds-newentity-pq/select-table.png)

1. (Opcional) Para modificar el esquema para satisfacer sus necesidades, elija qué columnas quiere incluir, transforme la tabla de distintas maneras, agregue un índice o una columna condicional, o realice otros cambios.

1. En la esquina inferior derecha, pulse o haga clic en **Siguiente**.

## <a name="specify-the-target-entity"></a>Especificar la entidad de destino
1. En **Configuración de carga**, haga clic en **Load to new entity** (Cargar en la nueva entidad).

    ![Especificar el nombre de la nueva entidad](./media/data-platform-cds-newentity-pq/new-entity-name.png)

    Se puede asignar otro nombre o nombre para mostrar a la entidad nueva, pero para seguir este tutorial exactamente, deje los valores predeterminados.

1. En la lista **Campo de nombre principal**, pulse o haga clic en **ContactName** y después en **Siguiente** en la esquina inferior derecha.

    Puede especificar otro campo de nombre principal diferente, asignar otra columna de la tabla de origen a cada campo de la entidad que se está creando o hacer las dos cosas. Para seguir este tutorial exactamente, mantenga la asignación de columnas predeterminada.

1. Cuando el **Estado de la carga** sea **Completado**, haga clic en **Listo** en la esquina inferior derecha.

1. En **Datos** (cerca del borde izquierdo), haga clic en **Entidades** para mostrar la lista de entidades de la base de datos.

    La entidad **Customers** que se ha creado a partir de una fuente de OData aparece como una entidad personalizada.

    ![Lista de entidades estándar y personalizadas](./media/data-platform-cds-newentity-pq/entity-list.png)

> [!WARNING]
> Si se usa Power Query para agregar datos a una entidad existente, se sobrescribirán todos los datos de esa entidad.

Si hace clic en **Load to existing entity** (Cargar en la entidad existente), puede especificar una entidad a la que agregar los datos de la tabla **Customers**. Por ejemplo, podría agregar los datos a la entidad **Account** que se incluye con Common Data Service. En **Columna de origen**, también se puede especificar que los datos de la columna **ContactName** de la tabla **Customers** se deben agregar a la columna **Name** de la entidad **Accounts**.

![Especificar el nombre de la nueva entidad](./media/data-platform-cds-newentity-pq/existing-entity.png)

Esta funcionalidad nos entusiasma y estamos ansiosos por recibir sus comentarios. [Envíenos sus sugerencias y comentarios](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1) acerca de esta característica.

Si aparece un [mensaje de error sobre los permisos](data-platform-cds-newentity-troubleshooting-mashup.md), hable con el administrador.