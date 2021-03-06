---
title: Personalizar un formulario en una aplicación de lienzo | Microsoft Docs
description: En PowerApps, especifique qué datos se mostrarán en un formulario de aplicación de lienzo, en qué orden y en qué controles.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/17/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: bb6f8edb35bd6f19bff06516f6fb9d22de1320a0
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2018
ms.locfileid: "42852678"
---
# <a name="customize-a-canvas-app-form-in-powerapps"></a>Personalizar un formulario de aplicación de lienzo en PowerApps

En una aplicación de lienzo, personalice un control **Mostrar formulario** y un control **Editar formulario** para que muestren los datos más importantes y en el orden más intuitivo para ayudar a los usuarios a comprender y actualizar los datos fácilmente.

Cada formulario consta de una o más tarjetas, cada una de las cuales muestra datos de una columna determinada del origen de datos. Siga los pasos descritos en este tema para especificar qué tarjetas aparecen en un formulario y subir o bajar las tarjetas dentro de un formulario.

Si no está familiarizado con PowerApps, consulte [Introducción a PowerApps](getting-started.md).

## <a name="prerequisites"></a>Requisitos previos

[Generar una aplicación](data-platform-create-app.md) desde Common Data Service y, después, [personalizar la galería](customize-layout-sharepoint.md) en esa aplicación.

## <a name="show-and-hide-cards"></a>Mostrar y ocultar las tarjetas

1. Inicie sesión en [PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

    ![Página principal del sitio de PowerApps](./media/customize-forms-sharepoint/sign-in.png)


1. Abra la aplicación que ha generado y personalizado.

1. En la barra de navegación de la izquierda, escriba o pegue **D** en la barra de búsqueda para filtrar la lista de elementos y, después, pulse o haga clic en **DetailForm1** para seleccionarlo.

    ![Pantalla de selección de detalles](./media/customize-forms-sharepoint/select-detailform.png)

1. En el panel de la derecha, pulse o haga clic en **Cuentas** para mostrar el panel **Datos**.

    ![Mostrar el panel Datos](./media/customize-forms-sharepoint/show-data-pane.png)

1. En el panel **Datos**, desactive las casillas **Contacto principal**, **Descripción** y **Dirección 1: Calle 2** para ocultar estos campos.

    ![Lista de campos](./media/customize-forms-sharepoint/hide-fields.png)

1.  En el panel **Datos**, active la casilla **Dirección 1: Código postal** para mostrar ese campo.

    ![Lista de campos](./media/customize-forms-sharepoint/show-field.png)

## <a name="reorder-the-cards"></a>Reordenar las tarjetas
1. En el panel **Datos**, arrastre el campo **Nombre de cuenta** a la parte superior de la lista de campos.

    ![Mover tarjeta](./media/customize-forms-sharepoint/move-card.png)

    En las tarjetas de **DetailForm1** se refleja el mismo cambio.

    ![Tarjetas reordenadas](./media/customize-forms-sharepoint/reordered-card.png)

1. Reordene las demás tarjetas en esta secuencia:

    - Nombre de cuenta
    - Dirección 1: Calle 1
    - Dirección 1: Ciudad
    - Dirección 1: Código postal
    - Número de empleados
    - Ingresos anuales

1. En la barra de navegación de la izquierda, escriba o pegue **Ed** en la barra de búsqueda y, después, pulse o haga clic en **EditForm1** para seleccionarlo.

1. Repita los pasos descritos en el procedimiento anterior y en este para que los campos de **EditForm1** coincidan con los de **DetailForm1**.

## <a name="run-the-app"></a>Ejecutar la aplicación
1. En la barra de navegación de la izquierda, escriba o pegue **Br** para filtrar la lista y, después, pulse o haga clic en **BrowseScreen1** para seleccionarlo.

2. Para abrir el modo de vista previa, presione F5 (o seleccione el icono de **vista previa** situado cerca de la esquina superior derecha).

    ![Icono de vista previa](./media/customize-forms-sharepoint/open-preview.png)

3. En la esquina superior derecha, haga clic o pulse en el icono del signo más para agregar un registro a **EditScreen1**.

    ![Agregar registro](./media/customize-forms-sharepoint/add-record.png)

4. Agregue los datos que quiera y pulse o haga clic en el icono de marca de verificación en la esquina superior derecha para guardar los cambios y volver a **BrowseScreen1**.

    ![Guardar registro](./media/customize-forms-sharepoint/save-record.png)

5. Haga clic o pulse en la flecha del elemento que acaba de crear para mostrar detalles acerca de ese elemento en **DetailScreen1**.  

    ![Flecha derecha](./media/customize-forms-sharepoint/right-arrow.png)

6. En la esquina superior derecha, haga clic o pulse en el icono de edición para actualizar el registro en **EditScreen1**.

    ![Editar registro](./media/customize-forms-sharepoint/edit-record.png)

7. Cambie la información de uno o varios campos y haga clic o pulse en la marca de verificación de la esquina superior derecha para guardar los cambios en la lista de SharePoint y volver a **DetailScreen1**.  

    ![Guardar cambios](./media/customize-forms-sharepoint/save-record.png)

8. Cerca de la esquina superior derecha, pulse o haga clic en el icono de papelera para eliminar el registro que acaba de actualizar y volver a **ExaminarPantalla1**.

    ![Eliminar registro](./media/customize-forms-sharepoint/delete-record.png)

9. Cierre el modo de vista previa presionando Esc (o pulsando o haciendo clic en el icono Cerrar junto a la esquina superior izquierda).

## <a name="next-steps"></a>Pasos siguientes
- [Guardar y publicar](save-publish-app.md) la aplicación.
- [Personalizar una tarjeta](customize-card.md) en la aplicación.
